---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティのトラブルシューティング
description: プロファイルトークンの問題、キャンペーン設定、配信エラーなど、Journey Optimizerのライブアクティビティをユニタリユースケースとブロードキャストユースケースの両方でトラブルシューティングする方法について説明します
role: User
level: Intermediate
exl-id: f0f83bd2-7c2b-4d9b-b455-e1df12dfa175
feature_v2:
  - id: b49ca41f-eb7a-4f4b-abeb-a97c06fd0c04
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: c96d2aa5-76a2-443d-8d23-5de95577c909
  - id: ed2fba79-65cb-4680-96d2-2ad5d851714d
source-git-commit: 8d7aea9c58b0f7622f3b11c21db55536ffe1cb66
workflow-type: tm+mt
source-wordcount: 5964
ht-degree: 1%

---

# ライブアクティビティのトラブルシューティング {#troubleshoot-mobile-live}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、ライブアクティビティが表示、更新、終了できない理由を体系的に診断するため、単一およびブロードキャストのユースケースの両方で、プロファイルトークン、キャンペーン設定、ペイロード、配信の問題を解決できます。

>[!ENDSHADEBOX]

Adobe Journey Optimizerのライブアクティビティにより、iOSのロック画面やダイナミック諸島でリアルタイムかつダイナミックに更新できます。 トリガーおよび管理できるのは、API トリガーキャンペーンのみです。

**ユースケースの種類：**

* **単一**：個別にターゲティングされたトランザクション （API トリガーのトランザクションキャンペーン）
* **ブロードキャスト**：オーディエンスをターゲットにした一括配信（API トリガーによるマーケティングキャンペーン）

ライブアクティビティに関する頻繁な課題は、ライブアクティビティをトリガーまたは更新するAPI呼び出しが&#x200B;**成功したレスポンス（200 OK）**&#x200B;を返すが、ライブアクティビティがユーザーのデバイスに表示または更新されない場合です。 API確認と実際のデバイス動作の間のこの断絶は、配信パイプラインの複数のポイントで発生する可能性があります。 このガイドでは、API リクエストの検証からデバイスのレンダリングに至るまで、各ステージを調べて、配信が失敗している場所を特定するための体系的なトラブルシューティングのアプローチを提供します。

## 主要な課題

| 症状 | ユースケース | に移動 |
|---------|----------|-------|
| APIが200 OKを返しますが、ライブアクティビティはデバイスに表示されません | 両方 | [&#x200B; シナリオ 1: プロファイルまたはプッシュトークンの問題](#scenario-1-profile-or-push-token-issues) |
| ライブアクティビティが表示されますが、更新または終了しません | 単一（1:1） | [&#x200B; シナリオ 4：更新トークンが同期されていません](#scenario-4-live-activity-update-token-not-synced) |
| キャンペーンとトークンは正しく表示されますが、配信は失敗します | 両方 | [&#x200B; シナリオ 3：配信エラーとエラー分析](#scenario-3-delivery-failures-and-error-analysis) |
| ペイロード設定またはAPI構造が不明確 | 両方 | [&#x200B; シナリオ 2: キャンペーン設定とペイロードの問題](#scenario-2-campaign-configuration-and-payload-issues) |
| ブロードキャストを受信しない特定のオーディエンスメンバー | 放送 | [&#x200B; シナリオ 7: プロファイルがオーディエンスにないか、古いスナップショットです](#scenario-7-profile-not-in-audience-or-stale-audience-snapshot) |
| 実行ステータスをプログラムで確認する必要がある | 単一（1:1） | [&#x200B; シナリオ 5: API](#scenario-5-checking-execution-status-via-the-api)を介した実行ステータスの確認 |
| Assuranceへのアクセス権なし。実稼動レベルのデバッグが必要 | 両方 | [詳細：データセット クエリを使用したデバッグ &#x200B;](#advanced-debugging-via-dataset-queries) |

## 2つのユースケースについて

デバッグの前に、キャンペーンに適用されるユースケースを確認します。 根本原因とデバッグパスは大きく異なります。

| | 単一（1:1） | 放送 |
|---|---|---|
| **AJO キャンペーンの種類** | API トリガーのトランザクション | API トリガーマーケティング |
| **ターゲティング** | `recipients[].userId`経由の個人プロファイル | `audience.id`経由のオーディエンスセグメント |
| **開始するトークン** | プッシュから開始までのトークン（プロファイルごと） | `input-push-channel` （ブロードキャストインスタンスごと） |
| 更新/終了する&#x200B;**トークン** | トークンを更新（ライブアクティビティインスタンスごとに） | 開始と同じ`input-push-channel` |
| **オーディエンスの鮮度リスク** | 該当なし | 最大24時間古い（バッチ評価） |

## 用語集

| 用語 | 定義 |
|------|------------|
| **プッシュから開始トークン** | IOS 17以降で生成されたAPNs トークンで、アプリを開かずにAJOがデバイス上でライブアクティビティをリモートで開始できるようにします。 モバイル SDKで登録され、AEP プロファイルに保存されます。 |
| **トークンを更新** | ライブアクティビティがデバイスで開始されたときに生成されるインスタンスごとのAPNs トークン。 単一の`update`および`end` イベントに必要です。 各ライブアクティビティインスタンスには、それぞれ固有の更新トークンがあります。 |
| **input-push-channel** | ブロードキャストライブアクティビティ用にApple Developer Portalで作成された一意のチャネル ID。 ブロードキャスト更新トークンとして機能し、このチャネルに登録されているすべてのデバイスは、同じライブアクティビティイベントを受け取ります。 |
| **liveActivityData** | Adobe SDKの`LiveActivityAttributes` プロトコルに必要なプロパティです。 単一の場合は、ブロードキャストの場合は`liveActivityID`；が含まれ、`channelID`が含まれます。 開始イベントペイロードの`attributes` フィールドに含める必要があります。 |
| **ブロードキャストチャネル ID** | 値`input-push-channel`。 ブロードキャストペイロードの`liveActivityData.channelID`と完全に一致する必要があります。 |
| **attributeType / attributes-type** | Swift `ActivityAttributes`構造体の名前。 AEP プロファイル属性に`attributeType` （camelCase）として保存され、APS JSON ペイロードに`attributes-type` （ハイフネーション）として送信されます。 これらは、異なる表示域で同じ値です。 |
| **liveActivityPushNotificationDetails** | デバイスのプッシュ対スタートトークン、`appId`、`platform`、および`attributeType`を格納するAEP プロファイル属性。 リモートスタートが機能するには、存在し、有効である必要があります。 |
| **APS ペイロード** | `context.requestPayload.aps`の下のAPI リクエスト内で送信されたJSON構造。 ライブアクティビティイベント、`content-state`、`attributes`、およびコントロールフィールドが含まれます。 |
| **Assurance** | Adobe Experience Platform Assurance：接続されたテストデバイス向けのリアルタイムデバッグツール 実稼動エンドユーザーデバイスでは使用できません。 |

## 前提条件

トラブルシューティングを行う前に、次の項目を確認してください。

+++ ライブアクティビティ用Assurance プラグイン

Adobe Experience Platform Assuranceのライブアクティビティビューでは、アプリの設定を検証し、アクティビティイベントを調べ、テストセッションからリモートでアクティビティを開始、更新、終了できます。

>[!IMPORTANT]
>
> Assurance セッションは、テストおよびQA デバイス専用です。 エンドユーザーの実稼動デバイスは、Assuranceに接続されていません。 実稼動診断の場合は、このガイドの最後にある「[詳細：データセットクエリを使用したデバッグ &#x200B;](#advanced-debugging-via-dataset-queries)」セクションを使用してください。

### 要件

| 要件 | 詳細 |
|---|---|
| iOS デバイス | IOS 16.1以降を実行している物理デバイス |
| Xcode Simulator | iOS 16.1以降&#x200B;**ローカル開始のみ**、APN経由のリモート プッシュはSimulatorではサポートされていません |
| Assuranceからのリモートスタート | iOS 17.1以降、有効なプッシュから開始までのトークン、有効なチャネル設定 |
| Mobile SDK | Adobe Experience Platform Mobile SDK 5.11.0以降 |
| Session | アクティブなAssuranceセッション |

### 3つのタブ

| タブ | What it shows |
|-----|---------------|
| **クライアント情報** | デバイス、プロファイル、App Storeの資格情報。 緑のチェック =正しく設定されている；インラインアラート =提案された修正を伴う問題。 以下の各シナリオのプリチェックに直接マッピングします。 |
| **アクティビティ** | 選択したクライアントのライブアクティビティ：タイプ（単一/ブロードキャスト）、ID、ステータス、イベント数。 サブタブ：概要（基本情報+ アップデートを送信ボタン）、アクティビティフロー（検査可能なペイロードを含むライフサイクルタイムライン）、イベントの詳細（イベントごとの完全なペイロード検査）。 |
| **イベント** | ライブアクティビティの開始、更新、終了イベントを含む、クライアントのすべてのAssurance イベント。 |

### Assuranceから開始、更新、終了

**ライブアクティビティを開始**。 登録されたアクティビティタイプを選択するダイアログを開き、「単一」または「ブロードキャスト」を選択し、ブロードキャストチャネル ID （ブロードキャストのみ）を入力し、事前入力されたAPS JSON ペイロードを編集します。 プッシュから開始トークン、iOS バージョン、またはチャネル設定の要件が満たされない場合、ボタンが無効になるか、エラーが返されます。

**更新を送信**。 既存のアクティビティの「概要」タブから、「更新」（新しいコンテンツをプッシュ）または「終了」イベントを送信します。 単一の場合、プラグインはアクティビティの更新トークンを自動的に使用します。 ブロードキャストの場合、同じブロードキャストチャネル IDに登録されているすべてのデバイスをターゲットにします。 ペイロードは有効なJSONで、アクティビティの属性スキーマに一致する必要があります。そうでない場合、リクエストは拒否されます。

セットアップとセッション接続の手順については、[Adobe Experience Platform Assurance ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/home.html)を参照してください。

+++

+++ API トリガーキャンペーンの詳細の収集

Journey OptimizerでAPI Triggered Campaignに移動し、次を取得します。

* キャンペーン名とID
* キャンペーンバージョン（該当する場合）
* キャンペーンの種類：**トランザクション** （単一）または&#x200B;**マーケティング** （ブロードキャスト）
* サーフェス設定：ライブアクティビティに使用されるiOS アプリサーフェス
* アクティビティタイプ：キャンペーンで設定された`AttributeType`構造体名

+++

+++ API リクエスト情報の収集

ライブアクティビティをトリガーするAPI呼び出しを行う際に、次を保存します。

* プロファイル識別子やライブアクティビティデータを含むAPI リクエストペイロード
* ステータスコード、メッセージ ID、リクエスト IDを含むAPI応答
* APIが呼び出されたときのタイムスタンプ
* 使用されているエンドポイント （例：`/campaign/{CAMPAIGN_ID}/execute`）

+++

+++ テストプロファイルの特定

API リクエストから、次を取得します。

* プロファイル名前空間（例：ECID、電子メール、顧客ID）
* API呼び出しで使用されるプロファイル ID

Adobe Experience Platformでこのプロファイルを検索できることを確認します。 プロファイルを[検索する方法については、Experience Platform ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/profile/ui/user-guide.html)を参照してください。

+++

+++ デバイスとアプリ情報

テストデバイスから以下を収集します。

* デバイスモデル（例：iPhone 14 Pro）
* iOS版
* アプリバンドル識別子
* APNs プッシュトークン
* テスト時のネットワーク接続ステータス

+++

## 一般的なシナリオ

### シナリオ 1: プロファイルまたはプッシュトークンの問題 {#scenario-1-profile-or-push-token-issues}

[!BADGE 単一とブロードキャストの両方のユースケースに適用]{type=Positive}

APIはHTTP 200を返しますが、Live アクティビティは表示されません。 一般的な原因：

* Adobe Experience Platformにプロファイルが存在しません。
* ライブアクティビティプッシュトークンがプロファイルに同期されていません。
* ライブアクティビティのプッシュの詳細は同期されますが、誤った設定（例：`appId`または`attributeType`）が含まれています。

**ブロードキャストのユースケースに関する注意**：オーディエンス内の一部のプロファイルにトークンがない場合、それらのプロファイルのみがライブアクティビティを受信できません。 トークンの問題を診断するために、オーディエンスからいくつかのプロファイルをサンプルします。 これは、リモート開始イベントにのみ適用され、更新イベントや終了イベントには適用されません。

#### 事前確認

* iOS アプリの要件：
   * iOS 16.1以降
   * `NSSupportsLiveActivities`が`Info.plist`で`YES`に設定されました
   * `ActivityAttributes`が正しく実装されました。
* モバイルSDKとの連携：
   * Adobe Experience Platform Mobile SDK（メッセージング SDK 5.11.0以降）
   * `Messaging.registerLiveActivities`が実装され、ライブアクティビティプッシュトークンで呼び出されました。

#### デバッグ手順

+++ &#x200B;1. Adobe Experience Platformにプロファイルが存在することを確認する

1. Journey Optimizerで、**Customer** `>` **Profiles**&#x200B;に移動します。
1. API リクエストの名前空間とID値を使用して検索します。
1. プロファイルが見つからない場合は、プロファイルが存在しないか、取り込みが完了していません。 プロファイルを作成するか、取り込みを待ってからライブアクティビティをトリガーします。
1. プロファイルが見つかった場合は、以下の手順2に進んで、プッシュトークンが同期されているかどうかを確認します。

+++

+++ &#x200B;2. ライブアクティビティプッシュトークンが同期されているかどうかを確認する

Assuranceを使用して、トークン登録を検証できます。

1. Assuranceでは、**イベント** リストから、イベント `eventType = "liveActivity.pushToStart"`をフィルタリングまたは検索します。
1. **イベント**&#x200B;を選択し、ペイロードを調べます。
1. トークン、appId、attributeTypeの値が存在することを確認します。
1. イベントが正常に送信されたかどうかを確認します。

Adobe Experience Platformのプロフィールもご覧いただけます。

1. Adobe Experience Platformで、**プロファイル**&#x200B;から「**イベント**」タブにアクセスします。
1. `liveActivity.pushToStart` イベントを検索します。
1. 偶数タイムスタンプとペイロードを確認します。

イベントが見つからない場合、モバイルアプリが`Messaging.registerLiveActivity`を正しく呼び出していません。 SDKとの連携を修正する必要があります。

+++

+++ &#x200B;3. プロファイルのトークン詳細の検証

1. **プロファイル**&#x200B;から、**属性** タブにアクセスします。
1. `liveActivityPushNotificationDetails`を探します。
1. トークン設定を確認します。

   ```json
   {
      "liveActivityPushNotificationDetails": [
      {
         "appId": "com.example.myapp",
         "token": "abc123def456...",
         "platform": "apns",
         "denylisted": false,
         "attributeType": "OrderTrackingAttributes",
         "identity": {}
      }
      ]
   }
   ```

**各フィールドを検証：**

| フィールド | 要件 | 共通イシュー |
|-|-|-|
| `appId` | IOS バンドル IDと完全に一致する必要があります | 開発バンドル IDと実稼動バンドル IDが一致しません |
| `attributeType` | Swift `ActivityAttributes`構造体名と完全に一致する必要があります（大文字と小文字を区別） | タイプミスまたは構造体名が正しくない |
| `platform` | `"apns"`または`"apnsSandbox"`である必要があります | 誤ったプラットフォーム値 |
| `denylisted` | `false`でなければなりません | 無効またはユーザーがオプトアウトとしてマークされたトークン |
| `token` | 有効なAPNs プッシュトークン | トークンの有効期限が切れているか、アプリが再インストールされています |

いずれかのフィールドが正しくない場合：モバイルアプリを更新し、`Messaging.registerLiveActivities`を使用して再登録し、5 ～ 10分待ってから、もう一度確認します。

`liveActivityPushNotificationDetails`が見つからない場合：トークンがまだ同期されていません。 Assuranceで`liveActivity.pushToStart` イベントを見てから5 ～ 10分待ちます。

+++

### シナリオ 2: キャンペーン設定とペイロードの問題 {#scenario-2-campaign-configuration-and-payload-issues}

[!BADGE 単一とブロードキャストの両方のユースケースに適用]{type=Positive}

有効なトークンを持つプロファイルは存在しますが、ライブアクティビティは表示されません。 これは、次の原因で発生する可能性があります。

* サーフェスまたはチャネルの設定が正しくありません。
* 誤ったAPI ペイロード構造。
* `content-state`と`attributes`はiOS `ActivityAttributes`の実装と一致しません。
* 古い`timestamp` （更新/終了に重要）。

**ブロードキャストのユースケースに関する注意**: キャンペーンは&#x200B;**API トリガーのマーケティング** （トランザクションではない）である必要があります。 ペイロードは、個別の`profile`ではなく`audience`を使用します。 ブロードキャスト固有のペイロード構造については[このセクション &#x200B;](#broadcast-config)を参照し、完全なAPI仕様については[Adobe Developer ドキュメント &#x200B;](https://developer.adobe.com/journey-optimizer-apis/references/messaging#operation/postIMAudienceMessageExecution)を参照してください。

#### 事前確認

* Campaignは&#x200B;**API トリガーのトランザクション** （単一）または&#x200B;**API トリガーのマーケティング** （ブロードキャスト）であり、**高スループット** オプションは&#x200B;**not**&#x200B;有効にする必要があります。ライブアクティビティと互換性がありません。
* プロファイルが存在し、上記の[&#x200B; シナリオ &#x200B;](#scenario-1-profile-or-push-token-issues)を使用してトークンが正しく同期されていることを確認します。

#### デバッグ手順

+++ &#x200B;1. キャンペーンサーフェス設定の確認

1. Journey Optimizerで&#x200B;**キャンペーン**&#x200B;を開き、**アクション** メニューに移動します。
1. **ライブアクティビティ設定**&#x200B;を確認します。 IOS アプリのサーフェスは、プロファイルの`liveActivityPushNotificationDetails`の`appId`と一致するバンドル IDで設定する必要があります。 例えば、プロファイルに`"appId": "com.example.myapp"`がある場合、サーフェスは同じアプリをターゲットにする必要があります。
1. キャンペーン設定の&#x200B;**アクティビティタイプ**&#x200B;が、プロファイルの`liveActivityPushNotificationDetails`の`attributeType`と正確に一致することを確認します。 例えば、プロファイルに`"attributeType": "FoodDeliveryLiveActivityAttributes"`がある場合、キャンペーンはこの同じアクティビティタイプを指定する必要があります。

+++

+++ &#x200B;2. API ペイロード構造の検証

API経由でキャンペーンを実行する場合は、ペイロードが正しい構造に従っていることを確認します。

**単一ペイロード：**

```json
{
   "campaignId": "your-campaign-id",
   "recipients": [{
      "type": "aep",
      "userId": "user@example.com",
      "namespace": "email",
      "context": {
      "requestPayload": {
         "aps": {
            "content-available": 1,
            "timestamp": 1756984054,
            "event": "start",
            "attributes-type": "FoodDeliveryLiveActivityAttributes",
            "content-state": { ... },
            "attributes": { ... }
         }
      }
      }
   }]
}
```

**一般的なペイロードの問題：**

| フィールド | 要件 | 共通イシュー |
|-|-|-|
| `attributes-type` | キャンペーンアクティビティタイプとプロファイル `attributeType`を一致させる必要があります | 不一致またはタイプミス |
| `campaignId` | アクティブなキャンペーン IDと一致する必要があります | キャンペーン IDが間違っているか見つかりません |
| `content-available` | `1`でなければなりません | 値が見つからないか間違っています |
| `event` | `"start"`、`"update"`または`"end"`である必要があります | 無効なイベントタイプ |
| `timestamp` | 常に最新のUnixのエポックタイムを秒単位にする必要があります | 古い/キャッシュされたタイムスタンプの使用 |
| `userId` / `namespace` | AEPの既存のプロファイルと一致する必要があります | プロファイル IDが一致しません |

**重要：常に最新のタイムスタンプを使用**

* `timestamp` フィールドは、各API呼び出しが行われた時点で&#x200B;**always**&#x200B;が&#x200B;**現在のUnix エポックタイム** （秒単位）である必要があります。
* これは、**すべてのイベントタイプ**&#x200B;に適用されます：`start`、`update`、**特に`end`**。
* **更新/終了リクエストに対する影響**：古いタイムスタンプまたは古いタイムスタンプを使用すると、更新リクエストと終了リクエストが失敗するか、デバイスによって無視されます。
* 以前のリクエストのタイムスタンプを&#x200B;**NOT**&#x200B;で再利用するか、キャッシュされた値を使用します。
* API呼び出しごとに新しいタイムスタンプを生成します。

**任意フィールド （すべてのイベントタイプ）:**

* `requestId`: トラッキング用の一意のID （推奨）。
* `alert`: `title`と`body`を持つオブジェクト （更新に注意を引くために便利です）。

**について`dismissal-date`:**

* Unix エポック時間（秒）を含むオプションフィールド。
* **`event: "end"`**&#x200B;の場合にのみ関連します。
* ライブアクティビティをデバイスから自動的に削除するタイミングを指定します。
* エンドイベントで指定しない場合、ユーザーがアクティビティを却下するまでライブアクティビティは表示されたままになります。
* 将来のタイムスタンプである必要があります（`timestamp`以降）。

+++

+++ &#x200B;3. ペイロードとiOSの実装の整合

API ペイロードがiOS アプリの`ActivityAttributes`実装と一致していることを確認します。 Adobe SDKの`LiveActivityAttributes` プロトコルは、iOS `ActivityAttributes`を拡張し、`liveActivityData` プロパティを必要とします。

**マッピングを検証：**

1. お使いの`ActivityAttributes`は、Adobeの`LiveActivityAttributes` プロトコルを実装する必要があります。 例：

   ```swift
   struct FoodDeliveryLiveActivityAttributes: LiveActivityAttributes {
      public struct ContentState: Codable, Hashable {
         var orderStatus: String
         var estimatedDeliveryTime: String
      }
   
      // Adobe SDK requirement
      var liveActivityData: LiveActivityData
   
      // Your custom attributes
      var restaurantName: String
   }
   ```

   **注意** `liveActivityData` フィールドはAdobe SDKで必要であり、すべての実装に含める必要があります。

1. API ペイロードは、iOS構造をミラーリングする必要があります。

   ```json
   {
      "aps": {
         "event": "start",
         "timestamp": 1756984054,
         "attributes-type": "FoodDeliveryLiveActivityAttributes",
         "content-state": {
         "orderStatus": "Preparing",
         "estimatedDeliveryTime": "20 mins"
      },
      "attributes": {
         "liveActivityData": {
         "liveActivityID": "order-12345"
         },
         "restaurantName": "Pizza Palace"
      }
      }
   }
   ```

**検証チェックリスト：**

* すべての`ContentState` フィールドを`content-state`に含めます（すべてのイベントタイプに必須）。
* 次を含むすべての`LiveActivityAttributes` フィールドを`attributes`に含めます（開始イベントのみ）。
   * `liveActivityData` （必須。通常は`liveActivityID`または類似の識別子が含まれます）
   * 構造体のすべてのカスタムフィールド
* フィールド名を正確に一致させます（大文字と小文字を区別します）。
* データタイプ（文字列、Int、Bool、ネストされたオブジェクト）を一致させます。
* ネストされたオブジェクト構造を保持します。

**よくある間違い：**

| 問題 | 影響 | 修正 |
|-------|--------|-----|
| 属性に`liveActivityData`がありません | ライブアクティビティは開始されません | 開始イベントに常に`liveActivityData` オブジェクトを含める |
| 開始イベントに必須フィールドがありません | ライブアクティビティは開始されません | IOS構造体からすべてのフィールドを追加する |
| 間違ったフィールド名（タイプミス/ケース） | フィールドが無視されたかエラーを解析しました | IOSのフィールド名と正確に一致 |
| 間違ったデータタイプ | 解析エラー | IOS データタイプの一致 |
| ネストされたオブジェクトがありません | 不完全なデータ | すべてのネストされた構造を含める |
| 更新/終了に`attributes`を含む | 不要だが、通常は無視される | 開始イベントに`attributes`のみを含める |
| 更新/終了時の古いタイムスタンプ | デバイスで更新/終了が無視されました | 常に新しいタイムスタンプを生成 |

詳細な例については、[&#x200B; ライブアクティビティページの作成](create-mobile-live.md)を参照してください。

+++

+++ &#x200B;4. Assuranceでテスト

Assuranceを使用して、APIの実行とペイロードの配信を検証します。

1. Assurance セッションを開きます。
1. API呼び出しを実行して、ライブアクティビティをトリガーします。
1. **イベントリスト**&#x200B;で、次を確認します。
   * キャンペーン実行イベント：
   * ライブアクティビティ配信イベント：
   * ペイロード検証エラーイベント。
1. イベントペイロードを確認して、以下を確認します。
   * ペイロードが正しく処理されました。
   * 検証エラーは発生しませんでした。
   * ライブアクティビティがAPNに送信されました。

+++

### シナリオ 3：配信エラーとエラー分析 {#scenario-3-delivery-failures-and-error-analysis}

[!BADGE 単一とブロードキャストの両方のユースケースに適用]{type=Positive}

このシナリオでは、以前のすべてのチェックに合格しました。

* プロファイルは[有効なライブアクティビティプッシュトークン &#x200B;](#scenario-1-profile-or-push-token-issues)で存在します
* Campaignは適切なペイロードで正しく[設定されています](#scenario-2-campaign-configuration-and-payload-issues)
* [更新トークンが同期されます](#scenario-4-live-activity-update-token-not-synced) （更新/終了イベントの場合、単一ユースケースのみ）

ただし、ライブアクティビティは、期待どおりに表示、更新、終了されません。 この問題は、Adobe配信システムレベルまたはプッシュ通知サービスプロバイダー（APN）で発生する可能性があります。

**ブロードキャストのユースケースに関するメモ**：すべてのオーディエンスメンバーに関する指標をレポートに表示します。 成功するプロファイルもあれば、失敗するプロファイルもあります。

**事前確認**

* **検証済みの以前のシナリオ：**
   * 正しい`liveActivityPushNotificationDetails`のプロファイルが存在します
   * キャンペーンサーフェスとアクティビティタイプが正しい
   * API ペイロードは現在のタイムスタンプで有効です
   * 更新トークンが同期されます（更新/終了イベントの場合）

* **API呼び出しが確認されました：**

   * API呼び出しでHTTP 200 （成功）が返されました
   * キャンペーン IDと受信者の詳細が正しい

#### デバッグ手順

+++ &#x200B;1. キャンペーンレポートの確認

1. **ライブアクティビティキャンペーン**&#x200B;に移動します。
1. 「**レポート**」ボタンをクリックします。
1. 「**すべての時間レポートを表示**」を選択します。
1. 次のセクションを確認します。

   1. 配信の成功について理解するには、**送信統計**&#x200B;指標を確認してください。

      | 指標 | 意味 | ビジネスの成長を促進するための |
      |-|-|-|
      | ターゲティング | オーディエンスに適格なプロファイルの数 | テストプロファイルを含める必要があります |
      | 送信数 | 試行されたプッシュ通知の合計 | API呼び出しと一致する必要があります |
      | 配信済み | デバイスへの正常な配信 | 送信数と比較して成功率を確認する |
      | 送信エラー | 送信できなかったプッシュ通知 | 大きい数値 |
      | 除外を送信 | Adobe Journey Optimizerによって除外されたプロファイル | プロファイルが除外されたかどうかを確認する |

   1. 送信エラーが0を超える場合は、**エラーの理由** テーブルで特定のエラーコードとメッセージを確認します。

      | 共通エラー | 意味 | 解決策 |
      |-|-|-|
      | 無効なトークン | プッシュトークンが無効または期限切れです | デバイスからのライブアクティビティトークンの再登録 |
      | トークンが見つかりません | プロファイルに関連付けられた有効なトークンがありません | `liveActivityPushNotificationDetails`が存在することを確認 |
      | APNsが拒否されました | Apple プッシュ通知サービスはプッシュを拒否しました | APNs証明書、バンドル ID、環境の確認 |
      | ネットワークタイムアウト | APNに到達できない | 一時的な問題。API呼び出しを再試行してください |

   1. **除外を送信** > 0の場合、**除外された理由** テーブルを確認します。

      | 共通の除外 | 意味 | 解決策 |
      |-|-|-|
      | プロファイルがオプトアウトされました | ユーザーが通知をオプトアウトしました | プロファイルの同意ステータスを確認 |
      | トークンをブロックリストに加える | 無効としてマークされたトークン | トークンの再登録またはブロックリストステータスの確認 |
      | プロファイルは対象外です | プロファイルがキャンペーン条件を満たしていません | キャンペーンオーディエンスのルールの確認 |

詳しくは、[&#x200B; ライブアクティビティキャンペーンレポートページ &#x200B;](../reports/campaign-global-report-cja-activity.md)を参照してください。

+++

+++ &#x200B;2. プロファイル内のメッセージフィードバックイベントの確認

1. Journey Optimizerの&#x200B;**Customer** > **Profiles**&#x200B;に移動します。
1. プロファイルを検索して開きます。
1. 「**イベント**」タブを選択します。
1. `eventType = "message.feedback"`のイベントをフィルタリングまたは検索します。
1. ライブアクティビティの`liveActivityID`と`event`の種類に一致するフィードバックイベントを探します。
1. 次のキーフィールドを確認します。

   | フィールド | 使用可能な値 | 意味 |
   |---|---|---|
   | `feedbackStatus` | `sent`, `error`, `denylist` | サービスプロバイダーからの配信の結果 |
   | `serviceProvider` | `apns/apnsSandbox` | IOS Live アクティビティのAPNであるべき |
   | `errorCode` | 数値コードまたは`null` | 失敗した場合のAPNs固有のエラーコード |
   | `errorMessage` | エラーの説明または`null` | 人間が判読可能なエラーメッセージ |

1. **場合`feedbackStatus: "error"`:**
   * 特定のAPNs エラーについては、`errorCode`と`errorMessage`を確認してください
   * APNの一般的なエラーには、期限切れのトークン、無効な証明書、間違ったバンドル IDなどがあります

1. **フィードバックイベントが見つからない場合：**
   * プッシュ通知が試行されていない可能性があります
   * 上記の手順1で説明したように、キャンペーンレポートでプロファイルが除外されたかどうかを確認します。

+++

+++ &#x200B;3. AssuranceのAPNへのライブアクティビティ配信を確認する

1. Assurance セッションを開きます。API呼び出し中にアクティブにする必要があります。
1. API呼び出しを実行します（開始、更新、終了）。
1. **イベントリスト**&#x200B;で、ライブアクティビティ配信イベントを探します。
1. APN プッシュ配信に関連するイベントを検索します。
1. 次のインジケーターを確認します。
   * **APNsへのプッシュリクエスト**: AdobeがAppleのサーバーにプッシュを送信したことを確認します
   * **APNs応答**: APNがプッシュを承認したか拒否したかを示します
   * **配信ステータス**：成功または失敗の兆候
1. 問題が見つかった場合は、次の一般的なAPNの配信の問題を参照してください。

   | 問題 | Assuranceの症状 | 解決策 |
   |-|-|-|
   | APNs証明書の有効期限 | 認証エラー | 新しいAPNs証明書の更新とアップロード |
   | 環境が正しくない（開発環境と実稼動環境） | トークンの不一致エラー | 証明書がアプリのビルドタイプに一致することを確認する |
   | バンドル IDの不一致 | 無効なバンドル ID | 証明書バンドル IDがアプリと一致することを確認する |
   | トークン期限切れ | APNsからのInvalidToken エラー | ライブアクティビティトークンの再登録 |
   | レート制限 | リクエストが多すぎます | API呼び出し頻度の削減 |

+++

+++ &#x200B;4. 追加の診断チェックに進みます

1. Campaign レポートのライブアクティビティライフサイクル指標を確認します。

   キャンペーンレポートで、**ライブアクティビティライフサイクル** セクションを確認します。

   | 指標 | 確認すべきこと |
   |-|-|
   | リモートスタート | API トリガー開始回数を表示する必要があります |
   | アップデート | 更新イベント数を表示する必要があります |
   | 終了 | 終了イベント数を表示する必要があります |
   | 合計数 | ライブアクティビティイベントの全体的な量 |

   これらの指標が0であるか、API呼び出しに一致しない場合は、AdobeとAPNの間に配信の問題があります。

1. Adobeが正常に配信されたが、デバイスにライブアクティビティが表示されない場合：

   * IOS デバイスログでライブアクティビティエラーを確認します。
   * アプリが前景または背景にあることを確認します（終了しません）。
   * デバイスにネットワーク接続があることを確認します。
   * 複数のデバイスをテストして、デバイス固有の問題を除外します。
   * IOSのバージョンが16.1以降であることを確認します。

+++

+++ &#x200B;5. Adobe サポートへのエスカレーション

すべての手順を完了しても問題が解決しない場合は、Adobe カスタマーサポートにお問い合わせください。

**必要な情報：**

* キャンペーン ID と名前
* プロファイルの名前空間とID
* API ペイロードからの`liveActivityID`
* API呼び出しのタイムスタンプ
* スクリーンショット：
* キャンペーンレポート（送信統計、エラー理由、除外された理由）
* プロファイルイベント （`liveActivity.updateToken`, `message.feedback`）
* 配信イベントを示すAssuranceのセッション
* 完全なAPI リクエストペイロード
* APNs証明書の詳細（有効期限、環境、バンドル ID）

+++

## 単一に固有のシナリオ

### シナリオ 4: ライブアクティビティ更新トークンが同期されない {#scenario-4-live-activity-update-token-not-synced}

ライブアクティビティはデバイスで正常に開始されますが、後続の`update`または`end` API呼び出し（HTTP 200を返します）はライブアクティビティの更新または却下に失敗します。 これは、**ライブアクティビティ更新トークン**&#x200B;がAdobeのシステムに正しく同期されていない場合に発生します。

**更新トークンについて**

デバイスでライブアクティビティが開始されると、iOSは、その特定のライブアクティビティインスタンスに対して一意の更新トークンを生成します。 このトークンは、次の場合に必要です。

* ライブアクティビティへの更新の送信
* ライブアクティビティをリモートで終了する

各ライブアクティビティインスタンスには、それぞれ固有の更新トークンがあります。 Adobeでは、更新イベントと終了イベントを配信するためにこのトークンが必要です。

**期待される動作**

更新イベントと終了イベントを機能させるには、次の操作が必要です。

1. デバイスでライブアクティビティが正常に開始されます。
1. デバイスは、そのライブアクティビティインスタンスの更新トークンを生成します。
1. Mobile SDKは、更新トークンをキャプチャし、Adobeに送信します。
1. 更新トークンは同期され、Adobeのシステムに保存されます。
1. 更新/終了に対する後続のAPI呼び出しは、このトークンを配信に使用します。

**プリチェック：**

* **ユーザー権限**: デバイスでライブアクティビティが初めて開始されると、iOSにシステムプロンプト「[ アプリ名]でライブアクティビティの更新を提供しますか？」が表示されます。 更新トークンを生成して同期するには、ユーザー&#x200B;**が「許可」をタップする必要があります**。 ユーザーが「許可しない」をタップした場合、更新トークンは作成されず、更新/終了リクエストは失敗します。 これはアプリごとに1回限りの権限です。
* **プロファイルとキャンペーンの検証**: プロファイル、トークン、キャンペーン設定が正しいことを確認するために、[&#x200B; シナリオ 1](#scenario-1-profile-or-push-token-issues)と[&#x200B; シナリオ 2](#scenario-2-campaign-configuration-and-payload-issues)のチェックを完了します。

#### デバッグ手順

+++ Assuranceで更新トークンの同期を確認する

1. Assurance セッションを開きます。
1. ライブアクティビティがデバイスで開始されたときに、セッションがアクティブであることを確認します。
1. `eventType = "liveActivity.updateToken"`のイベントをフィルタリングまたは検索します。
1. イベントを選択し、ペイロードを調べます。

   * `token` フィールドに有効な更新トークン文字列が含まれていることを確認します。
   * `liveActivityID`がライブアクティビティインスタンスと一致することを確認します。
   * `activityType`が`attributes-type`と一致することを確認します。

1. イベントが見つからない場合：

   * 更新トークンは、SDKによって生成またはキャプチャされませんでした。
   * ユーザーがライブアクティビティ権限を付与したかどうかを確認します。
   * 実際にデバイスで正常に開始されたことを確認します。
   * 更新トークンを取得するために、モバイル SDKが適切に統合されていることを確認します。

1. イベントが見つかった場合は、手順2に進みます。

+++

+++ &#x200B;2. プロファイルイベントでの更新トークンの検証

1. Journey Optimizerの&#x200B;**Customer** > **Profiles**&#x200B;に移動します。
1. プロファイルを検索して開きます。
1. 「**イベント**」タブを選択します。
1. `liveActivity.updateToken` イベントを探します。
1. イベントの詳細を確認します。

   * タイムスタンプが最新であることを確認します（ライブアクティビティが開始されたときに一致）。
   * `token`と`liveActivityID`が存在することを確認します。
   * `activityType`が正しいことを確認します。

1. プロファイルにイベントが見つからない場合：

   * 更新トークンイベントはまだプロファイルに取り込まれていない可能性があります。
   * 5～10分待って、もう一度確認してください。
   * 15分経過しても見つからない場合は、イベント取り込みの問題が発生している可能性があります。

1. イベントが見つかった場合、更新トークンは同期されています。 手順3に進みます。

+++

+++ &#x200B;3. Assuranceのライブアクティビティ配信イベントの確認

1. Assurance セッションで、更新または終了API呼び出しを実行します。
1. **イベントリスト**&#x200B;で、ライブアクティビティ配信イベント（APNs プッシュイベント）を探します。
1. 次を示すイベントを確認します。
   * プッシュ通知がAPNに送信されました。
   * APNからの応答（成功またはエラー）。
   * 配達確認。
1. APNs配信イベントが存在する場合：プッシュ通知が送信されました。 それでもデバイスが更新されない場合、問題はデバイス側にある可能性があります（アプリがプッシュやネットワークの問題を処理しない場合など）。
1. APNs配信イベントが見つからない場合：更新トークンが正しく保存されていないか、Adobe システムのプロファイルに関連付けられていない可能性があります。
1. エラーイベントが存在する場合：特定のエラーの理由（無効なトークン、APNが拒否されたなど）について、エラーの詳細を調べます。

+++

### シナリオ 5: APIを介した実行ステータスの確認 {#scenario-5-checking-execution-status-via-the-api}

[!BADGE 単一（1:1）のユースケースにのみ適用]{type=Informative}

単一のLive アクティビティをトリガーした後、**GET Message Execution API**&#x200B;は、実行の現在の状態を返します。 このインターフェイスを使用すると、フィードバックイベントがデータセットに表示されるのを待たずに、実行がキューに入っているか、進行中、完了しているか、失敗しているかを確認できます。

`executionId`は、トリガー応答で返されたメッセージ IDです。 単一の実行の場合は、先頭に`HUOC-`が付きます。

#### エンドポイントとリクエスト例

**エンドポイント**: `GET https://cjm.adobe.io/imp/message/executions/{executionId}`

```bash
curl --location 'https://cjm.adobe.io/imp/message/executions/HUOC-123456' \
  --header 'x-gw-ims-org-id: <IMS_ORG_ID>' \
  --header 'Authorization: Bearer <ACCESS_TOKEN>' \
  --header 'x-sandbox-name: <SANDBOX_NAME>' \
  --header 'x-sandbox-id: <SANDBOX_UUID>' \
  --header 'x-api-key: <API_KEY>'
```

#### HTTP応答コード

| コード | 意味 |
|------|---------|
| 200 OK | 実行が見つかり、正常に返されました |
| 401未認証 | ベアラートークンが見つからないか無効です |
| 403禁止 | 有効なトークンだが権限が不十分 |
| 404が見つかりません | 実行IDが存在しません |

#### 実行ステータス値

200件の応答の`status` フィールドは、実行の進行状況を示します。

| ステータス | 説明 |
|--------|-------------|
| `PENDING` | 実行はキューに入れられていますが、まだ開始されていません |
| `INPROGRESS` | 実行は処理中です |
| `COMPLETED` | 実行が正常に完了しました |
| `FAILED` | 実行でエラーが発生しました |

200件の応答では、`executionType` （`unitary`または`batch`）、`executionRunMode` （`default`または`test`）、メタデータ （`campaignId`、`journeyId`、`batchInstanceId`、アセット情報）を含む`source` ブロックも返されます。このブロックは、実行をトリガーキャンペーンまたはジャーニーに関連付けます。

## 放送固有のシナリオ

### シナリオ 6：ブロードキャストキャンペーンの設定とペイロードの問題{#broadcast-config}

[!BADGE &#x200B; ブロードキャストのユースケースにのみ適用]{type=Informative}

この節では、ブロードキャストライブアクティビティに固有のトラブルシューティングのシナリオについて説明します。これらのシナリオでは、単一キャンペーンとは異なるデバッグアプローチが必要です。

プロファイルに有効なトークンが含まれていても、ライブアクティビティがオーディエンスメンバーに表示されない、更新されない、または想定どおりに動作しない場合、問題は通常、次のいずれかに起因します。

* キャンペーンがAPI トリガーマーケティングとして設定されていません。
* API ペイロードで正しくないブロードキャスト構造が使用されています（`audience`または`input-push-channel`がありません）。
* `content-state`と`attributes` フィールドがiOS `ActivityAttributes`の実装と一致しません。
* Apple Developer Portalで`input-push-channel`が正しく作成されませんでした。

このトラブルシューティングのシナリオは、ブロードキャストキャンペーンのすべてのライブアクティビティイベント（`start`、`update`、および`end`）に適用されます。

**プリチェック：**

* **キャンペーンタイプ**:
   * キャンペーンがAPI トリガーマーケティングとして作成されていることを確認します（ブロードキャスト/オーディエンスベースのキャンペーンに必要）。
   * キャンペーン設定でオーディエンスが定義されていることを確認します。
* **プロファイルとトークンの検証**：オーディエンスから複数のプロファイルをサンプルして、有効な`liveActivityPushNotificationDetails`を持っていることを確認します。 詳細な検証手順については、[&#x200B; シナリオ 1](#scenario-1-profile-or-push-token-issues)に従ってください。

#### デバッグ手順

+++ &#x200B;1. キャンペーンオーディエンス設定の確認

1. Journey Optimizerで&#x200B;**API Triggered Marketing Campaign**&#x200B;を開きます。
1. 「**オーディエンス**」セクションに移動して、次を確認します。
   * キャンペーン用にオーディエンスが選択されます。
   * オーディエンス IDは、API ペイロードで使用されるIDと一致します。
   * オーディエンスには、想定されるプロファイルが含まれています。
1. 「**アクション**」セクションに移動します。
1. **ライブアクティビティ設定**&#x200B;を確認します。
   * IOS アプリの設定は、正しいバンドル IDを使用して設定する必要があります。
   * アクティビティの種類は、API ペイロードの`attributes-type`と一致する必要があります。 例えば、ペイロードに`"attributes-type": "AirplaneTrackingAttributes"`が含まれている場合、キャンペーンはこの同じアクティビティタイプを指定する必要があります。

+++

+++ &#x200B;2. ブロードキャスト API ペイロード構造の検証

ブロードキャストペイロードの構造は、単一キャンペーンとは異なります。 ペイロードが正しいブロードキャスト形式に従っていることを確認します。

**ブロードキャストの必須フィールド：**

```json
{
   "campaignId": "878a11d4-b519-47bd-8313-fecfee19857b",
   "audience": {
      "id": "8c3dbdea-2957-401f-acf0-3966fba1601e"
   },
   "context": {
      "requestPayload": {
      "aps": {
         "input-push-channel": "FEt0NgvLEfEAAOqA6AXdIQ==",
         "content-available": 1,
         "timestamp": 1771829292,
         "event": "update",
         "attributes-type": "AirplaneTrackingAttributes",
         "content-state": { ... },
         "attributes": { ... }
      }
      }
   }
}
```

**一般的なペイロードの問題：**

| フィールド | 要件 | 共通イシュー |
|-|-|-|
| `campaignId` | アクティブなマーケティングキャンペーン IDと一致する必要があります | 間違ったキャンペーン IDまたはトランザクションキャンペーンの使用 |
| `audience.id` | AEPの既存オーディエンスと一致する必要があります | 間違ったオーディエンス IDまたはオーディエンスが存在しない |
| `input-push-channel` | ブロードキャストに必須 – このブロードキャストインスタンスの一意の識別子 | `liveActivityData`の`channelID`が見つからないか、一致しません |
| `timestamp` | 常に最新のUnixのエポックタイムを秒単位にする必要があります | 古い/キャッシュされたタイムスタンプの使用 |
| `event` | `"start"`、`"update"`または`"end"`である必要があります | 無効なイベントタイプ |
| `attributes-type` | キャンペーンアクティビティタイプに一致する必要があります | 不一致またはタイプミス |
| `content-available` | `1`でなければなりません | 値が見つからないか間違っています |

**重要なブロードキャスト固有のフィールド：**

* **`input-push-channel`**:
   * すべてのブロードキャストライブアクティビティに必要です。
   * この特定のブロードキャストインスタンスの一意の識別子として機能します。
   * オーディエンス内のすべてのプロファイルは、このチャネルにリンクされたライブアクティビティを受け取ります。
   * `liveActivityData.channelID`の`channelID`と一致する必要があります（手順3を参照）。
   * クライアントがApple Developer Portal上の`appID`用に作成する必要があります。
   * 特定の`appID`用に作成されたチャネルのみを、そのアプリのライブアクティビティのブロードキャストに使用できます。

* **`audience.id`**:
   * Adobe Experience Platformで作成された有効なオーディエンスセグメントを参照する必要があります。
   * このオーディエンス内のすべてのプロファイルは、ライブアクティビティを対象としています。
   * オーディエンスをアクティブ化し、有効な`liveActivityPushNotificationDetails`のプロファイルを含める必要があります。

**常に最新のタイムスタンプを使用：**

* `timestamp` フィールドは、常にAPI呼び出しごとに現在のUnix エポック時間（秒単位）である必要があります。
* この要件は、すべてのイベントタイプ（`start`、`update`、および`end`）に適用されます。
* **更新/終了に重要**：古いタイムスタンプを使用すると、更新リクエストと終了リクエストが失敗します。
* ブロードキャスト API呼び出しごとに新しいタイムスタンプを生成します。

**任意フィールド：**

* `dismissal-date`：自動却下のUnixのエポックタイム（`end` イベントにのみ関連）
* `alert`：通知用に`title`と`body`を含むオブジェクト

完全なAPI仕様については、[Adobe Journey Optimizer Messaging API ドキュメント &#x200B;](https://developer.adobe.com/journey-optimizer-apis/references/messaging)を参照してください。

+++

+++ &#x200B;3. IOSを活用して、content-state、attributes、input-push-channelの連携を強化

ペイロードフィールドがiOS アプリの`ActivityAttributes`実装と一致していること、および`input-push-channel`が`liveActivityData`の`channelID`と一致していることを確認してください。

1. IOS ActivityAttributesの定義を確認します。

カスタム `ActivityAttributes`構造体は、Adobeの`LiveActivityAttributes` プロトコルを実装する必要があります。

```swift
struct AirplaneTrackingAttributes: LiveActivityAttributes {
   public struct ContentState: Codable, Hashable {
      var journeyProgress: Int
   }
   
   // Adobe SDK requirement
   var liveActivityData: LiveActivityData
   
   // Your custom attributes
   var arrivalAirport: String
   var departureAirport: String
   var arrivalTerminal: String
}
```

1. IOS フィールドをブロードキャスト API ペイロードにマッピングします。

すべてのイベントに対して、`attributes`と`content-state`の両方を含めます。

```json
      {
      "aps": {
         "input-push-channel": "FEt0NgvLEfEAAOqA6AXdIQ==",
         "event": "start",
         "timestamp": 1771829292,
         "attributes-type": "AirplaneTrackingAttributes",
         "content-state": {
         "journeyProgress": 0
         },
         "attributes": {
         "arrivalAirport": "DEL",
         "departureAirport": "MUM",
         "arrivalTerminal": "T1",
         "liveActivityData": {
            "channelID": "FEt0NgvLEfEAAOqA6AXdIQ=="
         }
         }
      }
      }
```

**重要：`input-push-channel`は`channelID`**&#x200B;と一致する必要があります

* `aps`のルートの`input-push-channel`値は、`liveActivityData`の`channelID`と完全に一致する必要があります。
* 上記の例では、両方の値は`"FEt0NgvLEfEAAOqA6AXdIQ=="`です。
* このマッチングにより、ブロードキャストインスタンスがライブアクティビティデータにリンクされます。
* 不一致が発生すると、配信エラーが発生します。

**主要な検証ポイント：**

* すべてのイベントタイプに対して、`content-state`にすべての`ContentState` フィールドを含めます。
* 開始イベントに対してのみ、`attributes`にすべてのカスタム `LiveActivityAttributes` フィールドを含めます。
* 開始イベントの場合、`liveActivityData.channelID`は`input-push-channel`と一致する必要があります。
* フィールド名は大文字と小文字が区別され、正確に一致する必要があります。
* データ型は一致する必要があります（String、Int、Bool、ネストされたオブジェクトなど）。
* 更新/終了イベントの場合は、元の開始イベントと同じ`input-push-channel`を使用します。

**よくある間違い：**

| 問題 | 影響 | 修正 |
|-|-|-|
| `input-push-channel`がありません | ブロードキャストが機能しない | 各ブロードキャストに一意のチャネル IDを追加する |
| `input-push-channel`が`channelID`と一致しません | ライブアクティビティは開始されません | 両方の値が同じであることを確認します |
| 更新/終了に対して異なる`input-push-channel` | 更新/終了はライブアクティビティに到達しません | ライフサイクル全体で同じチャネル IDを使用 |
| `liveActivityData.channelID`がありません | ライブアクティビティはブロードキャストにリンクされません | 開始イベントの属性に`channelID`を含める |
| 開始イベントに必須フィールドがありません | ライブアクティビティは開始されません | IOS構造体からすべてのフィールドを追加する |
| 間違ったフィールド名（タイプミス/ケース） | フィールドが無視されたかエラーを解析しました | IOSのフィールド名と正確に一致 |
| 更新/終了時の古いタイムスタンプ | デバイスが更新/終了を無視 | 常に新しいタイムスタンプを生成 |

+++

+++ &#x200B;4. Assuranceでテスト

Assuranceを使用して、APIの実行とペイロードの配信を検証します。

1. オーディエンスの一部であるテストデバイスでAssurance セッションを開きます。
1. ブロードキャスト API呼び出しを実行します。
1. **イベントリスト**&#x200B;で、次を探します。
   * キャンペーン実行イベント：
   * ライブアクティビティ配信イベント：
   * ペイロード検証エラーを示すエラーイベント。
1. イベントペイロードを調べて確認します。
   * ペイロードが正しく処理されました。
   * `input-push-channel`が存在します。
   * 検証エラーは発生しませんでした。
   * ライブアクティビティは、オーディエンスメンバー向けにAPNに送信されました。

+++

### シナリオ 7: プロファイルがオーディエンス内にないか、古いオーディエンススナップショットです {#scenario-7-profile-not-in-audience-or-stale-audience-snapshot}

このシナリオでは、キャンペーンとペイロードは正しく設定されますが、特定のプロファイルはライブアクティビティを受信しません。 これは通常、次の場合に発生します。

* プロファイルは、キャンペーンにリンクされたオーディエンスのメンバーではありません。
* オーディエンスはバッチオーディエンスで、プロファイルデータの古いスナップショットが含まれています。
* プロファイルのライブアクティビティトークンは最近追加されましたが、オーディエンススナップショットにはまだ反映されていません。

このトラブルシューティングのシナリオは、オーディエンスベースのターゲティングを使用するブロードキャストキャンペーンに特に適用されます。

**オーディエンスの評価について**

Adobe Experience Platformでは、プロファイルの更新がオーディエンスに反映されるタイミングを決定するために、様々なオーディエンス評価方法を使用します。

| メソッド | 評価頻度 | データの鮮度 | 最適な用途 |
|-|-|-|--|
| バッチ | 1日1回（予定） | 最大で24時間古くなる可能性があります | 多数のオーディエンスに対応（時間的制約なし） |
| ストリーミング | リアルタイム（プロファイル変更時） | プロファイルを更新するためにほぼリアルタイム | 時間的制約があり、プロファイルの更新が必要 |

**プリチェック：**

* **キャンペーンとペイロードの検証**:
   * [このシナリオ &#x200B;](#broadcast-config)のチェックを完了して、キャンペーンとペイロードが正しいことを確認します。
   * API ペイロードの`audience.id`がキャンペーン設定と一致することを確認します。
* **プロファイルが存在します**：有効な`liveActivityPushNotificationDetails`のプロファイルがAEPに存在することを確認します。

#### デバッグ手順

+++ &#x200B;1. プロファイルがオーディエンスにあることを確認

まず、ライブアクティビティを受け取るプロファイルが実際にオーディエンスの一部であるかどうかを確認します。

1. Adobe Experience Platformの&#x200B;**Audiences**&#x200B;に移動します。
1. キャンペーンの`audience.id`を使用してオーディエンスを検索し、開きます。
1. **参照**&#x200B;または&#x200B;**サンプルプロファイル**&#x200B;をクリックして、オーディエンスメンバーを表示します。
1. 名前空間とID値を使用して、テストプロファイルを検索します。
1. **オーディエンスにプロファイルが見つからない場合：**
   * プロファイルがオーディエンスの基準またはセグメントルールを満たしていません。
   * オーディエンス定義を確認して、メンバーシップ要件を理解します。
   * プロファイルデータまたはオーディエンス定義を更新して、プロファイルを含めます。
   * オーディエンスの評価が完了するのを待ちます（手順2を参照）。
1. **オーディエンスにプロファイルが見つかった場合：** ステップ 2に進んで、データの鮮度を確認します。

+++

+++ &#x200B;2. オーディエンスの評価の種類とスケジュールを確認する

オーディエンスがバッチ評価とストリーミング評価のどちらを使用しているかを特定し、データの鮮度を判断します。

1. **オーディエンスの詳細** ページで、**評価方法**&#x200B;を確認します。
   * **バッチ**：毎日1回、スケジュールに従って評価されます。
   * **ストリーミング**: プロファイルの更新時にリアルタイムで評価されます。
   * **Edge**: リアルタイムでエッジの場所で評価されました。

評価方法に基づく適切なトラブルシューティング手順に従います。

**オーディエンスがバッチ評価を使用している場合：**

1. **バッチオーディエンスの制限について：**
   * バッチオーディエンスは、1日に1回（通常は毎晩）評価されます。
   * オーディエンスのスナップショットは、最大で24時間前になる場合があります。
   * プロファイルが最近登録したライブアクティビティトークンの場合、これらのトークンは現在のスナップショットにない可能性があります。
   * プロファイルの更新は、次のバッチ評価まで反映されません。

1. **最後の評価が発生した際の確認：**
   * オーディエンスの詳細で、**最終評価** タイムスタンプを探します。
   * プロファイルの`liveActivityPushNotificationDetails`がこのタイムスタンプの後に更新された場合、オーディエンスには古いデータがあります。

1. **古いデータを解決：**
   1. **オプション 1：スケジュールされたバッチ評価を待つ**
      * 次のバッチ評価には、更新されたプロファイルデータが含まれます。
      * これは1日に1回自動的に行われます。
      * 緊急性の低いシナリオに最適：

   1. **オプション 2: オンデマンドのオーディエンス評価のトリガー**
      1. AEPの&#x200B;**Audiences**&#x200B;に移動します。
      1. オーディエンスを選択します。
      1. **今すぐ評価**&#x200B;または&#x200B;**オンデマンドでアクティベート**&#x200B;をクリックします。
      1. 評価が完了するまで待ちます（オーディエンスサイズによっては数分から数時間かかる場合があります）。
      1. プロファイルがオーディエンススナップショットのデータを更新したことを確認します。
      1. ブロードキャスト API呼び出しを再試行します。

**オーディエンスがストリーミング評価を使用している場合：**

1. **ストリーミングオーディエンスの動作について：**
   * ストリーミングオーディエンスは、プロファイルの更新が発生したときにリアルタイムで評価されます。
   * **新しいプロファイル**: セグメントの条件を満たす場合は、作成後すぐに選定します。
   * **更新されたプロファイル**：更新された直後に選定または選定を解除しました。
   * **既存の変更されていないプロファイル**：更新が発生しない限り、再評価されません。

1. **問題の特定：**
   * プロファイルが既に存在し、セグメント条件を満たしていても、そのプロファイルに更新が発生しない場合は、新しく作成されたストリーミングオーディエンスに追加できない可能性があります。
   * プロファイルは、トリガーの再評価に対する更新（属性の変更）を受け取る必要があります。

1. **問題の解決：**
   * **新しいプロファイルの場合**：条件が満たされると、自動的に選定されます。 行動は必要ありません。
   * **最近更新されていない既存のプロファイルの場合：**
      * プロファイルのマイナーな更新（例：タイムスタンプフィールドの更新）を行います。
      * ストリーミング評価がトリガーされ、プロファイルがオーディエンスに追加されます。
      * 代替案：既存のプロファイルにバッチオーディエンスまたはエッジオーディエンスを使用します。

+++

## 詳細設定：データセットのクエリによるデバッグ {#advanced-debugging-via-dataset-queries}

>[!BEGINSHADEBOX]

**Audience**：開発者およびデータエンジニア。 Adobe Experience Platform Query Service経由でJourney Optimizer データセットにSQL アクセスする必要があります。

**使用するタイミング**: Assuranceは、アクティブなセッション中に接続されたテストデバイスに限定されます。 データセットクエリを使用して、本番環境のエンドユーザーが報告した問題を調査したり、ファクトの後に配信履歴を監査したりできます。 このデータセットは、Assurance プラグインと同じライフサイクルおよび障害情報を公開します。

>[!ENDSHADEBOX]

### データセットの検索

1. Journey Optimizerで、**Data Management** `>` **Datasets**&#x200B;に移動します。

1. 「**システムデータセットを表示**」トグルを有効にし、**AJO メッセージフィードバックイベントデータセット**&#x200B;を開きます。

詳細ページに表示されているテーブル名を正確に記録します。 以下のクエリでは、`ajo_message_feedback_event_dataset`を使用しています。異なる場合は、実際のテーブル名に置き換えてください。

### ライブアクティビティ IDによるクエリ

これは、ライブアクティビティ ID （注文UUIDや出荷追跡IDなど）がわかっていて、すべてのフィードバックイベントをライフサイクル全体で関連付ける場合に使用します。

```sql
SELECT
  timestamp,
  identitymap,
  _experience.customerJourneyManagement
    .messageDeliveryfeedback.feedbackStatus AS status,
  _experience.customerJourneyManagement
    .messageDeliveryfeedback.messageFailure.reason AS failure_reason,
  _experience.customerJourneyManagement
    .pushChannelContext.liveActivity.event AS la_event,
  _experience.customerJourneyManagement
    .messageExecution.campaignID AS campaign_id,
  _experience.customerJourneyManagement
    .messageExecution.batchInstanceID AS batch_id,
  _id
FROM ajo_message_feedback_event_dataset
WHERE
  _experience.customerJourneyManagement
    .pushChannelContext.liveActivity.liveActivityID
    = '<YOUR_LIVE_ACTIVITY_ID>'
  AND eventtype = 'message.feedback'
ORDER BY timestamp ASC
```

### ECIDによるクエリ

影響を受けるプロファイルのECIDがわかっている場合に使用します。 `<YOUR_ECID>`をプロファイルから取得したECID値に置き換えます。

```sql
SELECT
  timestamp,
  _experience.customerJourneyManagement
    .messageDeliveryfeedback.feedbackStatus AS status,
  _experience.customerJourneyManagement
    .messageDeliveryfeedback.messageFailure.reason AS failure_reason,
  _experience.customerJourneyManagement
    .pushChannelContext.liveActivity.event AS la_event,
  _experience.customerJourneyManagement
    .pushChannelContext.liveActivity.liveActivityID AS la_id,
  _experience.customerJourneyManagement
    .messageExecution.campaignID AS campaign_id,
  _id
FROM ajo_message_feedback_event_dataset
WHERE
  identityMap['ECID'][0].id = '<YOUR_ECID>'
  AND eventtype = 'message.feedback'
ORDER BY timestamp ASC
```

>[!NOTE]
>
> `identityMap`は構造化MAP タイプであり、文字列ではありません。 上記の配列と構造体アクセサーの構文を使用します。 `LIKE`などの文字列関数は、`DATATYPE_MISMATCH` エラーを返します。
>
></br>
>&gt; メッセージフィードバックイベントデータセットは、「identityMap」にECIDのみを格納します。 影響を受けるプロファイルがECIDではなくカスタム名前空間で識別される場合は、最初にECIDを解決します。AEPで&#x200B;**Profiles**&#x200B;に移動し、カスタム名前空間とID値を使用してプロファイルを検索し、プロファイルのIDの詳細からECIDを取得します。 上記のクエリでそのECID値を使用します。

### feedbackStatus値

| 値 | 意味 |
|-------|---------|
| `sent` | APNに引き渡し – デバイスレンダリングを確認しません（以下のメモを参照）。 |
| `error` | 配信エラー – `failure_reason`で詳細を確認してください |
| `exclude` | 送信前にプロファイルを除外（トークンが欠落している、同意の問題またはタイポロジルール） |
| `delay` | 配信の遅延。再試行されます |

>[!NOTE]
>
> `la_event` フィールドの場合、最初の配信イベントのデータセット レコードは`start`ではなく`remotestart`です。 イベントタイプでクエリを実行する際に、それに応じてフィルタリングします。

### 送信済みステータスの解釈

`sent`件中`feedbackStatus`件は、Journey OptimizerがAPNに通知を正常に渡したことを確認します。 ライブ アクティビティがデバイス上でレンダリングされたことを&#x200B;**not**&#x200B;が確認します。

iOSでは、通知がAPNを離れた後もコールバックは提供されません。 デバイス側のエラー（OS制限、APNとデバイス間のネットワークドロップ、8時間のライブアクティビティ期間制限に達しているなど）は、データセットから観察できません。 `feedbackStatus`が`sent`であるが、デバイスにライブアクティビティが表示されない場合、問題はJourney Optimizer パイプラインの外にあります。 Assurance プラグインまたはアプリレベルのログを使用して、デバイスサイドの動作を診断します。


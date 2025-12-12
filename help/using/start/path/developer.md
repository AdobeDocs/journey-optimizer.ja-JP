---
title: 開発者向けの基礎知識
description: 開発者向けに Journey Optimizer の操作方法の詳細について説明します
feature: Get Started
role: Developer
level: Experienced
exl-id: 5053dd4f-d050-415f-bc74-d6d061bdcbe1
source-git-commit: 2d699fe8a3320400dad2d5d962028d6e2a5425f8
workflow-type: tm+mt
source-wordcount: '1816'
ht-degree: 3%

---

# 開発者向けの基礎知識 {#get-started-developers}

**開発者** には、[!DNL Adobe Journey Optimizer] ールを実装し、アプリケーションやシステムに統合する責任があります。 [!DNL Adobe Journey Optimizer] システム管理者 [ と ](administrator.md) データエンジニア [ からアクセス権を付与され、環境の準備ができたら、](data-engineer.md) での作業を開始できます。

## Journey Optimizer エコシステムでの役割

他のチームメンバーがユーザーインターフェイスを使用してJourney Optimizerを設定する際は、以下に焦点を当てます。

* モバイルアプリケーションと web アプリケーションでの **SDK の実装**
* アプリケーションからトリガージャーニーへの **イベントの送信**
* カスタムアクションを使用してJourney Optimizerが呼び出すことができる **API エンドポイントの構築**
* **Journey Optimizerの統合** 既存のシステムおよびインフラストラクチャとの統合
* 実装 **テストとデバッグ**

[ データエンジニア ](data-engineer.md) が、データスキーマ、イベント設定およびデータソースを処理します。 [ 管理者 ](administrator.md) が権限とチャネル設定をセットアップします。 [ マーケター ](marketer.md) は、実装を使用するジャーニーとコンテンツを設計します。

このガイドでは、Journey Optimizerを使い始めるための基本的な技術実装手順を説明します。 モバイルアプリを作成する場合でも、web エクスペリエンスを作成する場合でも、API 統合を作成する場合でも、以下の節に従って実装を設定してください。

## 前提条件 {#prerequisites}

実装を開始する前に、次のことを確認します。

| カテゴリ | 要件 |
|----------|-------------|
| **技術力** | * JavaScript （Web SDK用）または Swift/Kotlin （Mobile SDK用）の使用経験 <br>* RESTful API と JSON の理解 <br>*非同期プログラミングおよびイベント駆動型アーキテクチャに関する知識 <br>*組織のアプリケーションアーキテクチャに関する知識 |
| **アクセスとツール** | * API 資格情報の [Adobe Developer Console](https://developer.adobe.com){target="_blank"} へのアクセス <br>* アプリケーションのコードベースへのアクセスを使用した開発環境 <br>* API テスト用Postmanなどのテストツール <br>* ブラウザー開発者ツールまたはモバイルデバッグツール |
| **他のチームメンバーから** | *お客様の [ 管理者 ](administrator.md)<br>*XDM スキーマおよびイベント定義によって付与された環境アクセス *お客様の [ データエンジニア ](data-engineer.md)<br>*要件およびユースケースからの [ マーケター ](marketer.md) |

## 技術基盤について {#technical-foundation}

実装に立ち入る前に、次の主要な技術概念を理解しておく必要があります。

1. **Adobe Experience Platform統合**: Journey Optimizerは、Adobe Experience Platformでネイティブに構築されています。 基盤となるアーキテクチャを理解すると、より効果的な実装を構築するのに役立ちます。 詳しくは、[Journey Optimizerの仕組み ](../understanding-ajo.md) を参照してください。

1. **XDM データモデル**:Journey Optimizerは、Experience Data Model （XDM）を使用してイベントとプロファイルデータを構造化します。 開発者は、[ データエンジニア ](data-engineer.md) が設定したスキーマに準拠するデータの送信方法を理解する必要があります。 [XDM スキーマ ](../../data/get-started-schemas.md) について説明します。

1. **認証とセキュリティ**：すべての実装に適切な認証が必要です。 SDK と API の認証を設定する方法を理解します。 [API 認証 ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} の詳細情報

## モバイルアプリ統合の設定 {#mobile-integration}

### Adobe Experience Platform Mobile SDKの設定

プッシュ通知、アプリ内メッセージおよびその他のモバイル機能を有効にするには、モバイルアプリケーションにAdobe Experience Platform Mobile SDKを組み込みます。

1. **Mobile SDKをインストールして設定**: [Adobe Experience Platform Mobile SDKのドキュメント ](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} に従って、SDK統合を開始します。

1. **モバイルプロパティの作成**:[!DNL Adobe Experience Platform Data Collection] でモバイルプロパティを設定します。 方法について説明します [ モバイルプロパティを作成および設定する ](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}。

1. **プッシュ通知の設定**:
   * **iOS アプリ** の場合：アプリを APN に登録します（Apple プッシュ通知サービス）。 詳しくは、[Appleのドキュメント ](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"} を参照してください。
   * **Android アプリの場合**:Android アプリ用に Firebase Cloud Messaging を設定します。 詳しくは、[Googleのドキュメント ](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"} を参照してください。

1. **モバイル統合のテスト**:[ モバイルオンボーディングのクイックスタートワークフロー ](../../push/mobile-onboarding-wf.md) を使用して、モバイル設定を迅速に設定し、テストします。

プッシュ通知を設定する詳細な手順については、[ このページ ](../../push/push-configuration.md) を参照してください。

### コードベースのエクスペリエンスの実装（Mobile SDK）

コードベースのエクスペリエンスを使用したネイティブモバイルアプリのパーソナライズ機能の場合：

* Mobile SDKの実装については、[ このチュートリアル ](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/code-based/tutorial/){target="_blank"} に従ってください
* [iOS} および ](https://github.com/adobe/aepsdk-messaging-ios/tree/main/TestApps/MessagingDemoAppSwiftUI){target="_blank"}2}Android[ のサンプル実装を確認します](https://github.com/adobe/aepsdk-messaging-android/tree/main/code/testapp){target="_blank"}

## Web エクスペリエンスの実装 {#web-implementation}

### Adobe Experience Platform Web SDKの設定

Web ベースの実装の場合、Web SDKが主な統合ポイントになります。

1. **Web SDKをインストール**:『 Web SDK導入ガイド [ に従って、web サイトにSDKを設定します ](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"}。

1. **データストリームを設定**:Journey Optimizerを有効にして、[!DNL Adobe Experience Platform Data Collection] でデータストリームを作成および設定します。 詳しくは、[ データストリームのドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target="_blank"} を参照してください。

1. **Web プッシュ通知を有効にする** （オプション）:Web SDK設定で [pushNotifications プロパティ ](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/pushnotifications){target="_blank"} を設定し、[sendPushSubscription コマンド ](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/sendpushsubscription){target="_blank"} を使用してプッシュ購読を登録します。

### コードベースのエクスペリエンスの実装（Web SDK）

コードベースのエクスペリエンスを使用すると、あらゆるデジタルタッチポイントをパーソナライズできます。

1. **実装方法をクライアントサイド、サーバーサイド、ハイブリッドから選択します**。 アプローチごとに [ 実装サンプル ](../../code-based/code-based-implementation-samples.md) を確認します。

1. **サーフェスの定義**：パーソナライズされたコンテンツを配信するアプリケーション内の場所を特定します。 [ サーフェス設定 ](../../code-based/code-based-surface.md) について説明します。

1. **コンテンツレンダリングの実装**:Web SDKを使用して、パーソナライゼーションコンテンツを取得し、適用します。 [ コードベースの実装チュートリアル ](../../code-based/code-based-decisioning-implementations.md) を参照してください。

1. **表示イベントとインタラクションイベントの送信**：コンテンツが表示されるタイミングと、分析と最適化のためにユーザーがコンテンツとやり取りするタイミングを追跡します。

[GitHub のサンプル実装 ](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"} を調べて、コードベースのエクスペリエンスの動作を確認します。

詳しくは、[ コードベースのエクスペリエンスの概要 ](../../code-based/get-started-code-based.md) を参照してください。

## イベントストリーミングの実装 {#event-streaming}

### トリガージャーニーへのイベントの送信

トリガーは、ジャーニーを開発するイベントを送信するコードを実装します。 担当の [ データエンジニア ](data-engineer.md) が、Journey Optimizerでイベントのスキーマと定義を設定します。

1. **イベントペイロードについて**：データエンジニアと協力して、イベントのスキーマと必要なペイロード構造を取得します。 ペイロードは、設定した XDM スキーマに準拠する必要があります。 [ イベントスキーマ要件 ](../../event/experience-event-schema.md) について説明します。

1. **イベントストリーミングの実装**:[ ストリーミング取得 API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja){target="_blank"} を使用して、Adobe Experience Platformにイベントを送信します。 [ イベントの送信手順 ](../../event/additional-steps-to-send-events-to-journey.md) を説明します。

1. **イベントタイプを処理**:
   * **単一イベント**：ユーザー固有のアクション（ボタンのクリック、購入完了など）のイベント送信を実装します
   * **ビジネスイベント**：ビジネス関連のイベント（在庫の更新、価格の変更など）を送信します

1. **イベント配信をテスト**：イベントが適切に受信され、ジャーニーが期待どおりにトリガーすることを確認します。 詳細情報 [ イベントのトラブルシューティング ](../../building-journeys/troubleshooting-inbound.md)。

API を使用してイベントを送信する場合の **実装例**:

```javascript
POST https://{DATACOLLECTION_ENDPOINT}/collection/{DATASTREAM_ID}
Content-Type: application/json

{
  "header": {
    "datasetId": "{DATASET_ID}",
    "imsOrgId": "{ORG_ID}",
    "source": {
      "name": "Web SDK"
    }
  },
  "body": {
    "xdmMeta": {
      "schemaRef": {
        "id": "{SCHEMA_ID}"
      }
    },
    "xdmEntity": {
      "_id": "unique-event-id",
      "eventType": "purchase",
      "timestamp": "2024-01-01T12:00:00Z",
      // ... your event data
    }
  }
}
```

詳しくは、[ ジャーニーイベントの操作 ](../../event/about-events.md) を参照してください。

## カスタムアクションエンドポイントの開発 {#custom-actions}

カスタムアクションを使用すると、ジャーニーで API を呼び出すことができます。 開発者は、カスタムアクションによって呼び出される API エンドポイントを作成します。

1. **API エンドポイントの作成**：ジャーニーの実行中にJourney Optimizerが呼び出す RESTful API エンドポイントを作成します。 エンドポイントは次のようになります。
   * JSON ペイロードを受け入れる
   * リクエストの認証（OAuth、API キーまたは JWT）
   * 適切なタイムアウト制限内でリクエストを処理
   * 応答を想定される形式で返します

1. **カスタムアクション機能について**：カスタムアクションは、Epsilon、Slack、Firebase、独自のサービスなどのサードパーティシステムに接続できます。 詳しくは、[カスタムアクション](../../action/action.md)を参照してください。

1. **アクション設定の操作**:[ 管理者 ](administrator.md) または [ データエンジニア ](data-engineer.md) が、Journey Optimizerでカスタムアクションを設定し、API エンドポイントの URL、認証方法、パラメーターを定義します。 API 仕様を提供します。 [ カスタムアクション設定 ](../../action/about-custom-action-configuration.md) について説明します。

1. **アクションにつながるデータを返す**：後続のジャーニーステップで使用できるデータを返すように API を設計します。 詳細情報 [ アクション応答 ](../../action/action-response.md)。

1. **レート制限の実装**：想定されるボリュームをエンドポイントが処理できることを確認します。 Journey Optimizerでは 1 秒あたり 5,000 回の呼び出しに制限が適用されますが、システムは回復力を備えている必要があります。 [ キャッピングとスロットル ](../../configuration/external-systems.md) について説明します。

**例のユースケース**:[Experience Platformへのジャーニーイベントの書き込み ](../../building-journeys/custom-action-aep.md) カスタムアクションの使用

## Journey Optimizer API の操作 {#apis}

Journey Optimizerは、プログラムによるアクセス用に包括的な REST API を提供しています。

1. **API の機能について**:Journey Optimizer API を使用すると、様々なリソースをプログラムで作成、読み取り、更新、削除できます。 [Journey Optimizer API](../../configuration/ajo-apis.md) について説明します。

1. **認証**:[ このチュートリアル ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} に従って、Adobe Developer Consoleを使用して API 認証を設定します。

1. **API リファレンスについて**：完全な API ドキュメントを参照して、[Adobe Journey Optimizer API リファレンスで直接 API を試してください ](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}。

1. **API トリガーキャンペーン**:API トリガーキャンペーンを使用してトランザクションメッセージを作成します。 大量のシナリオ（最大 5,000 TPS）の場合は、[ ハイスループットモード ](../../campaigns/api-triggered-high-throughput.md) を参照してください（アドオンライセンスが必要です）。

1. **意思決定管理 API**：オファー管理と意思決定には専用の API を使用します。 詳しくは、[ 意思決定管理 API ガイド ](../../offers/api-reference/getting-started.md) を参照してください。

## テストとデバッグ {#testing}

1. **SDK実装のデバッグ**:Adobe Experience Platform Assuranceを使用して、SDK イベントの調査、データ収集の検証、統合に関する問題のトラブルシューティングをリアルタイムで行います。 [Assuranceの詳細情報 ](https://experienceleague.adobe.com/docs/experience-platform/assurance/home.html?lang=ja){target="_blank"}。

1. **イベント配信をテスト**：アプリケーションからのイベントが、Adobe Experience Platformおよびトリガージャーニーで期待どおりに正しく受信されていることを確認します。 イベント取り込みを監視し、ペイロード構造を検証します。

1. **API 統合の検証**：カスタムアクションエンドポイントをテストし、Journey Optimizer リクエストが正しく処理され、タイムアウト制限内で応答し、期待されるデータ形式を返すことを確認します。

1. **テストプロファイルでテストモードを使用**：お客様の [ データエンジニア ](data-engineer.md) と協力してテストプロファイルへのアクセス権を取得し、ジャーニーテストモードを使用して実装を検証します。 詳細情報 [ ジャーニーのテスト ](../../building-journeys/testing-the-journey.md)。

1. **SDK ログの監視**:SDK実装でデバッグログを有効にして、開発中の問題のトラブルシューティングを行います。
   * **Mobile SDK**：ログを有効にして、SDKのイベントと API 呼び出しを表示します
   * **Web SDK**：ブラウザーコンソールを使用して、SDKのアクティビティを監視します

1. **データストリーム設定の確認**:Journey Optimizerにデータを送信するようにデータストリームが正しく設定されていることを確認します。 イベントがデータストリームを介して正しい宛先に送られるかどうかを確認します。

1. **分析用にジャーニーデータをクエリ**：データレイクの SQL クエリを使用して、ジャーニーステップイベントの分析、問題のデバッグ、カスタムアクションのパフォーマンスの監視を行います。 次のような、ジャーニー分析の [ クエリ例 ](../../reports/query-examples.md) を探索します。
   * プロファイルのエントリ/離脱のトラッキングと破棄理由
   * カスタムアクションパフォーマンス指標（待ち時間、スループット、エラー）
   * イベントの配信とエラーパターン
   * ジャーニーインスタンスの状態

## 開発者向けの詳細トピック {#advanced-topics}

### コンテキストデータとエンリッチメントの操作

* **配列の反復**：ハンドルバー構文を使用して、イベント、カスタムアクション応答およびデータセット検索からの動的リストをメッセージに表示します。 [ コンテキストデータの反復 ](../../personalization/iterate-contextual-data.md) について説明します。
* **データセット検索**：データセット検索を実装して、Adobe Experience Platform データセットからのジャーニーデータを強化します。 設定については、データエンジニアにお問い合わせください。 [ データセットルックアップ ](../../building-journeys/dataset-lookup.md) について説明します。

### 同意とガバナンスの使用

統合にデータガバナンスと同意ポリシーを実装します。

* **データガバナンス**：カスタムアクションにデータ使用ポリシーを適用します。 詳しくは、[ データガバナンス ](../../action/action-privacy.md) を参照してください。
* **同意管理**：実装で顧客の同意環境設定を処理します。 [ 同意 ](../../action/consent.md) の詳細情報。

### 最適化とベストプラクティス

* **キャッピングとスロットル**：レート制限を理解し、適切なスロットルを実装します。 [ 外部システム ](../../configuration/external-systems.md) の詳細情報
* **ジャーニーの最適化**: [ ジャーニーの最適化 ](../../building-journeys/optimize.md) のベストプラクティスに従います。
* **エラー処理**：堅牢なエラー処理を実装します。 [ エラーコード ](../../building-journeys/error-codes-reference.md) と [ トラブルシューティングガイド ](../../building-journeys/troubleshooting.md) を確認します。

## その他のリソース {#additional-resources}

* **Developer Console**: [Adobe Developer Console](https://developer.adobe.com){target="_blank"} にアクセスして統合を作成し、API 資格情報を管理します。
* **サンプルコード**:[GitHub のサンプル実装 ](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"} を調べます。
* **チュートリアルビデオ**: [Experience League](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html?lang=ja){target="_blank"} の実践チュートリアルを通じて学びます。
* **開発者コミュニティ**:Adobe コミュニティフォーラムで、他の開発者とつながり、サポートを受けることができます。

## 複数の役割での共同作業 {#next-steps}

実装作業が他のチームメンバーと重なっています。

>[!BEGINTABS]

>[!TAB  データエンジニアとの連携 ]

データとイベントの設定に関する [ データエンジニア ](data-engineer.md) との共同作業：

* 実装する必要がある XDM スキーマとイベント構造を取得します
* 送信する必要があるイベントと、必要なペイロード形式を理解する
* データ収集要件とデータ品質基準の調整
* イベント配信とデータ取り込みのテスト

>[!TAB  管理者の操作 ]

アクセスと設定に関する [ 管理者 ](administrator.md) との共同作業：

* 設定するカスタムアクションの API 仕様を提供する
* 必要な権限と API 資格情報のリクエスト
* チャネル設定要件（プッシュ証明書など）に基づく調整
* テスト環境とサンドボックス戦略の調整

>[!TAB  マーケターとの連携 ]

ジャーニー要件とテストに関する [ マーケター ](marketer.md) との共同作業：

* イベントをトリガーにするユーザーインタラクションについて
* コンテンツのパフォーマンスとユーザーエンゲージメントを追跡するための実装
* 実装した機能でジャーニーのテストをサポート
* メッセージ配信またはパーソナライゼーションに関する問題のトラブルシューティング

>[!ENDTABS]

## 実装の開始

ビルドを開始する準備はできていますか？ 上記の節から最初の実装領域を選択します。

1. **モバイルアプリ？** Mobile SDK統合 [ の基本を ](#mobile-integration) ぶ
2. **Web サイト？** Web SDKの設定 [ から始める ](#web-implementation)
3. **API 統合？** ジャンプ [API の操作 ](#apis)
4. **カスタムシステム？** チェックアウト [ カスタムアクション ](#custom-actions)

各セクションには、実装をガイドする詳細な技術ドキュメント、コードサンプル、チュートリアルへのリンクが含まれています。

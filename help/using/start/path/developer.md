---
title: 開発者向けの基礎知識
description: 開発者向けに Journey Optimizer の操作方法の詳細について説明します
feature: Get Started
role: Developer
level: Experienced
exl-id: 5053dd4f-d050-415f-bc74-d6d061bdcbe1
source-git-commit: 2d699fe8a3320400dad2d5d962028d6e2a5425f8
workflow-type: ht
source-wordcount: '1816'
ht-degree: 100%

---

# 開発者向けの基礎知識 {#get-started-developers}

**開発者**&#x200B;は、[!DNL Adobe Journey Optimizer] をアプリケーションやシステムに実装し、統合する責任を負います。[システム管理者](administrator.md)と[データエンジニア](data-engineer.md)からアクセス権を付与され、環境の準備ができたら、[!DNL Adobe Journey Optimizer] での作業を開始できます。

## Journey Optimizer エコシステムでの役割

他のチームメンバーがユーザーインターフェイスを通じて Journey Optimizer を設定している間、以下に焦点を当てます。

* モバイルアプリケーションと web アプリケーションでの **SDK の実装**
* ジャーニーをトリガーするためのアプリケーションからの&#x200B;**イベントの送信**
* カスタムアクションを通じて Journey Optimizer が呼び出せる **API エンドポイントの作成**
* Journey Optimizer と既存のシステムおよびインフラストラクチャとの&#x200B;**統合**
* 実装の&#x200B;**テストとデバッグ**

[データエンジニア](data-engineer.md)は、データスキーマ、イベント設定およびデータソースを処理します。[管理者](administrator.md)は、権限とチャネル設定を指定します。[マーケター](marketer.md)は、実装を使用するジャーニーとコンテンツをデザインします。

このガイドでは、Journey Optimizer を開始するための基本的な技術的実装手順について説明します。モバイルアプリ、web エクスペリエンス、API 統合のいずれを作成する場合でも、以下の節に従って実装を設定してください。

## 前提条件 {#prerequisites}

実装を開始する前に、以下の点を確認してください。

| カテゴリ | 要件 |
|----------|-------------|
| **技術スキル** | * JavaScript（Web SDK の場合）または Swift／Kotlin（Mobile SDK の場合）の使用経験<br>* RESTful API と JSON に関する理解<br>* 非同期プログラミングとイベント駆動型アーキテクチャに関する知識<br>* 組織のアプリケーションアーキテクチャに関する知識 |
| **アクセスとツール** | * API 資格情報用の [Adobe Developer Console](https://developer.adobe.com){target="_blank"} へのアクセス権<br>* アプリケーションのコードベースへのアクセス権がある開発環境<br>* API テスト用の Postman などのテストツール<br>* ブラウザー開発者ツールまたはモバイルデバッグツール |
| **他のチームメンバーから** | * [管理者](administrator.md)<br>から付与された環境へのアクセス権* [データエンジニア](data-engineer.md)<br>からの XDM スキーマとイベント定義* [マーケター](marketer.md)からの要件とユースケース |

## 技術的な基盤について {#technical-foundation}

実装に進む前に、次のコアとなる技術概念を理解しておきます。

1. **Adobe Experience Platform の統合**：Journey Optimizer は、Adobe Experience Platform でネイティブに作成されています。基盤となるアーキテクチャを理解すると、より効果的な実装を作成できます。詳しくは、[Journey Optimizer の仕組み](../understanding-ajo.md)を参照してください。

1. **XDM データモデル**：Journey Optimizer は、エクスペリエンスデータモデル（XDM）を使用して、イベントデータとプロファイルデータを構造化します。開発者は、[データエンジニア](data-engineer.md)が設定したスキーマに準拠するデータの送信方法を理解する必要があります。 詳しくは、[XDM スキーマ](../../data/get-started-schemas.md)を参照してください。

1. **認証とセキュリティ**：すべての実装に適切な認証が必要です。SDK と API の認証を設定する方法を理解します。詳しくは、[API 認証](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}を参照してください。

## モバイルアプリの統合の設定 {#mobile-integration}

### Adobe Experience Platform Mobile SDK の設定

プッシュ通知、アプリ内メッセージ、他のモバイル機能を有効にするには、Adobe Experience Platform Mobile SDK をモバイルアプリケーションに統合します。

1. **Mobile SDK をインストールして設定**：[Adobe Experience Platform Mobile SDK ドキュメント](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"}に従って、SDK 統合を開始します。

1. **モバイルプロパティを作成**：[!DNL Adobe Experience Platform Data Collection] でモバイルプロパティを設定します。詳しくは、[モバイルプロパティの作成と設定](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}方法を参照してください。

1. **プッシュ通知を設定**：
   * **iOS アプリ**&#x200B;の場合：アプリを APNs（Apple プッシュ通知サービス）に登録します。詳しくは、[Apple のドキュメント](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}を参照してください。
   * **Android アプリ**&#x200B;の場合：Android アプリに Firebase Cloud Messaging を設定します。詳しくは、[Google のドキュメント](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}を参照してください。

1. **モバイル統合をテスト**：[モバイルオンボーディングのクイックスタートワークフロー](../../push/mobile-onboarding-wf.md)を使用して、モバイル設定を迅速に設定およびテストします。

プッシュ通知を設定する手順について詳しくは、[このページ](../../push/push-configuration.md)を参照してください。

### コードベースのエクスペリエンスの実装（Mobile SDK）

コードベースのエクスペリエンスを使用したネイティブモバイルアプリのパーソナライゼーションの場合：

* Mobile SDK の実装について詳しくは、[このチュートリアル](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/code-based/tutorial/){target="_blank"}に従ってください
* [iOS](https://github.com/adobe/aepsdk-messaging-ios/tree/main/TestApps/MessagingDemoAppSwiftUI){target="_blank"} および [Android](https://github.com/adobe/aepsdk-messaging-android/tree/main/code/testapp){target="_blank"} のサンプル実装を確認します

## Web エクスペリエンスの実装 {#web-implementation}

### Adobe Experience Platform Web SDK の設定

Web ベースの実装の場合、Web SDK が主な統合ポイントです。

1. **Web SDK をインストール**：[Web SDK 実装ガイド](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"}に従って、web サイトに SDK を設定します。

1. **データストリームを設定**：Journey Optimizer を有効にして、[!DNL Adobe Experience Platform Data Collection] でデータストリームを作成および設定します。詳しくは、[データストリームドキュメント](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target="_blank"}を参照してください。

1. **Web プッシュ通知を有効にする**（オプション）：Web SDK 設定で [pushNotifications プロパティ](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/pushnotifications){target="_blank"}を設定し、[sendPushSubscription コマンド](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/sendpushsubscription){target="_blank"}を使用してプッシュ購読を登録します。

### コードベースのエクスペリエンスの実装（Web SDK）

コードベースのエクスペリエンスを使用すると、任意のデジタルタッチポイントをパーソナライズできます。

1. **実装方法を選択**：クライアントサイド、サーバーサイド、ハイブリッド。各アプローチの[実装サンプル](../../code-based/code-based-implementation-samples.md)を確認します。

1. **サーフェスを定義**：パーソナライズされたコンテンツを配信するアプリケーション内の場所を特定します。詳しくは、[サーフェスの設定](../../code-based/code-based-surface.md)を参照してください。

1. **コンテンツレンダリングを実装**：Web SDK を使用して、パーソナライゼーションコンテンツを取得および適用します。[コードベースの実装チュートリアル](../../code-based/code-based-decisioning-implementations.md)を参照してください。

1. **表示イベントとインタラクションイベントを送信**：コンテンツが表示されるタイミングと、ユーザーがコンテンツとやり取りするタイミングを追跡して、分析と最適化を行います。

実際のコードベースのエクスペリエンスを確認するには、[GitHub のサンプル実装](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"}を参照してください。

詳しくは、[コードベースのエクスペリエンスの基本を学ぶ](../../code-based/get-started-code-based.md)を参照してください。

## イベントストリーミングの実装 {#event-streaming}

### ジャーニーをトリガーするイベントの送信

開発者は、ジャーニーをトリガーするイベントを送信するコードを実装します。[データエンジニア](data-engineer.md)は、Journey Optimizer でイベントスキーマと定義を設定します。

1. **イベントペイロードを理解**：データエンジニアと連携して、イベントスキーマと必要なペイロード構造を取得します。ペイロードは、設定した XDM スキーマに準拠する必要があります。詳しくは、[イベントスキーマ要件](../../event/experience-event-schema.md)を参照してください。

1. **イベントストリーミングを実装**：[Streaming Ingestion API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja){target="_blank"} を使用して、Adobe Experience Platformにイベントを送信します。詳しくは、[イベントの送信手順](../../event/additional-steps-to-send-events-to-journey.md) を参照してください。

1. **イベントタイプを処理**：
   * **単一イベント**：ユーザー固有のアクション（例：ボタンのクリック、購入完了）に対するイベント送信を実装します
   * **ビジネスイベント**：ビジネス関連のイベント（例：在庫の更新、価格の変更）を送信します

1. **イベント配信をテスト**：イベントが適切に受信され、期待どおりにジャーニーがトリガーされることを確認します。詳しくは、[イベントのトラブルシューティング](../../building-journeys/troubleshooting-inbound.md)を参照してください。

API 経由でイベントを送信する場合の&#x200B;**実装例**：

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

詳しくは、[ジャーニーイベントの操作](../../event/about-events.md)を参照してください。

## カスタムアクションエンドポイントの開発 {#custom-actions}

カスタムアクションを使用すると、ジャーニーで API を呼び出すことができます。開発者は、カスタムアクションにより呼び出される API エンドポイントを作成します。

1. **API エンドポイントを作成**：ジャーニー実行中に Journey Optimizer により呼び出される RESTful API エンドポイントを作成します。エンドポイントで次の操作を実行する必要があります。
   * JSON ペイロードを受け入れる
   * リクエストを認証（OAuth、API キーまたは JWT）
   * 適切なタイムアウト制限内でリクエストを処理
   * 応答を想定される形式で返す

1. **カスタムアクションの機能を理解**：カスタムアクションは、Epsilon、Slack、Firebase などのサードパーティシステムや独自のサービスに接続できます。詳しくは、[カスタムアクション](../../action/action.md)を参照してください。

1. **アクション設定を操作**：[管理者](administrator.md)または[データエンジニア](data-engineer.md)は、Journey Optimizer でカスタムアクションを設定し、API エンドポイント URL、認証方法、パラメーターを定義します。お客様は、API 仕様を管理者またはデータエンジニアに提供してください。詳しくは、[カスタムアクション設定](../../action/about-custom-action-configuration.md)を参照してください。

1. **アクションにつながるデータを返す**：後続のジャーニーステップで使用できるデータを返すように API をデザインします。詳しくは、[アクション応答](../../action/action-response.md)を参照してください。

1. **レート制限を実装**：エンドポイントが想定されるボリュームを処理できることを確認します。Journey Optimizer では、1 秒あたり 5000 回の呼び出しの制限が適用されますが、システムは回復力を備えている必要があります。詳しくは、[キャップとスロットル](../../configuration/external-systems.md)を参照してください。

**ユースケース例**：カスタムアクションを使用して、[ジャーニーイベントを Experience Platform に書き込みます](../../building-journeys/custom-action-aep.md)。

## Journey Optimizer API の操作 {#apis}

Journey Optimizer は、プログラムによるアクセス用の包括的な REST API を提供します。

1. **API 機能を理解**：Journey Optimizer API を使用すると、様々なリソースをプログラムで作成、読み取り、更新、削除できます。詳しくは、[Journey Optimizer API](../../configuration/ajo-apis.md) を参照してください。

1. **認証**：[このチュートリアル](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}に従って、Adobe Developer Console を使用して API 認証を設定します。

1. **API リファレンスを探索**：完全な API ドキュメントを参照して、[Adobe Journey Optimizer API リファレンス](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}で API を直接試します。

1. **API トリガーキャンペーン**：API トリガーキャンペーンを使用して、トランザクションメッセージを作成します。大量のシナリオ（最大 5000 TPS）の場合は、[高スループットモード](../../campaigns/api-triggered-high-throughput.md)を探索します（アドオンライセンスが必要）。

1. **Decision Management API**：オファー管理と決定に専用の API を使用します。詳しくは、[Decision Management API ガイド](../../offers/api-reference/getting-started.md)を参照してください。

## テストとデバッグ {#testing}

1. **SDK 実装をデバッグ**：Adobe Experience Platform Assurance を使用して、SDK イベントの検査、データ収集の検証、統合に関する問題のトラブルシューティングをリアルタイムで行います。[オーディエンスの詳細情報](https://experienceleague.adobe.com/docs/experience-platform/assurance/home.html?lang=ja){target="_blank"}。

1. **イベント配信をテスト**：アプリケーションからのイベントが Adobe Experience Platform により正しく受信され、期待どおりにジャーニーがトリガーされることを確認します。イベントの取り込みを監視し、ペイロード構造を検証します。

1. **API 統合を検証**：カスタムアクションエンドポイントをテストして、Journey Optimizer リクエストが正しく処理され、タイムアウト制限内に応答し、期待されるデータ形式が返されることを確認します。

1. **テストプロファイルでテストモードを使用**：[データエンジニア](data-engineer.md)と連携してテストプロファイルにアクセスし、ジャーニーテストモードを使用して実装を検証します。詳しくは、[ジャーニーのテスト](../../building-journeys/testing-the-journey.md)方法を参照してください。

1. **SDK ログを監視**：SDK 実装でデバッグログを有効にして、開発中の問題をトラブルシューティングします。
   * **Mobile SDK**：ログを有効にして、SDK イベントと API 呼び出しを確認します
   * **Web SDK**：ブラウザーコンソールを使用して SDK アクティビティを監視します

1. **データストリームの設定を確認**：データストリームが Journey Optimizer にデータを送信するために正しく設定されていることを確認します。イベントがデータストリームを通じて正しい宛先にフローされることを確認します。

1. **分析用にジャーニーデータのクエリを実行**：データレイクで SQL クエリを使用して、ジャーニーステップイベントの分析、問題のデバッグ、カスタムアクションのパフォーマンスの監視を行います。次を含む[ジャーニー分析のクエリ例](../../reports/query-examples.md)を探索します。
   * プロファイルのエントリ／終了のトラッキングと破棄理由
   * カスタムアクションのパフォーマンス指標（待ち時間、スループット、エラー）
   * イベントの配信パターンとエラーパターン
   * ジャーニーインスタンスの状態

## 高度な開発者向けトピック {#advanced-topics}

### コンテキストデータとエンリッチメントの操作

* **配列を反復処理**：Handlebars 構文を使用して、イベント、カスタムアクション応答およびメッセージ内のデータセット検索からの動的なリストを表示します。詳しくは、[コンテキストデータの反復処理](../../personalization/iterate-contextual-data.md)を参照してください。
* **データセット参照**：データセット参照を実装して、Adobe Experience Platform データセットからのジャーニーデータを強化します。設定について詳しくは、データエンジニアと連携してください。詳しくは、[データセット参照](../../building-journeys/dataset-lookup.md)を参照してください。

### 同意とガバナンスの操作

統合にデータガバナンスと同意ポリシーを実装します。

* **データガバナンス**：カスタムアクションにデータ使用ポリシーを適用します。詳しくは、[データガバナンス](../../action/action-privacy.md)を参照してください。
* **同意管理**：実装で顧客の同意環境設定を処理します。詳しくは、[同意](../../action/consent.md)を参照してください。

### 最適化とベストプラクティス

* **キャップとスロットル**：レート制限を理解し、適切なスロットルを実装します。詳しくは、[外部システム](../../configuration/external-systems.md)を参照してください。
* **ジャーニーの最適化**：[ジャーニーの最適化](../../building-journeys/optimize.md)のベストプラクティスに従います。
* **エラー処理**：堅牢なエラー処理を実装します。詳しくは、[エラーコード](../../building-journeys/error-codes-reference.md)および[トラブルシューティングガイド](../../building-journeys/troubleshooting.md)を参照してください。

## その他のリソース {#additional-resources}

* **Developer Console**：[Adobe Developer Console](https://developer.adobe.com){target="_blank"} にアクセスして統合を作成し、API 資格情報を管理します。
* **サンプルコード**：[GitHub のサンプル実装](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"}を探索します。
* **チュートリアルビデオ**：[Experience League](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html?lang=ja){target="_blank"} の実践的なチュートリアルを通じて学びます。
* **開発者コミュニティ**：アドビコミュニティフォーラムで、他の開発者とつながり、サポートを受けることができます。

## 役割をまたいだ共同作業 {#next-steps}

実装作業は、次の他のチームメンバーと連携します。

>[!BEGINTABS]

>[!TAB データエンジニアとの連携]

データとイベントの設定に関する[データエンジニア](data-engineer.md)との共同作業：

* 実装に必要な XDM スキーマとイベント構造を取得
* 送信する必要があるイベントとその必須のペイロード形式を理解
* データ収集要件とデータ品質基準に関して調整
* イベント配信とデータ取り込みを連携してテスト

>[!TAB 管理者との連携]

アクセスと設定に関する[管理者](administrator.md)との共同作業：

* 設定するカスタムアクションの API 仕様を提供
* 必要な権限と API 資格情報をリクエスト
* チャネル設定要件（例：プッシュ証明書）を調整
* テスト環境とサンドボックス戦略を調整

>[!TAB マーケターとの連携]

ジャーニー要件とテストに関する[マーケター](marketer.md)との共同作業：

* イベントをトリガーする必要があるユーザーインタラクションを理解
* コンテンツのパフォーマンスとユーザーエンゲージメントのトラッキングを実装
* 実装した機能を使用してジャーニーのテストをサポート
* メッセージ配信やパーソナライゼーションに関する問題をトラブルシューティング

>[!ENDTABS]

## 実装の開始

作成を開始する準備は整っていますか？上記の節から最初の実装領域を選択します。

1. **モバイルアプリですか？**[Mobile SDK 統合](#mobile-integration)から開始します
2. **Web サイトですか？**[Web SDK 設定](#web-implementation)から開始します
3. **API 統合ですか？**[API の操作](#apis)にジャンプします
4. **カスタムシステムですか？**[カスタムアクション](#custom-actions)を確認します

各節には、実装をガイドする詳細な技術ドキュメント、コードサンプル、チュートリアルへのリンクが含まれています。

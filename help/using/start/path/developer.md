---
title: 開発者向けの基礎知識
description: 開発者向けに Journey Optimizer の操作方法の詳細について説明します
feature: Get Started
role: Developer
level: Intermediate
exl-id: 5053dd4f-d050-415f-bc74-d6d061bdcbe1
TQID: https://experienceleague.adobe.com/7fRI-CPkIeBAPjtXmDgFdyNKgB4WwEc01yKrGUXnc3U
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
subfeature_v2:
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: c2beecbb-b93e-4ae3-baa9-72adcdc06781
  - id: d08afb72-92f6-4856-88e3-11ec34313c2f
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4c109a6021d46ee7290f09d9333892b42b5af3e2
workflow-type: tm+mt
source-wordcount: 3490
ht-degree: 54%

---

# 開発者向けの基本を学ぶ {#get-started-developers}

>[!BEGINSHADEBOX]

**このページ：** アプリケーションをAdobe Journey Optimizerに接続するSDK、イベントストリーミング、カスタムアクションエンドポイント、およびAPIを実装して、ライブデータでジャーニーを実行できるようにします。

>[!ENDSHADEBOX]

**開発者**&#x200B;は、[!DNL Adobe Journey Optimizer] をアプリケーションやシステムに実装し、統合する責任を負います。 [システム管理者](administrator.md)と[データエンジニア](data-engineer.md)からアクセス権を付与され、環境の準備ができたら、[!DNL Adobe Journey Optimizer] での作業を開始できます。

>[!NOTE]
>
>**実装指示：** [管理者](administrator.md) → [&#x200B; データエンジニア &#x200B;](data-engineer.md) →現在地：**開発者** → [&#x200B; マーケター](marketer.md)
>
>モバイルとwebの統合を実装する前に、[&#x200B; データスキーマとイベント &#x200B;](data-engineer.md)が設定されていることを確認してください。

## Journey Optimizer エコシステムでの役割

他のチームメンバーがユーザーインターフェイスを通じて Journey Optimizer を設定している間、以下に焦点を当てます。

* モバイルアプリケーションと web アプリケーションでの **SDK の実装**
* ジャーニーをトリガーするためのアプリケーションからの&#x200B;**イベントの送信**
* カスタムアクションを通じて Journey Optimizer が呼び出せる **API エンドポイントの作成**
* Journey Optimizer と既存のシステムおよびインフラストラクチャとの&#x200B;**統合**
* 実装の&#x200B;**テストとデバッグ**

[データエンジニア](data-engineer.md)は、データスキーマ、イベント設定およびデータソースを処理します。 [管理者](administrator.md)は、権限とチャネル設定を指定します。 [マーケター](marketer.md)は、実装を使用するジャーニーとコンテンツをデザインします。

このガイドでは、Journey Optimizer を開始するための基本的な技術的実装手順について説明します。 モバイルアプリ、web エクスペリエンス、API 統合のいずれを作成する場合でも、以下の節に従って実装を設定してください。

## 前提条件 {#prerequisites}

実装を開始する前に、以下の点を確認してください。

| カテゴリ | 要件 |
|----------|-------------|
| **技術スキル** | * JavaScript（Web SDK の場合）または Swift／Kotlin（Mobile SDK の場合）の使用経験<br>* RESTful API と JSON に関する理解<br>* 非同期プログラミングとイベント駆動型アーキテクチャに関する知識<br>* 組織のアプリケーションアーキテクチャに関する知識 |
| **アクセスとツール** | * API 資格情報用の [Adobe Developer Console](https://developer.adobe.com){target="_blank"} へのアクセス権<br>* アプリケーションのコードベースへのアクセス権がある開発環境<br>* API テスト用の Postman などのテストツール<br>* ブラウザー開発者ツールまたはモバイルデバッグツール |
| **他のチームメンバーから** | * [管理者](administrator.md)<br>から付与された環境へのアクセス権* [データエンジニア](data-engineer.md)<br>からの XDM スキーマとイベント定義* [マーケター](marketer.md)からの要件とユースケース |

## 技術的な基盤について {#technical-foundation}

実装に進む前に、次のコアとなる技術概念を理解しておきます。

1. **Adobe Experience Platform の統合**：Journey Optimizer は、Adobe Experience Platform でネイティブに作成されています。 基盤となるアーキテクチャを理解すると、より効果的な実装を作成できます。 詳しくは、[Journey Optimizer の仕組み](../understanding-ajo.md)を参照してください。

1. **XDM データモデル**：Journey Optimizer は、エクスペリエンスデータモデル（XDM）を使用して、イベントデータとプロファイルデータを構造化します。 開発者は、[データエンジニア](data-engineer.md)が設定したスキーマに準拠するデータの送信方法を理解する必要があります。 詳しくは、[XDM スキーマ](../../data/get-started-schemas.md)を参照してください。

1. **認証とセキュリティ**：すべての実装に適切な認証が必要です。 SDK と API の認証を設定する方法を理解します。 詳しくは、[API 認証](https://developer.adobe.com/journey-optimizer-apis/references/authentication){target="_blank"}を参照してください。

## モバイルアプリの統合の設定 {#mobile-integration}

### Adobe Experience Platform Mobile SDK の設定

モバイル SDKは、iOSまたはAndroid アプリに直接埋め込むライブラリのコレクションです。 アプリとAdobe Experience Platformの間のコミュニケーション層として機能し、利用者の特定、行動イベントの収集、プッシュ通知、アプリ内メッセージ、パーソナライズされたコンテンツなどの指示をJourney Optimizerから送信します。 この機能がなければ、Journey Optimizerでアプリの利用者が何をしているのかを把握したり、そうした利用者にリーチしたりすることはできません。

1. **Mobile SDK をインストールして設定**：[Adobe Experience Platform Mobile SDK ドキュメント](https://developer.adobe.com/client-sdks/documentation/getting-started){target="_blank"}に従って、SDK 統合を開始します。

1. **モバイルプロパティを作成**：[!DNL Adobe Experience Platform Data Collection] でモバイルプロパティを設定します。 詳しくは、[モバイルプロパティの作成と設定](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property){target="_blank"}方法を参照してください。

1. **プッシュ通知を設定**：
   * **iOS アプリ**&#x200B;の場合：アプリを APNs（Apple プッシュ通知サービス）に登録します。 詳しくは、[Apple のドキュメント](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}を参照してください。
   * **Android アプリ**&#x200B;の場合：Android アプリに Firebase Cloud Messaging を設定します。 詳しくは、[Google のドキュメント](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}を参照してください。

1. **モバイル統合をテスト**：[モバイルオンボーディングのクイックスタートワークフロー](../../push/mobile-onboarding-wf.md)を使用して、モバイル設定を迅速に設定およびテストします。

プッシュ通知を設定する手順について詳しくは、[このページ](../../push/push-configuration.md)を参照してください。

### コードベースのエクスペリエンスの実装（Mobile SDK）

コードベースのエクスペリエンスにより、新しいアプリのリリースを必要とせずに、オンボーディング画面や製品詳細ページ、アプリ内バナーや機能フラグなど、ネイティブモバイルアプリのあらゆるサーフェスにパーソナライズされたコンテンツを配信できます。 モバイルSDKを使用すると、ランタイムにパーソナライズされたコンテンツを取得してレンダリングできるため、チームは配置とプレゼンテーションを完全に制御できます。

* Mobile SDK の実装について詳しくは、[このチュートリアル](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/code-based/tutorial){target="_blank"}に従ってください
* [iOS](https://github.com/adobe/aepsdk-messaging-ios/tree/main/TestApps/MessagingDemoAppSwiftUI){target="_blank"} および [Android](https://github.com/adobe/aepsdk-messaging-android/tree/main/code/testapp){target="_blank"} のサンプル実装を確認します

## Web エクスペリエンスの実装 {#web-implementation}

### Adobe Experience Platform Web SDK の設定

Web SDK （`alloy.js`）は、サイトで必要になる可能性のある個別のJavaScript タグのパッチワークに代わる単一のAdobe ライブラリです。 単一のネットワークで、行動データを収集し、設定したデータストリームを通じてAdobe Experience Platformにストリーミングし、パーソナライゼーションの指示を受け取ります。 adobe Journey Optimizerを導入すれば、訪問者を特定し、その行動にもとづいてカスタマージャーニーをトリガーし、それぞれのページに合わせたコンテンツを迅速に提供できます。

1. **Web SDK をインストール**：[Web SDK 実装ガイド](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"}に従って、web サイトに SDK を設定します。

1. **データストリームを設定**：Journey Optimizer を有効にして、[!DNL Adobe Experience Platform Data Collection] でデータストリームを作成および設定します。 詳しくは、[データストリームドキュメント](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target="_blank"}を参照してください。

1. **Web プッシュ通知を有効にする**（オプション）：Web プッシュ通知が一般提供されるようになりました。 Web SDK 設定で [pushNotifications プロパティ](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/pushnotifications){target="_blank"}を設定し、[sendPushSubscription コマンド](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/sendpushsubscription){target="_blank"}を使用してプッシュ購読を登録します。 [Web プッシュ設定の詳細情報](../../push/push-configuration-web.md)。

### コードベースのエクスペリエンスの実装（Web SDK）

マーケターがレイアウトを完全に制御するビジュアルチャネルとは異なり、コードベースのエクスペリエンスでは、ページにパーソナライズされたコンテンツがどのように表示されるかを完全に管理できます。 Journey Optimizerは、パーソナライゼーションデータを含むJSON ペイロードを返します。コードは、どこにどのように表示するかを決定します。 このモデルは、視覚的なエディターやページ公開ワークフローを必要とせずに、ヒーローバナー、レコメンデーションカルーセル、検索結果ランキング、A/B テストのバリエーションなど、あらゆるweb サーフェスに対応します。

1. **実装方法を選択**：クライアントサイド、サーバーサイド、ハイブリッド。 各アプローチの[実装サンプル](../../code-based/code-based-implementation-samples.md)を確認します。

1. **サーフェスを定義**：パーソナライズされたコンテンツを配信するアプリケーション内の場所を特定します。 詳しくは、[サーフェスの設定](../../code-based/code-based-surface.md)を参照してください。

1. **コンテンツレンダリングを実装**：Web SDK を使用して、パーソナライゼーションコンテンツを取得および適用します。 [コードベースの実装チュートリアル](../../code-based/code-based-decisioning-implementations.md)を参照してください。

1. **表示イベントとインタラクションイベントを送信**：コンテンツが表示されるタイミングと、ユーザーがコンテンツとやり取りするタイミングを追跡して、分析と最適化を行います。

実際のコードベースのエクスペリエンスを確認するには、[GitHub のサンプル実装](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"}を参照してください。

詳しくは、[コードベースのエクスペリエンスの基本を学ぶ](../../code-based/get-started-code-based.md)を参照してください。

## イベントストリーミングの実装 {#event-streaming}

### ジャーニーをトリガーするイベントの送信

ジャーニーは、イベントにもとづいて実行されます。利用者がログインし、カートに商品を追加すると、購入が完了し、フォームが放棄されます。 あなたの仕事は、適切なタイミングでアプリケーションからそれらのイベントを放出することです。 各イベントは、Experience Platform Streaming Ingestion APIに送信されるXDM構造化JSON ペイロードです。Journey Optimizerは、ミリ秒以内にイベントを取得し、プロファイルを任意の一致するジャーニーにルーティングします。 イベントスキーマとペイロード構造は、[&#x200B; データエンジニア &#x200B;](data-engineer.md)によって定義されます。コーディングを開始する前に調整してください。

1. **イベントペイロードを理解**：データエンジニアと連携して、イベントスキーマと必要なペイロード構造を取得します。 ペイロードは、設定した XDM スキーマに準拠する必要があります。 詳しくは、[イベントスキーマ要件](../../event/experience-event-schema.md)を参照してください。

1. **イベントストリーミングを実装**：[Streaming Ingestion API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja){target="_blank"} を使用して、Adobe Experience Platformにイベントを送信します。 詳しくは、[イベントの送信手順](../../event/additional-steps-to-send-events-to-journey.md) を参照してください。

1. **イベントタイプを処理**：
   * **単一イベント**：ユーザー固有のアクション（例：ボタンのクリック、購入完了）に対するイベント送信を実装します
   * **ビジネスイベント**：ビジネス関連のイベント（例：在庫の更新、価格の変更）を送信します

1. **イベント配信をテスト**：イベントが適切に受信され、期待どおりにジャーニーがトリガーされることを確認します。 詳しくは、[イベントのトラブルシューティング](../../building-journeys/troubleshooting-inbound.md)を参照してください。

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

カスタマージャーニーのカスタムアクションのステップに到達すると、Journey Optimizerは、バックエンド、CRM、ロイヤルティプラットフォーム、REST エンドポイントなど、提供したURLに対してアウトバウンド HTTP呼び出しを行います。 あなたの仕事は、エンドポイントを構築して公開することです：リクエストコントラクト（ペイロードの形状、認証方法、応答形式）を定義し、その背後にあるビジネスロジックを実装し、Journey Optimizerが生成するコールボリュームを処理できることを確認します。 次に、[管理者](administrator.md)がエンドポイントをJourney Optimizerに登録し、マーケターがジャーニーのステップとして使用できるようにします。

1. **API エンドポイントを作成**：ジャーニー実行中に Journey Optimizer により呼び出される RESTful API エンドポイントを作成します。 エンドポイントで次の操作を実行する必要があります。
   * JSON ペイロードを受け入れる
   * リクエストを認証（OAuth、API キーまたは JWT）
   * 適切なタイムアウト制限内でリクエストを処理
   * 応答を想定される形式で返す

1. **カスタムアクションの機能を理解**：カスタムアクションは、Epsilon、Slack、Firebase などのサードパーティシステムや独自のサービスに接続できます。 詳しくは、[カスタムアクション](../../action/action.md)を参照してください。

1. **アクション設定を操作**：[管理者](administrator.md)または[データエンジニア](data-engineer.md)は、Journey Optimizer でカスタムアクションを設定し、API エンドポイント URL、認証方法、パラメーターを定義します。 お客様は、API 仕様を管理者またはデータエンジニアに提供してください。 詳しくは、[カスタムアクション設定](../../action/about-custom-action-configuration.md)を参照してください。 オプションの&#x200B;**エラー応答ペイロード**&#x200B;を、タイムアウト／エラー分岐のよりリッチなフォールバックロジックに対して定義できます。

1. **アクションにつながるデータを返す**：後続のジャーニーステップで使用できるデータを返すように API をデザインします。 詳しくは、[アクション応答](../../action/action-response.md)を参照してください。

1. **カスタムアクションの正常性を監視**：カスタムアクション監視ダッシュボードを使用して、呼び出しの成功、エラー、スループット、応答時間、キュー待ち時間を追跡します。 詳しくは、[カスタムアクションレポート](../../action/reporting.md)を参照してください。

1. **レート制限を実装**：エンドポイントが想定されるボリュームを処理できることを確認します。 Journey Optimizer では、1 秒あたり 5000 回の呼び出しの制限が適用されますが、システムは回復力を備えている必要があります。 詳しくは、[キャップとスロットル](../../configuration/external-systems.md)を参照してください。

**ユースケース例**：カスタムアクションを使用して、[ジャーニーイベントを Experience Platform に書き込みます](../../building-journeys/custom-action-aep.md)。

## Journey Optimizer API の操作 {#apis}

Journey Optimizer UIを通じてすべてが行われる必要はありません。 自社のバックエンドから施策をトリガーする、プライバシーリクエストの後にメールアドレスを抑制する、外部のCMSからコンテンツテンプレートを同期させる、といった必要が生じることもあります。 Journey OptimizerのREST APIでは、プラットフォームのコア機能にプログラムでアクセスできます。 すべての呼び出しはOAuth サーバー間認証を使用します。古いJWT メソッドは非推奨です。

1. **API 機能を理解**：Journey Optimizer API を使用すると、様々なリソースをプログラムで作成、読み取り、更新、削除できます。 詳しくは、[Journey Optimizer API](../../configuration/ajo-apis.md) を参照してください。

1. **認証**：[このチュートリアル](https://developer.adobe.com/journey-optimizer-apis/references/authentication){target="_blank"}に従って、Adobe Developer Console を使用して API 認証を設定します。

1. **API リファレンスを探索**：完全な API ドキュメントを参照して、[Adobe Journey Optimizer API リファレンス](https://developer.adobe.com/journey-optimizer-apis){target="_blank"}で API を直接試します。

1. **API トリガーキャンペーン**：API トリガーキャンペーンを使用して、トランザクションメッセージを作成します。 大量のシナリオ（最大 5000 TPS）の場合は、[高スループットモード](../../campaigns/api-triggered-high-throughput.md)を探索します（アドオンライセンスが必要）。

1. **Decision Management API**：オファー管理と決定に専用の API を使用します。 詳しくは、[Decision Management API ガイド](../../offers/api-reference/getting-started.md)を参照してください。

1. **Decisioning 移行 API**：柔軟なスコープ、自動検証、ロールバックのサポートにより、意思決定管理エンティティを Decisioning にプログラムで移行します。 詳しくは、[Decision 移行 API ガイド](../../experience-decisioning/decisioning-migration-api.md)を参照してください。

1. **SMS Webhook**：受信メッセージを取得するように受信 Webhook を設定し、配信レシートとステータス更新を受信するようにフィードバック Webhook を設定します。 [学習を増やす](../../mobile/mobile-webhook.md)。

## テストとデバッグ {#testing}

導入を開始する前に、イベントが適切なタイミングで実行され、ジャーニーが期待どおりにトリガーされ、カスタムアクションが現実的な読み込み中に動作し、パーソナライズされたコンテンツが正しくレンダリングされるという確信が必要です。 このセクションでは、低レベルのSDKのログ記録から、実際のプロファイルを使用したエンドツーエンドのジャーニーテストの実行まで、問題を早期に発見するためのツールとテクニックについて説明します。

1. **SDKの実装をデバッグ**: Adobe Experience Platform Assuranceを使用して、SDK イベントを調べ、データ収集を検証し、統合問題が発生した場合にトラブルシューティングを行います。 [オーディエンスの詳細情報](https://experienceleague.adobe.com/docs/experience-platform/assurance/home.html?lang=ja){target="_blank"}。

1. **イベント配信をテスト**：アプリケーションからのイベントが Adobe Experience Platform により正しく受信され、期待どおりにジャーニーがトリガーされることを確認します。 イベントの取り込みを監視し、ペイロード構造を検証します。

1. **API 統合を検証**：カスタムアクションエンドポイントをテストして、Journey Optimizer リクエストが正しく処理され、タイムアウト制限内に応答し、期待されるデータ形式が返されることを確認します。

1. **テストプロファイルでテストモードを使用**：[データエンジニア](data-engineer.md)と連携してテストプロファイルにアクセスし、ジャーニーテストモードを使用して実装を検証します。 詳しくは、[ジャーニーのテスト](../../building-journeys/testing-the-journey.md)方法を参照してください。

1. **SDK ログを監視**：SDK 実装でデバッグログを有効にして、開発中の問題をトラブルシューティングします。
   * **Mobile SDK**：ログを有効にして、SDK イベントと API 呼び出しを確認します
   * **Web SDK**：ブラウザーコンソールを使用して SDK アクティビティを監視します

1. **データストリームの設定を確認**：データストリームが Journey Optimizer にデータを送信するために正しく設定されていることを確認します。 イベントがデータストリームを通じて正しい宛先にフローされることを確認します。

1. **分析用にジャーニーデータのクエリを実行**：データレイクで SQL クエリを使用して、ジャーニーステップイベントの分析、問題のデバッグ、カスタムアクションのパフォーマンスの監視を行います。 次を含む[ジャーニー分析のクエリ例](../../reports/query-examples.md)を探索します。
   * プロファイルのエントリ／終了のトラッキングと破棄理由
   * カスタムアクションのパフォーマンス指標（待ち時間、スループット、エラー）
   * イベントの配信パターンとエラーパターン
   * ジャーニーインスタンスの状態

## 高度な開発者向けトピック {#advanced-topics}

コア SDK、イベント、APIを導入したら、次のトピックを実行します。プロファイルを肥大化させることなく、実行時にジャーニーデータを強化する、オプトアウトが各統合を通じて伝播するように同意シグナルを処理する、本番環境の拡張に必要なスループットと信頼性に合わせて実装を調整する、といった重要な機能です。

### コンテキストデータとエンリッチメントの操作

一般的に、ジャーニーは、商品名、ロイヤルティ層、注文明細リストなどのイベントをトリガーするのに必要な量よりも多くのデータを必要としています。 コンテキストに基づいたエンリッチメントにより、これらすべてを各プロファイルに事前に読み込むのではなく、AEP データセットから実行時に検索したり、カスタムアクションレスポンスから実行したりすることができます。 メッセージと分岐の条件は、プロファイルに永続的に保存されることなく、そのデータを参照できます。

* **配列を反復処理**：Handlebars 構文を使用して、イベント、カスタムアクション応答およびメッセージ内のデータセット検索からの動的なリストを表示します。 詳しくは、[コンテキストデータの反復処理](../../personalization/iterate-contextual-data.md)を参照してください。
* **データセット参照**：データセット参照を実装して、Adobe Experience Platform データセットからのジャーニーデータを強化します。 設定について詳しくは、データエンジニアと連携してください。 詳しくは、[データセット参照](../../building-journeys/dataset-lookup.md)を参照してください。

### 同意とガバナンスの操作

Journey Optimizerはデータガバナンスと同意ポリシーをプラットフォームレベルで適用しますが、統合ではそれらを尊重する必要があります。 顧客がマーケティングコミュニケーションをオプトアウトした場合、またはデータ使用ラベルがフィールドの使用方法を制限した場合は、UIのブロックアクションだけでなく、カスタムアクションとデータセット参照を通じてこれらのルールを伝播する必要があります。

* **データガバナンス**：カスタムアクションにデータ使用ポリシーを適用します。 詳しくは、[データガバナンス](../../action/action-privacy.md)を参照してください。
* **同意管理**：実装で顧客の同意環境設定を処理します。 詳しくは、[同意](../../action/consent.md)を参照してください。

### 最適化とベストプラクティス

Journey Optimizerの本番環境では、数百万のイベントと1秒間に数千ものジャーニー実行が定期的に処理されます。 これらのリソースは、期待通りに統合を調整するのに役立ちます。たとえば、レート制限を設定する前にレート制限を把握し、ジャーニーの設計で陥りやすい落とし穴を回避して、プロファイルをサイレントにドロップしたり、不透明に失敗するのではなく適切に低下するエラー処理を構築したりすることが重要です。

* **キャップとスロットル**：レート制限を理解し、適切なスロットルを実装します。 詳しくは、[外部システム](../../configuration/external-systems.md)を参照してください。
* **ジャーニーの最適化**：[ジャーニーの最適化](../../building-journeys/optimize.md)のベストプラクティスに従います。
* **エラー処理**：堅牢なエラー処理を実装します。 詳しくは、[エラーコード](../../building-journeys/error-codes-reference.md)および[トラブルシューティングガイド](../../building-journeys/troubleshooting.md)を参照してください。

## Journey Optimizer REST APIの呼び出し {#rest-apis}

SDKやイベントストリーミングを実装するだけでなく、独自のシステムからプログラムでJourney Optimizerを実行することもできます。 完全なAPI リファレンス、OpenAPI仕様、およびコードサンプルは、[Journey Optimizer デベロッパーポータル &#x200B;](https://developer.adobe.com/journey-optimizer-apis){target="_blank"}にあります。

>[!NOTE]
>
>すべての統合では、OAuth サーバー間認証を使用する必要があります。JWT メソッドは非推奨です。 [認証の設定](https://developer.adobe.com/journey-optimizer-apis/references/authentication){target="_blank"}

### API トリガーによるキャンペーンの実行 {#api-triggered}

Interactive Message Execution REST APIを使用して、外部システムからトランザクションメッセージまたはマーケティングメッセージをトリガーします。 エンドポイントを呼び出す前に：

* エンドポイントが呼び出しを受け入れる前に、キャンペーンを&#x200B;**アクティブ化**&#x200B;する必要があります。
* 呼び出しのタイムアウトは&#x200B;**60秒**&#x200B;です。内部再試行は予期しないタイムアウトを処理します。
* キャンペーンの開始日/終了日が設定されている場合、それらの日付以外のAPI呼び出しは失敗します。
* ペイロードを作成するには、Journey Optimizer UIのライブキャンペーンの&#x200B;**cURL リクエスト** セクションから、生成されたサンプル cURL リクエストを取得します。このリクエストには、そのキャンペーンのすべてのパーソナライゼーション変数が含まれます。
* 標準キャンペーンと[&#x200B; ハイスループットキャンペーン &#x200B;](../../campaigns/api-triggered-high-throughput.md)では、異なるエンドポイントを使用しています。

[API リファレンス &#x200B;](https://developer.adobe.com/journey-optimizer-apis/references/messaging){target="_blank"} ・ [&#x200B; コードサンプル &#x200B;](https://developer.adobe.com/journey-optimizer-apis/references/messaging-samples){target="_blank"} ・ [API トリガーキャンペーンの操作](../../campaigns/api-triggered-campaigns.md)

### 外部エンドポイントのキャッピングとスロットル {#capping-throttling}

ジャーニーがカスタムアクションまたはデータソースを介して外部システムを呼び出す場合、Capping APIとThrottling APIは、これらのシステムを過負荷から保護します。 キャッピングは、設定された制限を超える呼び出しを拒否します。スロットルキューは最大6時間待機します（実稼動サンドボックス、カスタムアクションのみ）。

[Capping API リファレンス &#x200B;](https://developer.adobe.com/journey-optimizer-apis/references/journeys-throttling){target="_blank"} ・ [Capping APIの操作](../../configuration/capping.md) ・ [&#x200B; スロットル APIの操作](../../configuration/throttling.md)

### その他のREST API {#more-rest-apis}

Journey Optimizerでは、メッセージとキャッピングの枠を超えて、抑制管理、コンテンツテンプレート、キャンペーン検索、プルーフ、キャンペーン実行のオーケストレーションなど、REST エンドポイントを活用できます。 データプル後にアドレスを一括抑制したり、外部コンテンツパイプラインからテンプレートを同期したりするなど、UIで手作業が必要な操作を自動化する必要がある場合に使用します。

| 連携の強化 | API リファレンス |
| ------------------- | ------------- |
| 電子メールアドレスまたはドメインをプログラムで送信から除外 | [抑制API](https://developer.adobe.com/journey-optimizer-apis/references/suppression){target="_blank"} ・ [抑制リストを管理](../../configuration/manage-suppression-list.md) |
| 監査または外部同期用にジャーニーのメタデータを取得 | [ジャーニー API](https://developer.adobe.com/journey-optimizer-apis/references/journeys-retrieve){target="_blank"} |
| 外部パイプラインからのコンテンツテンプレートとフラグメントの作成と管理 | [&#x200B; コンテンツ API](https://developer.adobe.com/journey-optimizer-apis/references/content){target="_blank"} ・ [&#x200B; テンプレート &#x200B;](../../content-management/content-templates.md) ・ [&#x200B; フラグメント &#x200B;](../../content-management/fragments.md) |
| アクションキャンペーンの取得とフィルタリング | [&#x200B; キャンペーン API](https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve){target="_blank"} |
| 施策をプレビューし、プログラムにより校正を送信する | [&#x200B; シミュレーション API](https://developer.adobe.com/journey-optimizer-apis/references/simulations){target="_blank"} |

>[!NOTE]
>
>シミュレーション APIは、API トリガーおよびアクション（スケジュール済み）キャンペーンで使用できます。 オーケストレーションされたキャンペーンでは&#x200B;**はサポートされていません**：代わりに、オーケストレーションされたキャンペーンのユーザーインターフェイスでプレビューとプルーフのワークフローを使用します。

| データセットとトリガーオーケストレーションされたキャンペーンの実行の検証| [&#x200B; データセットの検証](https://developer.adobe.com/journey-optimizer-apis/references/orchestrated-campaign-dataset){target="_blank"} ・ [トリガー](https://developer.adobe.com/journey-optimizer-apis/references/oc-trigger){target="_blank"} ・ [&#x200B; データセットを有効にする](../../orchestrated/manual-schema.md) |

## その他のリソース {#additional-resources}

* **Developer Console**：[Adobe Developer Console](https://developer.adobe.com){target="_blank"} にアクセスして統合を作成し、API 資格情報を管理します。
* **サンプルコード**：[GitHub のサンプル実装](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"}を探索します。
* **チュートリアルビデオ**：[Experience League](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html?lang=ja){target="_blank"} の実践的なチュートリアルを通じて学びます。
* **開発者コミュニティ**：アドビコミュニティフォーラムで、他の開発者とつながり、サポートを受けることができます。

## 役割をまたいだ共同作業 {#next-steps}

実装作業は、次の他のチームメンバーと連携します。

>[!BEGINTABS]

>[!TAB データエンジニアとの連携]

データとイベントの設定について[&#x200B; データエンジニア &#x200B;](data-engineer.md)と共同作業を行います。 ユーザーの行動に反応するジャーニーは、送信するイベントによって異なります。データエンジニアがスキーマを定義し、スキーマを生成するコードを実装します。

* 実装に必要な[XDM スキーマ &#x200B;](../../data/get-started-schemas.md)とイベント構造を取得します
* 送信する必要があるイベントと必要なペイロード形式について説明します。[&#x200B; ジャーニーイベントの操作](../../event/about-events.md)を参照してください。
* 各イベントペイロードで必須フィールドとオプションのフィールド、および期待されるフィールドが見つからないか形式が正しくない場合にジャーニーで何が起こるかを確認します。[&#x200B; スキーマ要件](../../event/experience-event-schema.md#schema-requirements)を参照してください。
* [Adobe Experience Platform Assurance](https://experienceleague.adobe.com/docs/experience-platform/assurance/home.html?lang=ja){target="_blank"}を使用して、イベント配信とデータ取り込みをテストします

>[!TAB 管理者との連携]

アクセスとチャネルの設定について、[管理者](administrator.md)と共同作業を行います。 ジャーニーは、管理者が設定したチャネルを通じてのみユーザーにリーチできます。早期に調整することで、SDKの作業と設定を同期させることができます。

* Journey Optimizerで設定する[&#x200B; カスタムアクション &#x200B;](../../action/about-custom-action-configuration.md)のAPI仕様を指定します
* [Adobe Developer Console](https://developer.adobe.com){target="_blank"}経由で必要な権限とAPI資格情報をリクエストする
* チャネル設定要件に関する調整 – [iOS](../../push/push-configuration.md)およびAndroidのプッシュ証明書、[web プッシュ &#x200B;](../../push/push-configuration-web.md)設定、[SMS webhook](../../mobile/mobile-webhook.md) エンドポイント
* [&#x200B; ジャーニーテストモード &#x200B;](../../building-journeys/testing-the-journey.md)を実行する前に、サンドボックス戦略とテスト環境を調整します

>[!TAB マーケターとの連携]

ジャーニーの設計とテストに関して[&#x200B; マーケター](marketer.md)と共同作業を行います。 マーケターは、送信するイベントと公開するサーフェスに完全に依存するジャーニーとコンテンツを構築します。近ければ近いほど、ジャーニーはより迅速に開始されます。

* [Journey Optimizer](../../building-journeys/journey.md)のジャーニーデザインを一緒に確認して、どのユーザーインタラクションがイベントをトリガーする必要があり、どのサーフェスがパーソナライズを必要としているかを把握します
* マーケターが[&#x200B; コンテンツのパフォーマンスとユーザーエンゲージメント &#x200B;](../../reports/report-gs-cja.md)を測定できるようにトラッキングを実装します
* テストプロファイルを使用して[&#x200B; ジャーニーテストモード &#x200B;](../../building-journeys/testing-the-journey.md)を一緒に実行し、エンドツーエンドでフルフローを検証します
* メッセージ配信、パーソナライゼーションのレンダリングまたは[&#x200B; カスタムアクション &#x200B;](../../action/action.md)応答に関する問題のトラブルシューティング

>[!ENDTABS]

## 実装の開始

作成を開始する準備は整っていますか？ 上記の節から最初の実装領域を選択します。

1. **モバイルアプリですか？** [Mobile SDK 統合](#mobile-integration)から開始します
2. **Web サイトですか？** [Web SDK 設定](#web-implementation)から開始します
3. **API 統合ですか？** [API の操作](#apis)にジャンプします
4. **カスタムシステムですか？** [カスタムアクション](#custom-actions)を確認します

各節には、実装をガイドする詳細な技術ドキュメント、コードサンプル、チュートリアルへのリンクが含まれています。

## その他のロールガイド {#other-role-guides}

| 役割 | ガイド |
|------|-------|
| 管理者 | [管理者の基本を学ぶ](administrator.md) |
| データエンジニア | [&#x200B; データエンジニア向けの基本を学ぶ](data-engineer.md) |
| 開発者 | [開発者向けの基本を学ぶ](developer.md) |
| マーケター | [マーケター向けの基本を学ぶ](marketer.md) |

[役割と責任の概要](../quick-start.md)に戻る・ [に戻る開始](../../../rp_landing_pages/get-started-landing-page.md)

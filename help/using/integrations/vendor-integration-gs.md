---
solution: Journey Optimizer
product: journey optimizer
title: ベンダーとの連携
description: 有効なAPIを公開する外部プラットフォームとAdobe Journey Optimizerの統合に加えて、エンジニアリングでテストされたベンダーパターンを使用して、設定の設計時に確実に機能します。
feature: Integrations
topic: Content Management
role: User
level: Intermediate
keywords: 統合、ベンダー、サードパーティ
subfeature_v2: []
feature_v2: id: fe96aceb-8194-4a8a-a6b0-75302d02804d
source-git-commit: 6dbdae6edd95d97e039565ed5c6e3cab9f4a19d8
workflow-type: tm+mt
source-wordcount: 401
ht-degree: 0%

---


# ベンダーとの連携 {#vendor-integration}

>[!BEGINSHADEBOX]

**このページでは、** サンプルを参照してください。Adobeがテストした、コンテンツ、ロイヤルティ、レコメンデーション、データおよび同意プラットフォームをまたいでAdobe Journey Optimizerとの連携をサード パーティ ベンダーに接続するための構成をテストしました。

>[!ENDSHADEBOX]

Adobe Journey Optimizerで&#x200B;**Integrations**&#x200B;を使用して、各システムがユースケースに適した&#x200B;**API エンドポイント**&#x200B;を公開し、Integrationsがリクエストを発行し、応答を消費する方法と互換性がある場合、HTTP **経由で**&#x200B;外部システムを呼び出すことができます。 完全なワークフローについては、[統合の操作](integrations.md)を参照してください。

記載されているサードパーティソリューションのリストは、網羅的ではなく例示です。 その他のプラットフォームは、製品要件を満たす場合に使用できます。

## 運用ガードレール {#operational-guardrails}

このガイドまたは類似のベンダーで統合を設定する場合は、次の手順を適用します。

* **応答形式：**&#x200B;統合は、**JSON**&#x200B;または&#x200B;**HTML**&#x200B;の応答からフィールドをマッピングします。 オーサリング時にマッピングに適したJSONまたはHTMLをAPIが返すように呼び出しをデザインします。
* **ペイロードとフィールド：**&#x200B;要求して、必要な属性のみをマッピングします。 応答が小さいほど、遅延が短縮され、機密データの公開も制限されます。
* **エンドポイントの形状：**&#x200B;製品がターゲット検索を想定している場合、ブロックリストまたはページネーションのエンドポイントよりも、安定した&#x200B;**単一リソース**&#x200B;の取得（例えば、1つのエントリ、製品、またはメンバー）を優先します。 [制限と除外事項](#limitations-exclusions)および[統合の操作](integrations.md)を参照してください。
* **ボリュームと信頼性：** ベンダーの&#x200B;**レート制限**&#x200B;を尊重します。 チャネルの&#x200B;**タイムアウト**、**再試行**&#x200B;および&#x200B;**キャッシュ** ポリシーを設定し（バッチメールとトランザクション送信など）、読み込み中に検証します。
* **セキュリティ：**&#x200B;組織のポリシーに従って、トークン、API キー、OAuth資格情報を保存および回転します。 メッセージコンテンツにシークレットを埋め込まないでください。


## 制限と除外事項 {#limitations-exclusions}

サードパーティのソリューション リストは&#x200B;**illustrative**&#x200B;で、すべてを網羅しているわけではありません。 ベンダーAPI、ホスト、レート制限、JSONまたはHTMLのレスポンスの形状が変化する可能性があります。 エンドポイント、認証、フィールドマッピングを、ベンダーの現在のドキュメントとサブスクリプションで確認します。 このパターンは、パーソナライゼーションに適した&#x200B;**読み取り指向**&#x200B;呼び出しを想定しています。 統合では、**JSON**&#x200B;および&#x200B;**HTML**&#x200B;の応答からのマッピングのみがサポートされています。 **書き戻し**、**バッチ書き出し**、およびその他の形式の応答はサポートされていません。

## クイックナビゲーション {#quick-navigation}

以下のグループ化されたリンクを使用して、関連するベンダーパターンにすばやく移動できます。

* **コンテンツ管理システム：** [Contentful](vendor-integration.md#contentful)、[Sitecore](vendor-integration.md#sitecore)、[Salsify](vendor-integration.md#salsify)、[Contentstack](vendor-integration.md#contentstack)、[Akeneo](vendor-integration.md#akeneo)、[Magnolia](vendor-integration.md#magnolia)
* **ロイヤルティと報酬：** [Voucherify](vendor-integration.md#voucherify)、[Talon.One](vendor-integration.md#talon-one)、[Antavo](vendor-integration.md#antavo)、[Salesforce ロイヤルティ ](vendor-integration.md#salesforce-loyalty)、[ キャピラリー](vendor-integration.md#capillary)
* **テンプレート、パーソナライズとレコメンデーション：** [Stensul](vendor-integration.md#stensul)、[Marigold](vendor-integration.md#marigold)、[Adobe Targetのレコメンデーション ](vendor-integration.md#adobe-target-recommendations)
* **データ、天気、および操作：** [AccuWeather](vendor-integration.md#accuweather)、[ShipStation](vendor-integration.md#shipstation)、[RevenueCat](vendor-integration.md#revenuecat)、[Databricks](vendor-integration.md#databricks)
* **レビュー、同意、およびソーシャル：** [Bynder](vendor-integration.md#bynder)、[Trustpilot](vendor-integration.md#trustpilot)、[Bazaarvoice](vendor-integration.md#bazaarvoice)、[OneTrust](vendor-integration.md#onetrust)、[Meta](vendor-integration.md#meta)、[Aprimo](vendor-integration.md#aprimo)、[Epsilon （Epsilon3） ](vendor-integration.md#epsilon)

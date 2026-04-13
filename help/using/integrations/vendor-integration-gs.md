---
solution: Journey Optimizer
product: journey optimizer
title: ベンダーとの連携
description: 有効なAPIを公開する外部プラットフォームとAdobe Journey Optimizerの統合に加えて、エンジニアリングでテストされたベンダーパターンを使用して、設定の設計時に確実に機能します。
feature: Integrations
topic: Content Management
role: User
level: Intermediate
hide: true
keywords: 統合、ベンダー、サードパーティ
source-git-commit: 3733c9ab401f85b22e1d6e07dbf4db535ff8a96d
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---


# ベンダーとの連携を始める {#vendor-integration}

>[!BEGINSHADEBOX]

目次：

* [統合の操作](external-sources.md)
* **[ベンダー統合の基本を学ぶ](vendor-integration-gs.md)**
* [利用可能なベンダー](vendor-integration.md)
* [FAQ](vendor-integration-faq.md)

>[!ENDSHADEBOX]

Adobe Journey Optimizerで&#x200B;**Integrations**&#x200B;を使用して、各システムがユースケースに適した&#x200B;**API エンドポイント**&#x200B;を公開し、Integrationsがリクエストを発行し、応答を消費する方法と互換性がある場合、HTTP **経由で**&#x200B;外部システムを呼び出すことができます。 完全なワークフローについては、[統合の操作](external-sources.md)を参照してください。

記載されているサードパーティソリューションのリストは、網羅的ではなく例示です。 その他のプラットフォームは、製品要件を満たす場合に使用できます。

## 運用ガードレール {#operational-guardrails}

このガイドまたは類似のベンダーで統合を設定する場合は、次の手順を適用します。

* **応答形式：**&#x200B;統合は、**JSON**&#x200B;の応答からフィールドをマッピングします。 オーサリング時にマッピングに適したJSONをAPIが返すように呼び出しをデザインします。
* **ペイロードとフィールド：**&#x200B;要求して、必要な属性のみをマッピングします。 応答が小さいほど、遅延が短縮され、機密データの公開も制限されます。
* **エンドポイントの形状：**&#x200B;製品がターゲット検索を想定している場合、ブロックリストまたはページネーションのエンドポイントよりも、安定した&#x200B;**単一リソース**&#x200B;の取得（例えば、1つのエントリ、製品、またはメンバー）を優先します。 [制限と除外事項](#limitations-exclusions)および[統合の操作](external-sources.md)を参照してください。
* **ボリュームと信頼性：** ベンダーの&#x200B;**レート制限**&#x200B;を尊重します。 チャネルの&#x200B;**タイムアウト**、**再試行**&#x200B;および&#x200B;**キャッシュ** ポリシーを設定し（バッチメールとトランザクション送信など）、読み込み中に検証します。
* **セキュリティ：**&#x200B;組織のポリシーに従って、トークン、API キー、OAuth資格情報を保存および回転します。 メッセージコンテンツにシークレットを埋め込まないでください。

## 制限と除外事項 {#limitations-exclusions}

サードパーティのソリューション リストは&#x200B;**illustrative**&#x200B;で、すべてを網羅しているわけではありません。 ベンダーAPI、ホスト、レート制限、JSON応答シェイプは変更される可能性があります。 エンドポイント、認証、フィールドマッピングを、ベンダーの現在のドキュメントとサブスクリプションで確認します。 このパターンは、パーソナライゼーションに適した&#x200B;**読み取り指向**&#x200B;呼び出しを想定しています。 書き戻し、バッチ書き出し、またはJSON以外の応答は、明記されていない限りスコープ外になる可能性があります。

## クイックナビゲーション {#quick-navigation}

以下のグループ化されたリンクを使用して、関連するベンダーパターンにすばやく移動できます。

* **コンテンツとCMS:** [Contentful](#contentful)、[Sitecore](#sitecore)、[Salsify](#salsify)、[Contentstack](#contentstack)、[Akeneo](#akeneo)、[Magnolia](#magnolia)
* **ロイヤルティと報酬：** [Voucherify](#voucherify)、[Talon.One](#talon-one)、[Antavo](#antavo)、[Salesforce ロイヤルティ &#x200B;](#salesforce-loyalty)、[&#x200B; キャピラリー](#capillary)
* **テンプレートとメッセージ：** [Stensul](#stensul)、[Marigold](#marigold)、[Adobe Target Recommendations](#adobe-target-recommendations)
* **データ、天気、および操作：** [AccuWeather](#accuweather)、[ShipStation](#shipstation)、[RevenueCat](#revenuecat)、[Databricks](#databricks)
* **レビュー、同意、およびソーシャル：** [Bynder](#bynder)、[Trustpilot](#trustpilot)、[Bazaarvoice](#bazaarvoice)、[OneTrust](#onetrust)、[Meta](#meta)、[Aprimo](#aprimo)、[Epsilon （Epsilon3） &#x200B;](#epsilon)

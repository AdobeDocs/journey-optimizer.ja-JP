---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer API の使用
description: Journey Optimizer には、アプリケーションの主要な操作をプログラムで実行できる RESTful API が用意されています。アクセス方法と使用方法について説明します。
feature: Integrations, Data Ingestion
role: Developer
level: Intermediate
exl-id: 4c897c52-6eb2-4d6e-aaa9-9bd83608b2b6
source-git-commit: 7864012ad148c2e52bc38598016e7bd7fac9644e
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 39%

---

# [!DNL Journey Optimizer] API の操作 {#apis-gs}

## クイックアクセス {#quick-access}

[ 完全な API リファレンス ](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"} を参照して、すべてのJourney Optimizer API にアクセスし、直接テストします。 開始するには、必ず [ 認証を設定 ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} して、必要な資格情報を収集します。

## 概要 {#overview}

Adobe Journey Optimizer API を使用すると、任意のアプリ、デバイス、チャネルをまたいで、パーソナライズおよび接続されたタイムリーな顧客体験を提供し、エンドツーエンドのカスタマージャーニーを効果的に管理できます。カスタマージャーニーは、顧客がブランドに最初に接触してから離れるまでの、やり取りのプロセス全体を表します。このジャーニーは、認知フェーズから開始します。このフェーズでは、顧客はブランドを知り、エンゲージメントを開始します。その後、顧客はブランドとやり取りし、オンラインショップや実店舗の訪問、購入、メッセージの送信、レビューの投稿を行います。

Adobe Journey Optimizer は、Adobe Experience Platform にネイティブに構築されており、統合されたリアルタイム顧客プロファイル、API ファーストのオープンなフレームワーク、一元化されたオファー決定支援、人工知能（AI）と機械学習（ML）を組み合わせて、パーソナライゼーションと最適化を実現します。Journey Optimizer API と統合することで、ブランドは、カスタマージャーニーをまたいで、スケール、速度、柔軟性を備えた次善のインタラクションをインテリジェントに判断できます。

**Journey Optimizer API の概要：**

* **[完全な API リファレンスを参照 ](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}** – すべてのJourney Optimizer API にアクセスして直接テストする
* **[認証の設定 ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}** - API の使用を開始するために必要な資格情報を収集します
* **[意思決定管理 API](../offers/api-reference/getting-started.md)** - オファーと決定をプログラムで管理します
* **[Experience Decisioning API](../experience-decisioning/api-reference/getting-started.md)** - コードベースのエクスペリエンスを使用してパーソナライズされた決定項目を配信します

## 認証 {#authentication}

Journey Optimizer API を使用する前に、API エンドポイントにアクセスするための認証を設定する必要があります。

[ 認証ガイド ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} に従って、すべてのJourney Optimizer API に必要な認証資格情報を収集します。

## API ドキュメント {#api-documentation}

完全なAdobe Journey Optimizer API ドキュメントには、使用可能なすべてのエンドポイント、リクエスト/応答の形式、インタラクティブテスト機能に関する詳細が含まれています。

[Adobe Journey Optimizer API ドキュメントにアクセスし ](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}**API リファレンス** メニューを参照して、使用可能なすべての API を確認します。

## 意思決定管理 API {#decision-management-apis}

Journey Optimizerには、意思決定管理の専用 API が用意されており、オファー、決定およびプレースメントをプログラムで管理できます。

Offer Decisioning API の使用を開始するには、[ 意思決定管理 API デベロッパーガイド ](../offers/api-reference/getting-started.md) を参照してください。

## Experience Decisioning API {#experience-decisioning-apis}

Journey Optimizerは、コードベースのエクスペリエンスを通じてパーソナライズされた意思決定項目を配信するための Experience Decisioning API も提供します。 Experience Decisioning では、決定項目、実施要件ルール、選択戦略を使用したパーソナライゼーションのシンプルなアプローチを提供します。

**使用可能な API 操作：**

* **決定項目** – 決定項目を作成、読み取り、更新、削除します
* **選択戦略** – 決定項目の選択およびランク付けの方法を定義します
* **実施要件ルール** – 品目実施要件の条件を設定します
* **項目コレクション** – 決定項目をコレクションに整理します
* **ランキング式** - カスタムランキングロジックの設定
* **プレースメント** – 決定項目を表示できる場所を定義します

詳しくは、[Experience Decisioning API リファレンス ](../experience-decisioning/api-reference/getting-started.md) を参照し、[ コードベースのエクスペリエンスを使用してオファーを配信 ](../experience-decisioning/gs-experience-decisioning.md) する方法を確認してください。

## 関連トピック {#related-topics}

**API ドキュメントとガイド**

* [Adobe Journey Optimizer API リファレンス ](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}
* [ 認証ガイド ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}
* [意思決定管理 API デベロッパーガイド](../offers/api-reference/getting-started.md)
* [Experience Decisioning API リファレンス](../experience-decisioning/api-reference/getting-started.md)

**Journey Optimizerの統合**

* [Adobe Analyticsの統合](../integrations/integration-ajo-analytics.md)
* [Adobe Targetの統合](../integrations/integration-ajo-target.md)
* [Adobe Campaignの統合](../building-journeys/using-adobe-campaign-v7-v8.md)

**開発者向けリソース**

* [Adobe Experience Platform API](https://developer.adobe.com/experience-platform-apis/){target="_blank"}
* [Adobe 開発者コンソール](https://developer.adobe.com/console){target="_blank"}
* [ジャーニーのカスタムアクション](../action/about-custom-action-configuration.md)

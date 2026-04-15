---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer API の使用
description: Journey Optimizer には、アプリケーションの主要な操作をプログラムで実行できる RESTful API が用意されています。アクセス方法と使用方法について説明します。
feature: Integrations, Data Ingestion
role: Developer
level: Intermediate
exl-id: 4c897c52-6eb2-4d6e-aaa9-9bd83608b2b6
source-git-commit: 0a2c384faea70dcbc9b99596740e375d85b2bc64
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 98%

---

# [!DNL Journey Optimizer] API の操作 {#apis-gs}

## クイックアクセス {#quick-access}

[完全な API リファレンス](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}を参照して、すべての Journey Optimizer API にアクセスし、直接テストします。開始するには、必ず[認証を設定](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}して、必要な資格情報を収集します。

## 概要 {#overview}

Adobe Journey Optimizer API を使用すると、任意のアプリ、デバイス、チャネルをまたいで、パーソナライズおよび接続されたタイムリーな顧客体験を提供し、エンドツーエンドのカスタマージャーニーを効果的に管理できます。カスタマージャーニーは、顧客がブランドに最初に接触してから離れるまでの、やり取りのプロセス全体を表します。このジャーニーは、認知フェーズから開始します。このフェーズでは、顧客はブランドを知り、エンゲージメントを開始します。その後、顧客はブランドとやり取りし、オンラインショップや実店舗の訪問、購入、メッセージの送信、レビューの投稿を行います。

Adobe Journey Optimizer は、Adobe Experience Platform にネイティブに構築されており、統合されたリアルタイム顧客プロファイル、API ファーストのオープンなフレームワーク、一元化されたオファー決定支援、人工知能（AI）と機械学習（ML）を組み合わせて、パーソナライゼーションと最適化を実現します。Journey Optimizer API と統合することで、ブランドは、カスタマージャーニーをまたいで、スケール、速度、柔軟性を備えた次善のインタラクションをインテリジェントに判断できます。

**Journey Optimizer API の基本を学ぶ：**

* **[完全な API リファレンスの参照](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}** - すべての Journey Optimizer API にアクセスし、直接テストします
* **[認証の設定](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}** - API の使用を開始するために必要な資格情報を収集します
* **[Decision Management API](../offers/api-reference/getting-started.md)** - オファーと決定をプログラムで管理します
* **[Experience Decisioning API](../experience-decisioning/api-reference/getting-started.md)** - コードベースのエクスペリエンスを使用してパーソナライズされた決定項目を配信します

## 認証 {#authentication}

Journey Optimizer API を使用する前に、API エンドポイントにアクセスするための認証を設定する必要があります。

[認証ガイド](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}に従って、すべての Journey Optimizer API に必要な認証資格情報を収集します。

## API ドキュメント {#api-documentation}

完全な Adobe Journey Optimizer API ドキュメントには、使用可能なすべてのエンドポイント、リクエスト／応答の形式、インタラクティブなテスト機能に関する詳細情報が含まれています。

[Adobe Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}にアクセスし、**API リファレンスメニュー**&#x200B;を参照して、使用可能なすべての API を探索します。

## 意思決定管理api {#decision-management-apis}

Journey Optimizer には、意思決定管理専用の API が用意され、オファー、決定、プレースメントをプログラムで管理できます。

Offer Decisioning API の使用を開始するには、[意思決定管理 API 開発者ガイド](../offers/api-reference/getting-started.md)を参照してください。

## エクスペリエンス決定API {#experience-decisioning-apis}

Journey Optimizer には、コードベースのエクスペリエンスを通じてパーソナライズされた決定項目を配信するための Experience Decisioning API も用意されています。エクスペリエンス決定には、決定項目、実施要件ルール、選択戦略を使用して、簡素化されたパーソナライゼーションアプローチが用意されています。

**使用可能な API 操作：**

* **決定項目** - 決定項目を作成、読み取り、更新、削除します
* **選択戦略** - 決定項目を選択およびランク付けする方法を定義します
* **実施要件ルール** - 項目の実施要件の条件を設定します
* **項目コレクション** - 決定項目をコレクションに整理します
* **ランキング式** - カスタムランキングロジックを設定します
* **プレースメント** - 決定項目を表示できる場所を定義します

詳しくは、[Experience Decisioning API リファレンス](../experience-decisioning/api-reference/getting-started.md)を参照し、[コードベースのエクスペリエンスを使用してオファーを配信](../experience-decisioning/gs-experience-decisioning.md)する方法を確認してください。

## 関連トピック {#related-topics}

**API ドキュメントとガイド**

* [Adobe Journey Optimizer API リファレンス](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}
* [認証ガイド](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}
* [意思決定管理 API 開発者ガイド](../offers/api-reference/getting-started.md)
* [Experience Decisioning API リファレンス](../experience-decisioning/api-reference/getting-started.md)

**Journey Optimizer の統合**

* [他のソリューションとの統合](../integrations/ajo-integrations.md)
* [Adobe Analytics との統合](../event/about-analytics.md)
* [Adobe Campaign の統合](../building-journeys/using-adobe-campaign-v7-v8.md)

**開発者向けリソース**

* [Adobe Experience Platform API](https://developer.adobe.com/experience-platform-apis/){target="_blank"}
* [Adobe Developer Console](https://developer.adobe.com/console){target="_blank"}
* [ジャーニーのカスタムアクション](../action/about-custom-action-configuration.md)

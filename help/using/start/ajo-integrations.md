---
solution: Journey Optimizer
product: journey optimizer
title: 他のソリューションとの統合
description: Journey Optimizerを他のソリューションと統合する方法の詳細
topic: Content Management
role: User
level: Intermediate
exl-id: 700dc66e-ae2d-418f-b75e-ece15af57ab3
source-git-commit: 90d7d4d39fe04198707be3d5b24888cfe5bed308
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 19%

---

# 他のソリューションとの統合 {#integration}

Adobe Journey Optimizerを使用すると、このデータを容易に管理、保持、およびテクノロジースタックの一部であるプラットフォームやシステムに書き出すことができます。 これらの統合は、特定の使用例に対処し、Adobe Journey Optimizerの機能範囲を拡張するのに役立ちます。

>[!NOTE]
>
> Adobe Experience Platformを基に構築されたAdobe Journey Optimizerは、 [Adobeのリアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target=&quot;_blank&quot;}。 この組み込みデータソースは事前に設定されており、リアルタイム顧客プロファイルからデータを取得して使用するように設計されています（例えば、ジャーニーにエントリした人がクライアントかどうかを確認します）。 プロファイルデータとエクスペリエンスイベントデータを使用できます。[詳細情報](../datasource/adobe-experience-platform-data-source.md)。

## Adobe Customer Journey Analytics{#integration-cja}

Customer Journey Analyticsを使用して、Journey Optimizerで生成されたデータに対して高度な分析を実行できます。

Journey Optimizerは、Adobe Experience Platformにデータを保存します。また、Customer Journey Analyticsは、すべてのジャーニー、キャンペーン、オファーの全体像を提供し、自動レポート配信とデータのカスタムビジュアライゼーションを提供します。

Journey Optimizerでジャーニーを作成した後、Customer Journey Analyticsは、プラットフォームからデータを取り込んでレポートを開始し、顧客がジャーニーとやり取りするたびの影響を把握できます。

詳細情報： [Journey Optimizer +Customer Journey Analytics](../reports/cja-ajo.md).

## Adobe Analytics{#integration-aa}

既にキャプチャし、Adobe Experience PlatformにストリーミングしているAdobe Analyticsのすべての行動イベントデータを活用して、トリガーのリアルタイムジャーニーを促進し、顧客のエクスペリエンスを自動化できます。 このデータは、Journey Optimizerを使用してエンゲージ可能なセグメントの作成にも使用できます。

詳細情報： [Journey Optimizer + Analytics](../event/about-analytics.md).

## Adobe インテリジェントサービス{#integration-intelligent-service}

Adobeインテリジェントサービスは、リアルタイム顧客データプラットフォームにネイティブで、顧客体験の使用例で人工知能と機械学習の機能を活用できます。 これにより、マーケティングアナリストは、データサイエンスの専門知識がなくても、ビジネスレベルの設定を使用して、会社のニーズに固有の予測を設定できます。

顧客 AI を使用すると、企業は、チャーンやコンバージョンの機械学習に基づくスコアを作成できます。このスコアは、Adobe Experience Platformのプロファイル属性として使用でき、ジャーニーのパーソナライズに使用できます。

[詳細情報](../building-journeys/ai-services-overview.md)。


## Adobe Campaign{#integration-ac}

統合は、Adobe Campaign v7 または v8 がある場合に使用できます。この統合を使用して、Adobe Campaignトランザクションメッセージ機能を使用して E メール、プッシュ通知、SMS を送信します。

詳細情報： [Journey Optimizer + Campaign](../building-journeys/ajo-ac.md).

また、ジャーニーでメッセージを送信するAdobe Campaign Standardとの統合を設定することもできます。

詳細情報： [Journey Optimizer +Campaign Standard](../building-journeys/ajo-ac.md).

## カスタムチャネル{#integration-custom}

サードパーティのシステムを使用してメッセージを送信する場合、またはジャーニーからサードパーティのシステムに API 呼び出しを送信する場合は、カスタムアクションを使用してジャーニーに接続します。 例えば、カスタムアクションを使用して次のシステムに接続できます。エプシロン、Slack、 [Adobe Developer](https://developer.adobe.com/){target=&quot;_blank&quot;}、Firebase など

カスタムアクションは、技術ユーザーが定義し、マーケターが使用できる追加のアクションです。設定が完了すると、ジャーニーの左側のパレットに表示されます。 **[!UICONTROL アクション]** カテゴリ。 詳しくは、[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

詳細情報： [カスタムアクション](../action/about-custom-action-configuration.md).

## 外部データソース{#integration-external-systems}

Journey Optimizer では、カスタムデータソースとカスタムアクションを使用して、外部システムへの接続を設定できます。 これにより、例えば、外部の予約システムからのデータでジャーニーをエンリッチメントできます。

外部データソースを使用して、でサードパーティシステムへの接続を定義する方法を説明します。 [この節](../datasource/external-data-sources.md).

---
solution: Journey Optimizer
product: journey optimizer
title: 他のソリューションとの統合
description: Journey Optimizer を他のソリューションと統合する方法を学ぶ
topic: Content Management
role: User
level: Intermediate
exl-id: 700dc66e-ae2d-418f-b75e-ece15af57ab3
source-git-commit: 14b081fbc1d824664c82e6af262a0a7e50764c0c
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 98%

---

# 他のソリューションとの統合 {#integration}

Adobe Journey Optimizer を使用すると、このデータを簡単に管理、保持し、テクノロジースタックの一部であるプラットフォームやシステムに書き出すことができます。これらの統合は、特定の使用例に対処し、Adobe Journey Optimizer の機能範囲を拡張するのに役立ちます。

>[!NOTE]
>
> Adobe Experience Platform 上に作成された Adobe Journey Optimizer は、[Adobe リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}にネイティブに接続されています。この組み込みのデータソースは事前に設定されており、リアルタイム顧客プロファイルからデータを取得して使用するように設計されています（例えば、ジャーニーに参加したユーザーがクライアントであるかどうかを確認します）。 プロファイルデータとエクスペリエンスイベントデータを使用できます。[詳細情報](../datasource/adobe-experience-platform-data-source.md)。

## Adobe Customer Journey Analytics{#integration-cja}

Customer Journey Analytics を使用すると、Journey Optimizer で生成されたデータに対してアドバンス分析を実行できます。

Journey Optimizer は、Adobe Experience Platform にデータを保存し、Customer Journey Analytics を使用して、自動化されたレポート配信とデータのカスタムビジュアライゼーションにより、すべてのジャーニー、キャンペーン、オファーの全体像を提供します。

Journey Optimizer でジャーニーを作成した後、Customer Journey Analytics は、プラットフォームからデータを取り込み、レポートを開始して、顧客がジャーニーで行ったすべてのインタラクションの影響を理解できます。

詳しくは、[Journey Optimizer + Customer Journey Analytics](../reports/cja-ajo.md) を参照してください。

## Adobe Analytics{#integration-aa}

リアルタイムのジャーニーをトリガーし、顧客のエクスペリエンスを自動化するために、既にキャプチャして Adobe Experience Platform にストリーミングしている Adobe Analytics のあらゆる行動イベントデータを活用できます。このデータは、Journey Optimizer を使用してエンゲージ可能なセグメントの作成にも使用できます。

詳しくは、[Journey Optimizer + Analytics](../event/about-analytics.md) を参照してください。


## Adobe Experience Manager Assets Essentials{#integration-assets}

[!DNL Adobe Experience Manager Assets Essentials] を使用してマーケティングワークフローとクリエイティブワークフローを統合します。[!DNL Adobe Journey Optimizer] とネイティブに統合され、[!DNL Assets Essentials] へアクセスして、デジタルアセットの保存、管理、検出、配布を行います。メッセージの入力に使用できる、アセットの一元的なリポジトリを提供します。

[!DNL Adobe Experience Manager Assets Essentials] は左メニューの「**[!UICONTROL アセット]**」セクションを使用して [!DNL Adobe Journey Optimizer] から直接アクセスできます。

詳細情報： [Journey Optimizer + Assets Essentials](../email/assets-essentials.md).


## Adobe Stock{#integration-stock}

[!DNL Adobe Stock] と [!DNL Adobe Journey Optimizer] E メールデザイナーの統合プラグインを使用すると、メッセージオーサリングで使用する画像のナビゲーション、ライセンス取得および保存を簡単に行うことができます。

[!DNL Adobe Journey Optimizer] を使用すると、[!DNL Adobe Stock] からメールに画像を直接アップロードし、「**[!UICONTROL Adobe Stock フォトを検索]**」オプションを使用して&#x200B;**[!UICONTROL アセット]**&#x200B;フォルダーに追加できます。「**[!UICONTROL 類似のストックフォトを検索]**」オプションを使用すると、配信で使用されるアセットのコンテンツ、カラー、構成に一致する画像を検索することができます。

詳細情報： [Journey Optimizer + Stock](../email/stock.md).


## Adobe インテリジェントサービス{#integration-intelligent-service}

リアルタイム顧客データプラットフォームにネイティブな Adobe インテリジェントサービスを使用すると、カスタマーエクスペリエンスのユースケースで人工知能と機械学習の機能を活用できます。これにより、マーケティングアナリストは、データサイエンスの専門知識がなくても、ビジネスレベルの設定を使用して、会社のニーズに固有の予測を設定できます。

顧客 AI を使用すると、ブランドは、Adobe Experience Platform でプロファイル属性として使用でき、ジャーニーをパーソナライズするために使用できるチャーンまたはコンバージョンの機械学習ベースのスコアを作成できます。

[詳細情報](../building-journeys/ai-services-overview.md)。


## Adobe Campaign{#integration-ac}

統合は、Adobe Campaign v7 または v8 のユーザーが使用できます。この統合により、Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS を送信できるようになります。

詳しくは、[Journey Optimizer + Campaign](../building-journeys/ajo-ac.md) を参照してください。

また、Adobe Campaign Standard との統合を設定して、ジャーニーでメッセージを送信することもできます。

詳しくは、[Journey Optimizer + Campaign Standard](../building-journeys/ajo-ac.md) を参照してください。

## カスタムチャネル{#integration-custom}

サードパーティ製システムを使用してメッセージを送信する場合、またはジャーニーがサードパーティ製システムに API 呼び出しを送信する場合は、カスタムアクションを使用してジャーニーに接続します。例えば、カスタムアクションを使用して Epsilon、Slack、[Adobe Developer](https://developer.adobe.com){target="_blank"}、Firebase などのシステムに接続できます。

カスタムアクションは、技術ユーザーが定義し、マーケターが使用できる追加のアクションです。設定が完了すると、**[!UICONTROL アクション]**&#x200B;カテゴリの、ジャーニーの左側のパレットに表示されます。詳しくは、[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

詳しくは、[カスタムアクション](../action/about-custom-action-configuration.md)を参照してください。

## 外部データソース{#integration-external-systems}

Journey Optimizer では、カスタムデータソースとカスタムアクションを使用して、外部システムへの接続を設定できます。 これにより、例えば、外部の予約システムからのデータでジャーニーをエンリッチメントできます。

外部データ ソースを使用して、サードパーティ製システムへの接続を定義する方法については、[この節](../datasource/external-data-sources.md)を参照してください。

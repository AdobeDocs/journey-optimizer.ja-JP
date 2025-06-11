---
solution: Journey Optimizer
product: journey optimizer
title: 更新済みレポートエクスペリエンス
description: 全期間のレポートの基本を学ぶ
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: bfd88d2a-e7b8-4e3b-85a1-4a14b0ba56dc
source-git-commit: 15a73ba3f2d91a38d61e6518d704fc218ad0eea3
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 68%

---

# 全期間のレポートの基本を学ぶ {#channel-report-gs-cja}

>[!CONTEXTUALHELP]
>id="cja_connections_enable_cja"
>title="Customer Journey Analytics を有効にする"
>abstract="Customer Journey Analytics でこのレポートを分析するには、管理者に連絡して、組織が Customer Journey Analytics を購入しており、統合が適切に設定されていることを確認します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/email/design-email/add-content/content-components#add-content-components" text="Customer Journey Analytics"

Journey Optimizer レポートでは、Customer Journey Analytics 機能との相互運用性が改善され、両方のプラットフォーム間でレポートが標準化され、データの一貫性と信頼性が向上します。Journey Optimizer と Customer Journey Analytics のシームレスな統合により、パフォーマンス指標がより明確に表示され、ユーザーはより多くの情報に基づいて意思決定を行うことができます。

これらのレポート機能へのアクセスは、コンテキストと製品領域に応じて異なります。

* **ジャーニー** - ジャーニーまたはジャーニーのコンテキストの配信をターゲットする場合は、**[!UICONTROL ジャーニー]** メニューからジャーニーにアクセスし、「**[!UICONTROL レポートを表示]**」ボタンをクリックします。

  既存のジャーニーのリストから、選択したジャーニーの詳細メニューの「**[!UICONTROL レポート]**」を選択することもできます。[詳しくは、ジャーニーレポートを参照してください](journey-global-report-cja.md)

  ![](assets/gs-cja-report-3.png)

* **キャンペーン** - キャンペーンをターゲットにする場合は、**[!UICONTROL キャンペーン]** メニューからキャンペーンにアクセスし、**[!UICONTROL レポート]** ボタンをクリックしてから、**[!UICONTROL 全期間レポートを表示]** をクリックします。

  既存のキャンペーンのリストから、選択したキャンペーンの詳細メニューの「**[!UICONTROL レポート]**」を選択することもできます。[詳しくは、キャンペーンレポートを参照してください](campaign-global-report-cja.md)

  ![](assets/gs-cja-report-2.png)

* **グローバル** – 環境内のすべてのキャンペーンおよびジャーニーの指標をターゲットにする場合は、&lbrace;6 **「ジャーニー管理**」セクション内の **[!UICONTROL レポート]** メニューに移動して **概要レポートにアクセスします。**&#x200B;[詳しくは、概要レポートを参照してください](channel-report-cja.md)

  ![](assets/gs-cja-report-1.png)

>[!IMPORTANT]
>
>Adobe Journey Optimizer のレポートは現在、UTC に標準化されています。レポーティングのタイムゾーンをカスタマイズする機能は、今後のリリースで導入される予定です。

## 前提条件 {#prerequisites}

* Customer Journey Analytics を所有して&#x200B;**いない**&#x200B;場合、または所有しているが Customer Journey Analytics 製品プロファイルにアクセス&#x200B;**できない**&#x200B;場合、Journey Optimizer で権限が管理されています。この場合、**[!UICONTROL チャネルレポートの表示]** 権限または関連する役割が必要です。 [詳細情報](../administration/permissions.md)

* Customer Journey Analyticsを **所有** し、Customer Journey Analytics製品プロファイルにアクセスできる場合は、次が必要です。

   * Customer Journey Analytics の&#x200B;**[!UICONTROL オーディエンスの作成]**&#x200B;権限および&#x200B;**[!UICONTROL オーディエンスの表示]**&#x200B;権限。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/technotes/access-control){target="_blank"}

   * Adobe Journey Optimizer の&#x200B;**[!UICONTROL プロファイルの管理]**&#x200B;権限。[詳細情報](../administration/permissions.md)

* Customer Journey Analytics データビューは、次の設定（**Adobe Journey Optimizer のデフォルトデータビューとして設定**）で行う必要があります。[詳しくは、データビューを参照してください](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}


## チュートリアルビデオ{#video}

次のビデオでは、強化された Journey Optimizer レポートを Customer Journey Analytics で使用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3430413)
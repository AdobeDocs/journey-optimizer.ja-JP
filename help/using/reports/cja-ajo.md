---
solution: Journey Optimizer
product: journey optimizer
title: Customer Journey Analytics の操作
description: Customer Journey Analytics の基本を学ぶ
feature: Reporting
topic: Content Management
role: User
level: Beginner
exl-id: 5349b0cf-da4e-458c-89be-c75a38e4721a
source-git-commit: 7e27f5502d64d0c91de2c67e4011e650e77c6a92
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 95%

---

# [!DNL Customer Journey Analytics] の操作 {#cja-ajo}

![](assets/cja.png)
[!DNL Customer Journey Analytics] との [!DNL Journey Optimizer] 統合は、すべてのジャーニーの全体像を、自動レポート配信とデータのカスタムビジュアライゼーションで提供します。

[!DNL Journey Optimizer] でジャーニーを作成した後、[!DNL Customer Journey Analytics] に顧客データを読み込んでレポートを開始し、ジャーニーにおける顧客のインタラクションが与える影響を把握できます。

➡️ [Customer Journey Analytics の概要を確認する](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=ja){target=&quot;_blank&quot;}

ジャーニーに対して [!DNL Customer Journey Analytics] を使用する前に、まずこの統合を設定する必要があります。

1. [接続の作成](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja) in [!DNL Customer Journey Analytics] と **[!UICONTROL データセット]** Adobe Experience Platformに送信します。

   次の [!DNL Journey Optimizer] を設定できます。
   * [ジャーニーステップイベント](../data/datasets-query-examples.md#journey-step-event)：誰がジャーニーにエントリし、どのくらい進んだかを確認できます。
   * [メッセージフィードバック／トラッキングデータセット](../data/datasets-query-examples.md#message-feedback-event-dataset)：[!DNL Journey Optimizer] を介して送信したメッセージに関する配信情報を表示できます。
   * [エンティティデータセットおよびジャーニーデータセット](../data/datasets-query-examples.md#entity-dataset)：わかりやすい名前を検索し、レポートで使用できます。

1. [データビューを作成](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja)して、レポートに使用するディメンションおよび指標を設定します。

   Journey Optimizer 固有の指標を作成して、ジャーニーのデータをよりよく反映できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/integrations/ajo.html?lang=ja#configure-the-data-view-to-accommodate-journey-optimizer-dimensions-and-metrics)


[!DNL Journey Optimizer] と [!DNL Customer Journey Analytics] を使用する場合、次の原因により、レポートデータに何らかの相違が生じる可能性があります。

* **[!DNL Journey Optimizer] と [!DNL Customer Journey Analytics] は両方とも、レポート用に Azure Data Lake Storage（ADLS）からのデータを同期します。**

   受信データの処理時間は、製品間で多少異なる場合があります。このため、指定した日付から現在の日付までのレポートを表示すると、データが一致しない場合があります。相違を減らすには、現在の日付を除く日付範囲を使用します。

* **[!DNL Journey Optimizer] レポートでは、送信済み指標には、再試行指標も含まれます。**

   **[!UICONTROL 再試行]**&#x200B;は、[!DNL Customer Journey Analytics]での&#x200B;**[!UICONTROL 送信済み]**&#x200B;指標には含まれません。そのため、[!DNL Customer Journey Analytics] **[!UICONTROL 送信済み]**&#x200B;指標には、[!DNL Journey Optimizer] より低い値が表示されます。ただし、再試行データは、「**[!UICONTROL 正常に送信されたメッセージ]**」または「**[!UICONTROL バウンス]**」指標に収束されます。
相違を減らすには、1 週間前またはそれ以降の日付範囲を使用します。

* **レポートは、異なるデータソースから提供されています。**

   その結果、製品間で 1～2％のデータの相違が生じる可能性があります。

---
solution: Journey Optimizer
product: journey optimizer
title: お客様の旅解析機能について
description: お客様の旅解析の開始
feature: Reporting
topic: Content Management
role: User
level: Beginner
exl-id: 5349b0cf-da4e-458c-89be-c75a38e4721a
source-git-commit: 928ad6822efbe95c0ddf5456531d92be8b4bed75
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# の操作 [!DNL Customer Journey Analytics] {#cja-ajo}


[!DNL Journey Optimizer] と [!DNL Customer Journey Analytics] の連携により、自動的にレポートを配布して、データのカスタム視覚化を行うすべての journeys の全体像を把握することができます。

![](assets/cja.png)

に [!DNL Journey Optimizer] 旅を作成した後は、お客様のデータをに [!DNL Customer Journey Analytics] 読み込んで、レポートを開始し、お客様が journeys について行うあらゆるやり取りの影響について理解することができます。

➡️ [ お客様の旅の分析 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html) を発見 {target = &quot;_blank&quot;}

Journeys の使用を開始する前に、この統合を設定して [!DNL Customer Journey Analytics] おく必要があります。

1. [で [!DNL Customer Journey Analytics] 、 **[!UICONTROL Dataset]** Adobe エクスペリエンスプラットフォームに送信するとの接続 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html) を作成します。

   次 [!DNL Journey Optimizer] の設定を行うことができます。
   * [「旅のステップ」イベント ](../data/datasets-query-examples.md#journey-step-event) : 誰が journeys を入力したかを表示します。
   * [メッセージのフィードバック/追跡データセット ](../data/datasets-query-examples.md#message-feedback-event-dataset) : 経由 [!DNL Journey Optimizer] で送信されたメッセージに関する配信情報を表示することができます。
   * [「エンティティおよび旅データセット ](../data/datasets-query-examples.md#entity-dataset) 」: フレンドリ名を検索して、レポートで使用することができます。

1. [データビュー ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html) を作成して、レポートに使用するディメンションとメトリックを設定します。

   Journeys のデータをより適切に反映するために、詳細なオプティマイザー特有のメトリックスを作成することができます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/integrations/ajo.html#configure-the-data-view-to-accommodate-journey-optimizer-dimensions-and-metrics)


を使用 [!DNL Journey Optimizer] すると、次のような [!DNL Customer Journey Analytics] 原因で発生するデータの報告に問題が生じることがあります。

* **[!DNL Journey Optimizer]レポート用に、Azure Data Lake Storage (ADLS) との間でデータを同期し [!DNL Customer Journey Analytics] ます。**

   受信データの処理時間は製品によって多少異なります。 このため、指定された日付から当日にレポートを表示すると、データが一致しないことがあります。 不一致を減らすには、現在の日付を除く日付の範囲を使用します。

* **[!DNL Journey Optimizer]報告書には、リトライメトリックも含まれています。**

   **[!UICONTROL Retries]**&#x200B;は、の [!DNL Customer Journey Analytics] 「メトリック」に **[!UICONTROL Sent]** は含まれません。これにより、メトリックには、より [!DNL Journey Optimizer] 小さい値が表示され [!DNL Customer Journey Analytics] **[!UICONTROL Sent]** ます。ただし、再試行データは or **[!UICONTROL Bounces]** メトリックに **[!UICONTROL Messages successfully sent]** 収束されます。不一致を減らすには、1週間前または後で日付の範囲を使用します。

* **レポートは別のデータソースから提供されています。**

   これにより、製品間に1-2% のデータ不一致が発生する可能性があります。

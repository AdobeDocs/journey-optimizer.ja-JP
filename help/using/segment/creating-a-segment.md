---
solution: Journey Optimizer
product: journey optimizer
title: セグメントの作成
description: セグメントの作成方法を学ぶ
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 289aac5d-6cdb-411f-985e-3acef58050a8
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 100%

---

# セグメントの作成 {#build-segments}

>[!CONTEXTUALHELP]
>id="ajo_ao_create_rule"
>title="ルールの作成"
>abstract="「ルールを作成」の作成方法を使用すると、Adobe Experience Platform セグメント化サービスを使用して新しいセグメント定義を作成できます。"

この例では、アトランタ、サンフランシスコ、シアトルに住み、1980 年以降に生まれたすべての顧客をターゲットするセグメントを作成します。これらのすべての顧客は、過去 7 日以内に Luma アプリを開き、その後 2 時間以内に購入している必要があります。

➡️ [セグメントの作成方法については、このビデオをご覧ください](#video-segment)

1. **[!UICONTROL セグメント]**&#x200B;メニューにアクセスし、「**[!UICONTROL セグメントを作成]**」ボタンをクリックします。

   ![](assets/create-segment.png)

   「セグメント定義」画面では、必須フィールドをすべて設定してセグメントを定義できます。セグメントの設定方法については、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja){target="_blank"}を参照してください。

   ![](assets/segment-builder.png)

1. **[!UICONTROL セグメントプロパティ]**ペインで、セグメントの名前と説明（オプション）を入力します。


   ![](assets/segment-properties.png)

1. 必要なフィールドを左ペインから中央のワークスペースにドラッグ＆ドロップし、必要に応じて設定します。


   >[!NOTE]
   >
   >左側のペインに表示されるフィールドは、組織での **XDM 個人プロファイル**&#x200B;と **XDM ExperienceEvent** スキーマの設定方法によって異なります。

詳しくは、[Adobe Experience Data Model（XDM）のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}を参照してください。

   ![](assets/drag-fields.png)

   この例では、「**属性**」フィールドと「**イベント**」フィールドに基づいてセグメントを作成する必要があります。

   * **属性**：1980 年以降、アトランタ、サンフランシスコ、シアトルに住む人のプロファイル。

      ![](assets/add-attributes.png)

   * **イベント**：過去 7 日間に Luma アプリを開き、アプリを開いてから 2 時間以内に購入したプロファイル。

      ![](assets/add-events.png)

1. ワークスペースに新しいフィールドを追加および設定すると、**[!UICONTROL セグメントのプロパティ]**&#x200B;ペインが自動的に更新され、セグメントに属する予測プロファイルに関する情報が表示されます。

   ![](assets/segment-estimate.png)

1. セグメントの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。Adobe Experience Platform セグメントのリストに表示されます。リストで特定のセグメントを検索する際に役立つ検索バーが用意されています。

これで、セグメントをジャーニーで使用できるようになります。詳しくは、[この節](../segment/about-segments.md)を参照してください。

## ハウツービデオ{#video-segment}

セグメントの作成方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334281?quality=12)

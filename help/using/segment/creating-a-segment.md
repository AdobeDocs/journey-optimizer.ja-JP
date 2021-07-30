---
title: セグメントの作成
description: セグメントの作成方法を学ぶ
feature: ジャーニー
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---

# セグメントの作成 {#build-segments}

この例では、アトランタ、サンフランシスコ、シアトルに住み、1980 年以降に生まれたすべての顧客をターゲットするセグメントを作成します。これらのすべての顧客は、過去 7 日以内に Luma アプリを開き、その後 2 時間以内に購入している必要があります。

1. **[!UICONTROL セグメント]**&#x200B;メニューにアクセスし、「**[!UICONTROL セグメントを作成]**」ボタンをクリックします。

   ![](../assets/create-segment.png)

   「セグメント定義」画面では、必須フィールドをすべて設定してセグメントを定義できます。セグメントの設定方法については、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

   ![](../assets/segment-builder.png)

1. **[!UICONTROL セグメントプロパティ]**&#x200B;ウィンドウで、セグメントの名前と説明（オプション）を入力します。

   ![](../assets/segment-properties.png)

1. 必要なフィールドを左ウィンドウから中央のワークスペースにドラッグ＆ドロップし、必要に応じて設定します。

   >[!NOTE]
   >
   >左側のウィンドウに表示されるフィールドは、組織での **XDM 個人プロファイル**&#x200B;と **XDM ExperienceEvent** スキーマの設定方法によって異なります。詳しくは、[Adobe Experience Data Model（XDM）のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

   ![](../assets/drag-fields.png)

   この例では、「**属性**」フィールドと「**イベント**」フィールドに基づいてセグメントを作成する必要があります。

   * **属性**：1980 年以降、アトランタ、サンフランシスコ、シアトルに住む人のプロファイル。

      ![](../assets/add-attributes.png)

   * **イベント**：過去 7 日間に Luma アプリを開き、アプリを開いてから 2 時間以内に購入したプロファイル。

      ![](../assets/add-events.png)

1. ワークスペースに新しいフィールドを追加および設定すると、**[!UICONTROL セグメントのプロパティ]**&#x200B;ウィンドウが自動的に更新され、セグメントに属する予測プロファイルに関する情報が表示されます。

   ![](../assets/segment-estimate.png)

1. セグメントの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。Adobe Experience Platform セグメントのリストに表示されます。リストで特定のセグメントを検索する際に役立つ検索バーが用意されています。

これで、セグメントをジャーニーで使用できるようになります。詳しくは、[この節](../segment/about-segments.md)を参照してください。

## チュートリアルビデオ{#create-segment-video}

>[!VIDEO](https://video.tv.adobe.com/v/334281?quality=12)

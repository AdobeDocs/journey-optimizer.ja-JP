---
title: セグメントの作成
description: セグメントの作成方法を学ぶ
feature: ジャーニー
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 100%

---

# セグメントの作成 {#build-segments}

この例では、アトランタ、サンフランシスコ、シアトルに住み、1980 年以降に生まれたすべての顧客をターゲットするセグメントを作成します。これらのすべての顧客は、過去 7 日以内に Luma アプリを開き、その後 2 時間以内に購入している必要があります。

1. **[!UICONTROL セグメント]**&#x200B;メニューにアクセスし、「**[!UICONTROL セグメントを作成]**」ボタンをクリックします。

   ![](../assets/create-segment.png)

   「セグメント定義」画面では、必須フィールドをすべて設定してセグメントを定義できます。セグメントの設定方法については、[Segmentation Service ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja)を参照してください。

   ![](../assets/segment-builder.png)

1. **[!UICONTROL セグメントプロパティ]**&#x200B;ウィンドウで、セグメントの名前と説明（オプション）を入力します。

   ![](../assets/segment-properties.png)

1. 必要なフィールドを左ウィンドウから中央のワークスペースにドラッグ＆ドロップし、必要に応じて設定します。

   >[!NOTE]
   >
   >左側のウィンドウに表示されるフィールドは、組織での **XDM 個人プロファイル**&#x200B;と **XDM ExperienceEvent** スキーマの設定方法によって異なります。詳しくは、[Adobe Experience Data Model（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。

   ![](../assets/drag-fields.png)

   この例では、**属性**&#x200B;と&#x200B;**イベント**&#x200B;の各フィールドを使用してセグメントを作成する必要があります。

   * **属性**：1980 年以降、アトランタ、サンフランシスコ、シアトルに住むプロファイル。
   * **イベント**：過去 7 日間に Luma アプリを開き、アプリを開いてから 2 時間以内に購入したプロファイル。

      ![](../assets/add-attributes.png)

      ![](../assets/add-events.png)

1. ワークスペースに新しいフィールドを追加および設定すると、**[!UICONTROL セグメントのプロパティ]**&#x200B;ウィンドウが自動的に更新され、セグメントに属する予測プロファイルに関する情報が表示されます。

   ![](../assets/segment-estimate.png)

1. セグメントの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。Adobe Experience Platform セグメントのリストに表示されます。リストで特定のセグメントを検索する際に役立つ検索バーが用意されています。

これで、セグメントをジャーニーで使用できるようになります。詳しくは、[この節](../segment/about-segments.md)を参照してください。

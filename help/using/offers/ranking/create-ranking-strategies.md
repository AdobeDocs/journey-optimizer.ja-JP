---
product: experience platform
solution: Experience Platform
title: AI モデルの作成
description: AI モデルを作成してオファーをランク付けする方法を説明します
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 81d07ec8-e808-4bc6-97b1-b9f7db2aec22
source-git-commit: 12b01cb9de84399e5ede987866609acc10b64c5f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 39%

---

# AI モデルの作成 {#ai-rankings}

[!DNL Journey Optimizer] を使用すると、ビジネス目標に基づいてオファーをランク付けする **AI モデル**&#x200B;を作成できます。

>[!CAUTION]
>
>AI モデルを作成、編集または削除するには、**ランキング戦略を管理**&#x200B;する権限が必要です。[詳細情報](../../administration/high-low-permissions.md#manage-ranking-strategies)

## AI モデルの作成 {#create-ranking-strategy}

AI モデルを作成するには、次の手順に従います。

1. 内 **[!UICONTROL コンポーネント]** メニュー、 **[!UICONTROL ランキング]** 「 」タブで、「 **[!UICONTROL AI モデル]**.

   ![](../assets/ai-ranking-list.png)

   これまでに作成した AI モデルがすべて表示されます。

1. 次をクリック： **[!UICONTROL AI モデルを作成]** 」ボタンをクリックします。

1. AI モデルの一意の名前と説明を指定します。

   <!--* **[!UICONTROL Auto-optimization]** optimizes offers based on past offer performance. [Learn more](auto-optimization-model.md)
    * **[!UICONTROL Personalized]** optimizes and personalizes offers based on segments and offer performance. [Learn more](personalized-optimization-model.md)-->

   ![](../assets/ai-ranking-fields.png)

   >[!NOTE]
   >
   >この **[!UICONTROL 最適化指標]** 「 」セクションでは、AI モデルがオファーのランク付けを計算する際に使用するコンバージョンイベントに関する情報を提供します。
   >
   >[!DNL Journey Optimizer] 次に基づいてオファーをランク付け **コンバージョン率** （コンバージョン率=コンバージョンイベントの合計数/インプレッションイベントの合計数）。 コンバージョン率は、次の 2 種類の指標を使用して計算されます。
   >* **インプレッションイベント** （表示されるオファー）
   >* **コンバージョンイベント** （電子メールまたは web でのクリックにつながるオファー）

   >
   >これらのイベントは、提供されている Web SDK または Mobile SDK を使用して自動的にキャプチャされます。 詳しくは、[Adobe Experience Platform web SDK の概要](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を参照してください。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを選択します。 そのようなデータセットを作成する方法については、[こちらの節](#create-dataset)を参照してください。 <!--This dataset needs to be associated with a schema that must have the **[!UICONTROL Proposition Interactions]** field group (previously known as mixin) associated with it.-->

   ![](../assets/ai-ranking-dataset-id.png)

   >[!CAUTION]
   >
   >「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループ（以前の mixin）に関連付けられたスキーマから作成されたデータセットのみがドロップダウンリストに表示されます。

<!--1. If you are creating a **[!UICONTROL Personalization]** AI model, select the segment(s) to use to train the AI model.

    ![](../assets/ai-ranking-segments.png)

    >[!NOTE]
    >
    >You can select up to 5 segments.-->

1. AI モデルを保存してアクティブ化します。

   ![](../assets/ai-ranking-save-activate.png)

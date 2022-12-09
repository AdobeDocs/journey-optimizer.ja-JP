---
product: experience platform
solution: Experience Platform
title: イベントを収集するためのデータセットの作成
description: イベントを収集するためのデータセットの作成方法について説明します。
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 99963ef4-0b19-475e-96f4-2eac3f680c6f
source-git-commit: 5abcef4ff057bb351abaafbf4dcb99e1ab61c6a9
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# イベントを収集するためのデータセットの作成 {#create-dataset}

AI モデルを作成する前に、変換イベントが収集されるデータセットを作成する必要があります。 まず、データセットで使用されるスキーマを作成します。

1. **[!UICONTROL Data Management]**&#x200B;メニューのを選択 **[!UICONTROL Schema]** して、タブに **[!UICONTROL Browse]** 移動し、をクリック **[!UICONTROL Create schema]** します。

   ![](../assets/ai-ranking-create-schema.png)

1. 「」を選択 **[!UICONTROL XDM ExperienceEvent]** します。

   ![](../assets/ai-ranking-xdm-event.png)

   >[!NOTE]
   >
   >Xdm について詳しくは、 [ xdm の「システム概要 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en) について」を参照してください。 {target = &quot;_blank&quot;}。

1. **[!UICONTROL Field groups]**&#x200B;左側のセクションから、を選択 **[!UICONTROL Add]** します。

   ![](../assets/ai-ranking-fields-groups.png)

1. **[!UICONTROL Search]**&#x200B;フィールドに「提案インタラクション」と入力し、フィールドグループを選択 **[!UICONTROL Experience Event - Proposition Interactions]** します。

   ![](../assets/ai-ranking-proposition-interactions.png)

   >[!CAUTION]
   >
   >データセットで使用されるスキーマには、フィールドグループが関連付けられている必要があり **[!UICONTROL Experience Event - Proposition Interactions]** ます。 それ以外の場合は、ランク付け方針に使用することはできません。

1. をクリック **[!UICONTROL Add field groups]** します。

   ![](../assets/ai-ranking-add-field-group.png)

   >[!NOTE]
   >フィールドグループは、以前は mixin と呼ばれていました。

1. 名前を入力し、スキーマを保存します。

>[!NOTE]
>
>スキーマコンポジション ](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#understanding-schemas) の基礎におけるスキーマの構築について詳しくは、 [ {target = &quot;_blank&quot;} を参照してください。

これで、このスキーマを使用してデータセットを作成する準備ができました。 これを行うには、次の手順を実行します。

1. **[!UICONTROL Data Management]**&#x200B;メニューのを選択 **[!UICONTROL Datasets]** して、タブに **[!UICONTROL Browse]** 移動し、をクリック **[!UICONTROL Create dataset]** します。

   ![](../assets/ai-ranking-create-dataset.png)

1. を選択 **[!UICONTROL Create dataset from schema]** します。

   ![](../assets/ai-ranking-create-dataset-from-schema.png)

1. 作成したスキーマをリストから選択します。

   ![](../assets/ai-ranking-dataset-select-schema.png)

1. をクリック **[!UICONTROL Next]** します。

1. フィールドに **[!UICONTROL Name]** データセットの一意の名前を指定して、をクリック **[!UICONTROL Finish]** します。

   ![](../assets/ai-ranking-dataset-name.png)

データセットは、ランク付けストラテジ ](#create-ranking-strategy) の作成時 [ に、イベントデータを収集するために選択できるようになりました。

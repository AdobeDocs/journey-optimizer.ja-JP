---
product: experience platform
solution: Experience Platform
title: AI モデルの作成
description: Rank のランク付けに AI モデルを作成する方法について説明します。
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 81d07ec8-e808-4bc6-97b1-b9f7db2aec22
source-git-commit: 3188bc97b8103d2a01101a23d8c242a3e2924f76
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 0%

---

# AI モデルの作成 {#ai-rankings}

[!DNL Journey Optimizer]では、実際の業務上のゴールに基づいて、ランク付けに AI モデル **を作成** することができます。

>[!CAUTION]
>
>AI モデルを作成、編集、または削除するには、「ランク付け方針 **の** 管理」権限が必要です。[詳細情報](../../administration/high-low-permissions.md#manage-ranking-strategies)

## AI モデルの作成 {#create-ranking-strategy}

AI モデルを作成するには、次の手順に従います。

1. **[!UICONTROL Components]**&#x200B;メニューからタブにアクセス **[!UICONTROL Ranking]** し、を選択 **[!UICONTROL AI models]** します。

   ![](../assets/ai-ranking-list.png)

   これまでに作成したすべての AI モデルがリストに表示されます。

1. ボタンを **[!UICONTROL Create AI model]** クリックします。

1. AI モデルの一意の名前と説明を指定し、作成する AI モデルの種類を選択します。

   * **[!UICONTROL Auto-optimization]** 従来のパフォーマンスに基づいて、提供する機能を最適化します。 [詳細情報](auto-optimization-model.md)
   * **[!UICONTROL Personalized]** 区分に基づいて、パフォーマンスを向上させることができます。 [詳細情報](personalized-optimization-model.md)

   ![](../assets/ai-ranking-fields.png)

   >[!NOTE]
   >
   >**[!UICONTROL Optimization metric]**&#x200B;このセクションでは、AI モデルによって使用される変換イベントに関する情報を提供します。
   >
   >[!DNL Journey Optimizer]変換レート **に** 基づくランク付け (変換率 = 変換イベントの合計回数/インプレッションイベント総数)。変換レートは、次の2種類のメトリックを使用して計算されます。
   >* **インプレッションイベント** (表示される提供)
   >* **変換イベント** (電子メールまたは web 経由でのクリックで発生する機能)

   >
   >これらのイベントは、提供されている Web SDK またはモバイル SDK を使用して自動的にキャプチャされます。 詳しくは、Adobe エクスペリエンス Platform Web SDK の [ 概要 ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) を参照してください。

1. 変換イベントおよびインプレッションイベントが収集されるデータセットを選択します。 このセクション ](#create-dataset) では、 [ このようなデータセットを作成する方法について説明します。<!--This dataset needs to be associated with a schema that must have the **[!UICONTROL Proposition Interactions]** field group (previously known as mixin) associated with it.-->

   ![](../assets/ai-ranking-dataset-id.png)

   >[!CAUTION]
   >
   >ドロップダウンリストに表示されるのは、 **[!UICONTROL Experience Event - Proposition Interactions]** フィールドグループに関連付けられたスキーマから作成されたデータセット (以前は mixin) のみです。

1. Ai モデルを **[!UICONTROL Personalization]** 作成する場合は、ai モデルの学習に使用するセグメントを選択します。

   ![](../assets/ai-ranking-segments.png)

   >[!NOTE]
   >
   >最大5つのセグメントを選択できます。

1. AI モデルを保存し、アクティブにします。

   ![](../assets/ai-ranking-save-activate.png)

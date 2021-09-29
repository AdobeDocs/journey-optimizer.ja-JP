---
title: 決定でのオファー選択の設定
description: 決定でのオファー選択を管理する方法を説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 8c7135d7-bf5a-4671-afdf-afec60907a56
source-git-commit: 43fb98a08555e6b889ad537e79dba78286dafeb9
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 94%

---

# 決定でのオファー選択の設定 {#offers-selection-in-activities}

複数のオファーが特定のプレースメントの資格を持つ場合、決定を設定する際に各プロファイルに最適なオファーを選択する方法（旧称：オファーアクティビティ）を選択できます。オファーのランク付けは、次の基準で行えます。
* オファーの優先度
* ランキング式
* [AIランキング](#use-ranking-strategy) （一部のユーザーに対してのみ先行アクセス）

![](../../assets/offer-rank-by.png)

## オファーの優先度 {#about-offers-priority}

デフォルトでは、決定（旧称：オファーアクティビティ）で指定のプレースメントに対して実施要件を満たすオファーが複数ある場合、**優先度**&#x200B;が最も高いオファーが最初に顧客に配信されます。

![](../../assets/offer-priority.png)

オファーの優先順位スコアは、オファーの作成時に割り当てられます。パーソナライズされたオファーを作成する方法については、[この節](../offer-library/creating-personalized-offers.md)を参照してください。

## ランキング式 {#assign-ranking-formula}

Journey Optimizer では、オファーの優先度に加えて、**ランキング式**&#x200B;を作成できます。 これらは、特定のプレースメントに対して最初に表示するオファーを決定する数式であり、オファーの優先度スコアを考慮するものではありません。

例えば、終了日が今から 24 時間以内のすべてのオファーの優先度を上げることもできますし、プロファイルの目標地点が「実行中」の場合は「実行中」カテゴリのオファーの優先度を上げることもできます。

ランキング式を作成する方法については、 [この節](../offer-library/create-ranking-formulas.md)を参照してください。

ランキング式を作成したら、決定（旧称：オファーアクティビティ）内のプレースメントに割り当てることができます。これを行うには、以下の手順に従います。

1. 決定を作成するか、既存の決定を編集します。[決定の作成](../offer-activities/create-offer-activities.md)を参照してください。

1. オファーを含むプレースメントを追加します。[プレースメントの作成](../offer-library/creating-placements.md)を参照してください。

1. 各プレースメントに対して、コレクションを追加します。[コレクションの作成](../offer-library/creating-collections.md)を参照してください。

1. ドロップダウンリストから「**[!UICONTROL ランキング]**」を選択してオファーをランク付けし、「**[!UICONTROL ランキングを追加]**」をクリックします。

   ![](../../assets/offer-activity-ranking.png)

1. 目的のランキング式を選択し、「**[!UICONTROL 選択]**」をクリックします。

   ![](../../assets/ranking-selection.png)

これで、ランキング式がプレースメントに関連付けられました。

このプレースメントで提示するための実施要件を満たすオファーが複数ある場合、決定はランキング式を使用して、最初に配信するオファーを計算します。

## AI ランキング {#use-ranking-strategy}

<!--If you are an [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target="_blank"} user leveraging the **Offer Decisioning** application service,-->You can also use an trained model system that automatically ranks offers to display for a given profile by selecting a ranking strategy. Learn how to create a ranking strategy in [this section](../offer-library/create-ranking-strategies.md).

>[!CAUTION]
>
>現在、AIランキングは、一部のユーザーに対してのみ早期にアクセスできます。

ランキング戦略を作成したら、決定（旧称：オファーアクティビティ）内のプレースメントに割り当てることができます。これを行うには、次の手順に従います。

1. 決定を作成するか、既存の決定を編集します。[決定の作成](../offer-activities/create-offer-activities.md)を参照してください。

1. オファーを含むプレースメントを追加します。[プレースメントの作成](../offer-library/creating-placements.md)を参照してください。

1. 各プレースメントに対して、コレクションを追加します。[コレクションの作成](../offer-library/creating-collections.md)を参照してください。

1. ドロップダウンリストから&#x200B;**[!UICONTROL AI ランキング]**&#x200B;別にオファーをランク付けするように選択します。

   ![](../../assets/ranking-selection-ai-ranking.png)

1. 「**[!UICONTROL ランキングを追加]**」をクリックします。

   ![](../../assets/ranking-selection-ai-ranking-add.png)

1. 作成したランキング戦略を選択します。ランキング戦略の詳細がすべて表示されます。

   ![](../../assets/ranking-selection-ai-ranking-selected.png)

1. 「**[!UICONTROL 選択]**」をクリックします。

これで、ランキング戦略がプレースメントに関連付けられました。

複数のオファーが適格な場合、トレーニング済みモデルシステムは、特定のプレースメントに対して最初に提示するオファーを決定します。

<!--Result? Describe the impact for the user, i.e. what's the effect of selecting this ranking strategy for this collection/placement.-->

<!--Click **[!UICONTROL Next]** to confirm and save your decision.-->

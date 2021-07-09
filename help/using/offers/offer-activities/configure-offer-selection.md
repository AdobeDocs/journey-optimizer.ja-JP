---
title: 決定でのオファー選択の設定
description: 決定でのオファー選択を管理する方法を説明します。
feature: オファー
topic: 統合
role: User
level: Intermediate
source-git-commit: a25264cb43f77671c29f18522110fd85d0155697
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 決定でのオファー選択の設定 {#offers-selection-in-activities}

## オファーの優先度について {#about-offers-priority}

決定での指定プレースメントに対する実施要件を満たすオファーが複数ある場合（旧称：オファーアクティビティ）、デフォルトでは、**優先度**&#x200B;が最も高いオファーが最初に顧客に配信されます。オファーの優先度スコアは、オファーの作成時に割り当てられます（「[パーソナライズされたオファーの作成](../offer-library/creating-personalized-offers.md)」を参照）。

![](../../assets/offer-priority.png)

また、Journey Optimizer では&#x200B;**ランキング式**&#x200B;を作成できます。これらは、特定のプレースメントに対して最初に表示するオファーを決定する数式であり、オファーの優先度スコアを考慮するものではありません。

例えば、終了日が今から 24 時間以内のすべてのオファーの優先度を上げることもできますし、プロファイルの目標地点が「実行中」の場合は「実行中」カテゴリのオファーの優先度を上げることもできます。

ランキング式の作成方法について詳しくは、[こちらの節](../offer-library/create-ranking-formulas.md)を参照してください。

## プレースメントへのランキング式の割り当て {#assign-ranking-formula}

ランキング式を作成したら、決定内のプレースメントに割り当てることができます。これをおこなうには、以下の手順に従います。

1. 決定を作成するか、既存の決定を編集し、オファーを含んだプレースメントを作成します（「 [決定の作成](../offer-activities/create-offer-activities.md)」を参照）。

1. 各プレースメントについて、ドロップダウンリストから「**[!UICONTROL ランキング]**」を選択します。

1. 「**[!UICONTROL ランキングを追加]**」をクリックします。

   ![](../../assets/offer-activity-ranking.png)

1. 目的のランキング式を選択し、「**[!UICONTROL 選択]**」をクリックします。

   ![](../../assets/ranking-selection.png)

これで、ランキング式がプレースメントに関連付けられました。

この配置で複数のオファーを提示する資格がある場合、決定では、ランキング式の数式を使用して、最初に配信するオファーを計算します。

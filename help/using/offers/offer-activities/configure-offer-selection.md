---
title: 決定でのオファーの選択の設定
description: オファーの選択を決定に対して管理する方法を説明します。
translation-type: tm+mt
source-git-commit: db7fd318b14d01a0369c934a3e01c6e368d7658d
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%

---

# 決定でのオファーの選択の構成{#offers-selection-in-activities}

## オファーの優先度について {#about-offers-priority}

デフォルトでは、複数のオファーが決定時に特定のプレースメントを受ける資格がある場合(旧オファーアクティビティ)、**優先度**&#x200B;が最も高いオファーが最初に顧客に配信されます。 オファーの優先度スコアは、オファーの作成時に割り当てられます（「[パーソナライズされたオファーの作成](../offer-library/creating-personalized-offers.md)」を参照）。

![](../../assets/offer-priority.png)

また、Journey Optimizerでは、**ランキング式**&#x200B;を作成できます。 これらは、オファーの優先度スコアを考慮するのではなく、特定のプレースメントに対して最初に表示するオファーを決定する数式です。例えば、終了日が今から 24 時間以内のすべてのオファーの優先度を上げることもできますし、プロファイルの目標地点が「実行中」の場合は「実行中」カテゴリのオファーの優先度を上げることもできます。

ランキング式の作成方法について詳しくは、[こちらの節](../offer-library/create-ranking-formulas.md)を参照してください。

## プレースメントへのランキング式の割り当て {#assign-ranking-formula}

ランキング式を作成したら、その数式を決定内のプレースメントに割り当てることができます。 これを行うには、以下の手順に従います。

* 決定を作成するか、既存の決定を編集してから、オファーを含める配置を作成します（[決定の作成](../offer-activities/create-offer-activities.md)を参照）。

* プレースメントごとに、ドロップダウンリストから 「**[!UICONTROL ランキング]**」を選択して、「**[!UICONTROL ランキングを追加]**」をクリックします。

   ![](../../assets/offer-activity-ranking.png)

* 目的のランキング式を選択し、「**[!UICONTROL 選択]**」をクリックします。

   ![](../../assets/ranking-selection.png)

これで、ランキング式がプレースメントに関連付けられました。複数のオファーがこのプレースメントで提示される資格がある場合、ランキング式の公式を使用して、最初に配信するオファーを計算します。

---
title: 「決定」の「選択項目を設定」を選択します。
description: 意思決定を選択して管理する方法を学習します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 8c7135d7-bf5a-4671-afdf-afec60907a56
source-git-commit: b890d7dc2e1508bb68d45a162236483ac6fc76bd
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---

# 「決定」の「選択項目を設定」を選択します。 {#offers-selection-in-decisions}

特定の場所に複数のオファーが適合する場合は、決定を設定するときに、各プロファイルに最適なオファーを選択する方法を選択できます。 オファーは、次の方法でランク付けできます。
* オファーの優先度
* ランク付け式
* [AI ランク付け](#use-ranking-strategy)

![](../assets/offer-rank-by.png)

## オファーの優先度 {#offer-priority}

初期設定では、複数の特典が特定の場所にある場合、その条件が高い **** 順にキャンペーンが実行されます。

![](../assets/offer-priority.png)

オファーの作成時には、「優先度スコアが割り当てられています。 この節 ](../offer-library/creating-personalized-offers.md) で [ は、パーソナライズされたオファーを作成する方法について説明します。

## ランク付け式 {#assign-ranking-formula}

重要度の高いオプティマイザーを使用すると、ランク付けする式 **を作成** することができます。次に示すのは、提示された配置について、キャンペーンの優先得点を考慮するのではなく、最初にどのオファーを表示するかを決定する判別式です。

例えば、終了日が今から24時間よりも少ない場合、または、プロファイルが対象点として「実行中」である場合は、「実行中」カテゴリから「ブースト」になるすべてのサービスの優先順位を上げることができます。

この節 ](../ranking/create-ranking-formulas.md) で [ は、ランキングの計算方法について説明しています。

ランク計算式が作成されると、決定の位置に割り当てることができます。 これを行うには、次の手順を実行します。

1. 決定を作成するか、既存の意思決定を編集します。 「意思決定 ](../offer-activities/create-offer-activities.md) の作成」を参照してください [ 。

1. 提供される広告を追加することができます。 配置の作成 ](../offer-library/creating-placements.md) を参照してください [ 。

1. 各配置にコレクションを追加します。 コレクション ](../offer-library/creating-collections.md) の作成を参照してください [ 。

1. ランキングメソッドとしてを選択 **[!UICONTROL Ranking formula]** し、をクリック **[!UICONTROL Add ranking]** します。

   ![](../assets/offer-activity-ranking.png)

1. 目的のランク付け式を選択し、をクリック **[!UICONTROL Select]** します。

   ![](../assets/ranking-selection.png)

ランク付け式が配置に関連付けられるようになりました。

この決定によって、複数のサービスがこのような方法で提示される場合は、ランク計算式の数式を使用して、最初にどのオファーリングを表示するかを計算します。

## AI ランク付け {#use-ranking-strategy}

<!--If you are an [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target="_blank"} user leveraging the **Offer Decisioning** application service,-->

また、ランク付け方針を選択することにより、特定のプロフィールについて、表示するサービスを自動的にランク付けする訓練されたモデルシステムを使用することもできます。 この節 ](../ranking/create-ranking-strategies.md) で [ は、ランク付け方法の作成方法について説明します。

ランキング法を作成した後は、それを決定の位置に割り当てることができます。 これを行うには、次の手順を実行します。

1. 決定を作成するか、既存の意思決定を編集します。 「意思決定 ](../offer-activities/create-offer-activities.md) の作成」を参照してください [ 。

1. 提供される広告を追加することができます。 配置の作成 ](../offer-library/creating-placements.md) を参照してください [ 。

1. 各配置にコレクションを追加します。 コレクション ](../offer-library/creating-collections.md) の作成を参照してください [ 。

1. ドロップダウンリストから「ランク付け **[!UICONTROL AI ranking]** 」を選択し、をクリック **[!UICONTROL Add ranking]** します。

   ![](../assets/ranking-selection-ai-ranking.png)

1. 作成したランク付け方法を選択します。 ランキングストラテジーのすべての詳細が表示されます。

   ![](../assets/ranking-selection-ai-ranking-selected.png)

1. をクリック **[!UICONTROL Select]** します。 これで、ランク付けストラテジが配置に関連付けられるようになりました。

複数のオファーが適格な場合、認定されたモデルシステムは、所定の配置について最初に提示するオファーを決定します。


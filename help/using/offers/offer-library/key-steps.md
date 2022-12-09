---
title: オファーを作成するための主な手順
description: オファーを作成するために必要な主な手順
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: e375fd3a-b10d-45f4-a95b-ceb48116e841
source-git-commit: c530905eacbdf6161f6449d7a0b39c8afaf3a321
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# オファーを作成および管理するための主な手順 {#key-steps-to-manage-offers}

以下に示すのは、オファーを作成、設定、管理するための主な手順です。

![](../assets/offer-create-manage-process.png)

オファーを設定する方法を示すエンドツーエンドの例については、次のようにして決定し、この決定を電子メール [ ](../offers-e2e.md) で活用してください。

## コンポーネントの作成 {#create-components}

キャンペーンの作成を開始する前に、オファーで使用するいくつかのコンポーネントを定義しておく必要があります。

1. ****&#x200B;提案を作成します。これは、ユーザーの好みに合わせて使用されます。例えば、イメージ形式のみを対象とし、メッセージの上部に表示されるように配置を作成することができます。

1. **条件を指定する意思決定ルール** を作成します。

1. **オファーに関連付けるタグ** を作成すると、容易に整理してライブラリに検索することができます。

1. 特定の配置について最初に提示する必要がある特典を決定するためのルールを定義する場合は、ランク計算式 **を作成することもでき** ます。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-placement.svg" width="60px"><p><a href="../offer-library/creating-placements.md">配置の作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-rules.svg" width="60px"><p><a href="../offer-library/creating-decision-rules.md">決定ルールの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-tags.svg" width="60px"><p><a href="../offer-library/creating-tags.md">タグの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-ranking.svg" width="60px"><p><a href="../ranking/create-ranking-formulas.md">ランク付け式の作成</a></p></td>
</table>

## オファーの作成と管理 {#create-and-manage-offers}

1. **オファー** を作成し、そのコンテンツとプロパティを設定します。

1. **選択されたサービスの対象とならないユーザーに対して表示する最後の手段として使用する予備製品** を作成します。

1. **作成したパーソナライズされたアイテムを含むコレクション** を作成し、それを選択して使用します。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-offer.svg" width="60px"><p><a href="../offer-library/creating-personalized-offers.md">キャンペーンの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-fallback.svg" width="60px"><p><a href="../offer-library/creating-fallback-offers.md">予備製品の作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-collection.svg" width="60px"><p><a href="../offer-library/creating-collections.md">コレクションの作成</a></p></td></tr>
</table>

## 決定事項の作成と設定 {#create-and-configure-decisions}

1. **パーソナライズされた特典と予備の特典が組み合わされた意思決定** を作成します。 この組み合わせを使用して、特定のプロファイルに最適なオファーを見つけるために decisioning engine で使用されます。

1. **決定** を設定します。 これを行うには、配置を選択し、それぞれの配置についてコレクションを選択してから、フォールバックを選択します。

1. 必要に応じて、決定を設定するときに、ランク付け式 **を配置に割り当てることができ** ます。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-decision.svg" width="60px"><p><a href="../offer-activities/create-offer-activities.md">意思決定の作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-configure-decision.svg" width="60px"><p><a href="../offer-activities/create-offer-activities.md#add-offers">決定事項の設定</a></p></td>
<td><img src="../../assets/do-not-localize/icon-assign-ranking.svg" width="60px"><p><a href="../offer-activities/configure-offer-selection.md#assign-ranking-formula">ランキングの割り当て</a></p></td>
</tr>
</table>

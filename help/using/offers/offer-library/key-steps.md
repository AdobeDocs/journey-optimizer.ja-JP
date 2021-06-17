---
title: オファーを作成するための主な手順
description: オファーの作成に必要な主な手順を説明します。
feature: オファー
topic: 統合
role: User
level: Intermediate
source-git-commit: 5631a1937b854c3e14d1816df9e8d30690588303
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 35%

---

# オファーを作成および管理するための主な手順{#key-steps}

オファーの作成、設定、管理および決定での使用に関する主な手順を以下に示します。

![](../../assets/offer-create-manage-process.png)

オファーの設定方法を示すエンドツーエンドの完全な例については、オファーを決定で使用し、この決定をEメールで活用する方法を示しています。[このページ](../offers-e2e.md)を参照してください。

## コンポーネントの作成

オファーの作成を開始する前に、オファーで使用する複数のコンポーネントを定義する必要があります。

1. **配置を作成**&#x200B;します。これは、オファーの表示に使用されるコンテナです。例えば、画像形式のオファー専用で、メッセージの上部に配置するプレースメントを作成できます。

1. オファーを表示する条件を指定する&#x200B;**決定ルールを作成**&#x200B;します。

1. オファーに関連付ける&#x200B;**タグを作成**&#x200B;すると、ライブラリを簡単に整理して検索できます。

1. （オファーの優先順位スコアを考慮するのではなく）特定の配置に対して最初に提示するオファーを決定するルールを定義する場合は、**ランキング式**&#x200B;を作成できます。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-placement.svg" width="60px"><p><a href="../offer-library/creating-placements.md">プレースメントの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-rules.svg" width="60px"><p><a href="../offer-library/creating-decision-rules.md">決定ルールの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-tags.svg" width="60px"><p><a href="../offer-library/creating-tags.md">タグの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-ranking.svg" width="60px"><p><a href="../offer-library/create-ranking-formulas.md">ランキング式の作成</a></p></td>
</table>

## オファーの作成と管理

1. **オファーを作成**&#x200B;し、そのコンテンツとプロパティを設定します。

1. 選択したオファーのいずれにも資格がない場合に、最後の手段として顧客に表示される&#x200B;**フォールバックオファーを作成**&#x200B;します。

1. **コレクションを作** 成し、作成したパーソナライズされたオファーを含めて、それらを決定に使用します。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-offer.svg" width="60px"><p><a href="../offer-library/creating-personalized-offers.md">オファーの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-fallback.svg" width="60px"><p><a href="../offer-library/creating-fallback-offers.md">フォールバックオファーの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-collection.svg" width="60px"><p><a href="../offer-library/creating-collections.md">コレクションの作成</a></p></td></tr>
</table>

## 決定の作成と設定

1. **配置を、パーソ** ナライズされたオファーおよびフォールバックオファーと組み合わせる決定を作成します。この組み合わせは、特定のOffer decisioningに最適なオファーを見つけるためにプロファイルエンジンで使用されます。

1. **決定を設定します**。それには、配置を選択し、各配置に対して、コレクションとフォールバックを選択します。

1. 必要に応じて、決定を設定する際に、配置にランキング式&#x200B;**を割り当てることができます。**

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-decision.svg" width="60px"><p><a href="../offer-activities/create-offer-activities.md">決定の作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-configure-decision.svg" width="60px"><p><a href="../offer-activities/create-offer-activities.md#add-offers">決定の設定</a></p></td>
<td><img src="../../assets/do-not-localize/icon-assign-ranking.svg" width="60px"><p><a href="../offer-activities/configure-offer-selection.md#assign-ranking-formula">ランキングの割り当て</a></p></td>
</tr>
</table>

---
title: オファーを作成するための主な手順
description: オファーの作成に必要な主な手順を説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: e375fd3a-b10d-45f4-a95b-ceb48116e841
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: ht
source-wordcount: '342'
ht-degree: 100%

---

# オファーを作成および管理するための主な手順 {#key-steps}

オファーを作成、設定、管理し、決定に使用するための主な手順を以下に示します。

![](../../assets/offer-create-manage-process.png)

オファーを設定して決定で使用し、この決定をメールで活用する方法を示す完全なエンドツーエンドの例については、[このページ](../offers-e2e.md)を参照してください。

## コンポーネントの作成

オファーの作成を開始する前に、オファーで使用する複数のコンポーネントを定義する必要があります。

1. **プレースメントを作成**&#x200B;します。プレースメントは、オファーを紹介するためのコンテナです。例えば、画像形式のオファー専用で、メッセージの上部に配置するプレースメントを作成できます。

1. オファーを表示する条件を指定する&#x200B;**決定ルールを作成**&#x200B;します。

1. オファーに関連付ける&#x200B;**タグを作成**&#x200B;すると、ライブラリを簡単に整理して検索できます。

1. （オファーの優先度スコアを考慮するのではなく）特定のプレースメントに対して最初に提示するオファーを決定するルールを定義する場合は、**ランキング式**&#x200B;を作成できます。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-placement.svg" width="60px"><p><a href="../offer-library/creating-placements.md">プレースメントの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-rules.svg" width="60px"><p><a href="../offer-library/creating-decision-rules.md">決定ルールの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-tags.svg" width="60px"><p><a href="../offer-library/creating-tags.md">タグの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-ranking.svg" width="60px"><p><a href="../offer-library/create-ranking-formulas.md">ランキング式の作成</a></p></td>
</table>

## オファーの作成と管理

1. **オファーを作成**&#x200B;し、そのコンテンツとプロパティを設定します。

1. **フォールバックオファーを作成**&#x200B;します。これは、顧客が選択したオファーのいずれにも資格がない場合に表示する最後の手段です。

1. **コレクションを作成**&#x200B;し、作成したパーソナライズされたオファーを含めて、それらを決定に使用します。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-offer.svg" width="60px"><p><a href="../offer-library/creating-personalized-offers.md">オファーの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-fallback.svg" width="60px"><p><a href="../offer-library/creating-fallback-offers.md">フォールバックオファーの作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-collection.svg" width="60px"><p><a href="../offer-library/creating-collections.md">コレクションの作成</a></p></td></tr>
</table>

## 決定の作成と設定

1. パーソナライズされたオファーおよびフォールバックオファーとプレースメントを組み合わせる&#x200B;**決定を作成**&#x200B;します。この組み合わせは、Offer Decisioning エンジンが特定のプロフィールに最適なオファーを見つけるために使用されます。

1. **決定を設定します**。そのためには、プレースメントを選択し、各プレースメントに対してコレクションとフォールバックを選択します。

1. 必要に応じて、決定を設定する際に、プレースメントに&#x200B;**ランキング式を割り当てる**&#x200B;ことができます。

<table>
<tr>
<td><img src="../../assets/do-not-localize/icon-decision.svg" width="60px"><p><a href="../offer-activities/create-offer-activities.md">決定の作成</a></p></td>
<td><img src="../../assets/do-not-localize/icon-configure-decision.svg" width="60px"><p><a href="../offer-activities/create-offer-activities.md#add-offers">決定の設定</a></p></td>
<td><img src="../../assets/do-not-localize/icon-assign-ranking.svg" width="60px"><p><a href="../offer-activities/configure-offer-selection.md#assign-ranking-formula">ランキングの割り当て</a></p></td>
</tr>
</table>

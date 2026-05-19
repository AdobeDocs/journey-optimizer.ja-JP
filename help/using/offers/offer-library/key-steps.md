---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: オファーを作成するための主な手順
description: オファーの作成に必要な主な手順を見つける
badge: label="レガシー" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: e375fd3a-b10d-45f4-a95b-ceb48116e841
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/26dKfdb1fhdF0bGpilYam-2bzuJZPjFYGeKy3ni0dzE
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: c132d929-fa62-4271-803e-b823be07b914id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 364
ht-degree: 95%

---

# オファーを作成および管理する主要ステップ {#key-steps-to-manage-offers}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

オファーを作成、設定、管理し、決定に使用するための主な手順を以下に示します。

![](../assets/offer-create-manage-process.png)

オファーを設定して決定で使用し、この決定をメールで活用する方法を示す完全なエンドツーエンドの例については、[このページ](../offers-e2e.md)を参照してください。

## コンポーネントの作成 {#create-components}

オファーの作成を開始する前に、オファーで使用する複数のコンポーネントを定義する必要があります。

1. [プレースメントを作成](creating-placements.md)します。プレースメントは、オファーを紹介するためのコンテナです。 例えば、画像形式のオファー専用で、メッセージの上部に配置するプレースメントを作成できます。

1. オファーを表示する条件を指定する[決定ルールを作成](creating-decision-rules.md)します。

1. オファーに関連付ける[コレクション修飾子を作成](creating-tags.md)すると（旧称「タグ」）、ライブラリを簡単に整理して検索できます。

1. （オファーの優先度スコアを考慮するのではなく）特定のプレースメントに対して最初に提示するオファーを決定するルールを定義する場合は、[ランキング式](../ranking/create-ranking-formulas.md)を作成できます。

<!--
<table style="table-layout:fixed">
<tr style="border: 0;">
<td>
<img src="../../assets/do-not-localize/icon-placement.svg" width="60px">
<div>
<a href="../offer-library/creating-placements.md">Create placements</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-rules.svg" width="60px">
<div>
<a href="../offer-library/creating-decision-rules.md">Create decision rules</a>
</div>
<p>
<td>
<img src="../../assets/do-not-localize/icon-tags.svg" width="60px">
<div>
<a href="../offer-library/creating-tags.md">Create collection qualifiers</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-ranking.svg" width="60px">
<div>
<a href="../ranking/create-ranking-formulas.md">Create ranking formulas</a>
</div>
<p>
</td>
</tr>
</table>
-->

## オファーの作成と管理 {#create-and-manage-offers}

1. [オファーを作成](creating-personalized-offers.md)し、そのコンテンツとプロパティを設定します。 オファーのコンテンツ（表示域）をパーソナライズする場合は、特定の関数のみがサポートされます。パーソナライゼーションエディターでサポートされている関数[を参照してください](personalization-editor-supported-functions.md)。

1. [フォールバックオファーを作成](creating-fallback-offers.md)します。これは、顧客が選択したオファーのいずれにも資格がない場合に表示する最後の手段です。

1. [コレクションを作成](creating-collections.md)し、作成したパーソナライズされたオファーを含めて、それらを決定に使用します。

<!--
<table style="table-layout:fixed">
<tr style="border: 0;">
<td>
<img src="../../assets/do-not-localize/icon-offer.svg" width="60px">
<div>
<a href="../offer-library/creating-personalized-offers.md">Create offers</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-fallback.svg" width="60px">
<div>
<a href="../offer-library/creating-fallback-offers.md">Create fallback offers</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-collection.svg" width="60px">
<div>
<a href="../offer-library/creating-collections.md">Create collections</a>
</div>
<p>
</td>
</tr>
</table>
-->

## 決定の作成と設定 {#create-and-configure-decisions}

1. パーソナライズされたオファーおよびフォールバックオファーとプレースメントを組み合わせる[決定を作成](../offer-activities/create-offer-activities.md)します。 この組み合わせは、意思決定エンジンが特定のプロファイルに最適なオファーを見つけるために使用されます。

1. [決定を設定します](../offer-activities/create-offer-activities.md#add-decision-scopes)。 そのためには、プレースメントを選択し、各プレースメントに対してコレクションとフォールバックを選択します。

1. 必要に応じて、決定を設定する際に、プレースメントに[ランキング式](../offer-activities/configure-offer-selection.md#assign-ranking-formula)または [AI ランキング](../offer-activities/configure-offer-selection.md#use-ranking-strategy)を割り当てることができます。

<!--
<table style="table-layout:fixed">
<tr style="border: 0;">
<td>
<img src="../../assets/do-not-localize/icon-decision.svg" width="60px">
<div>
<a href="../offer-activities/create-offer-activities.md">Create decisions</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-configure-decision.svg" width="60px">
<div>
<a href="../offer-activities/create-offer-activities.md#add-offers">Configure decisions</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-assign-ranking.svg" width="60px">
<div>
<a href="../offer-activities/configure-offer-selection.md#assign-ranking-formula">Assign ranking</a>
</div>
<p>
</td>
</tr>
</table>
-->
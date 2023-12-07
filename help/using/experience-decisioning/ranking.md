---
title: ランキング方法
description: ランキング方法の使用方法を学ぶ
feature: Experience Decisioning, Ranking
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: c1d69bc9-4486-4037-b218-f4f704b2ba9c
source-git-commit: c13cd73229b2fab80722663afae9fe24b660c0f9
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 86%

---

# ランキング方法 {#rankings}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_formulas"
>title="ランキング式の作成"
>abstract="式を使用すると、項目の優先度スコアを考慮するのではなく、最初に提示する項目を決定するルールを定義できます。ランキング方法を作成したら、その方法を決定戦略に割り当てて、最初に選択する項目を定義できます。"

>[!BEGINSHADEBOX &quot;このドキュメントガイドの内容&quot;]

* [Offer Decisioning の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目を管理します。 [項目カタログを設定](catalogs.md) - [決定項目の作成](items.md) - [項目コレクションを管理](collections.md)
* 項目の選択を設定： [決定ルールの作成](rules.md) - **[ランキングメソッドの作成](ranking.md)**
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーを作成](create-decision.md)

>[!ENDSHADEBOX]

ランキング方法を使用すると、特定のプロファイルに対して表示する項目をランク付けできます。ランキング方法を作成したら、その方法を決定戦略に割り当てて、最初に選択する項目を定義できます。

ランキング方法には、**[!UICONTROL 設定]**／**[!UICONTROL ランキング方法]**&#x200B;メニューからアクセスします。次の 2 種類のランキング方法が使用できます。

* **式**&#x200B;を使用すると、項目の優先度スコアを考慮するのではなく、最初に提示する項目を決定するルールを定義できます。

* **AI モデル**&#x200B;を使用すると、複数のデータポイントを活用するトレーニング済みモデルシステムを使用して、最初に提示する項目を決定できます。

![](assets/ranking-create.png)

ランキング方法の各タイプとその作成方法について詳しくは、次の意思決定管理ドキュメントを参照してください。

* [ランキング式](../offers/ranking/create-ranking-formulas.md)
* [AI モデル](../offers/ranking/ai-models.md)

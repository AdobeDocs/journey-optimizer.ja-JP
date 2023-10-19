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
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 100%

---

# ランキング方法 {#rankings}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [Offer Decisioning の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目の管理
   * [項目カタログの設定](catalogs.md)
   * [決定項目の作成](items.md)
   * [項目コレクションの管理](collections.md)
* 項目の選択の設定
   * [決定ルールの作成](rules.md)
   * **[ランキング方法の作成](ranking.md)**
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)

>[!ENDSHADEBOX]

ランキング方法を使用すると、特定のプロファイルに対して表示する項目をランク付けできます。ランキング方法を作成したら、その方法を決定戦略に割り当てて、最初に選択する項目を定義できます。

ランキング方法には、**[!UICONTROL 設定]**／**[!UICONTROL ランキング方法]**&#x200B;メニューからアクセスします。次の 2 種類のランキング方法が使用できます。

* **式**&#x200B;を使用すると、項目の優先度スコアを考慮するのではなく、最初に提示する項目を決定するルールを定義できます。

* **AI モデル**&#x200B;を使用すると、複数のデータポイントを活用するトレーニング済みモデルシステムを使用して、最初に提示する項目を決定できます。

![](assets/ranking-create.png)

ランキング方法の各タイプとその作成方法について詳しくは、次の意思決定管理ドキュメントを参照してください。

* [ランキング式](../offers/ranking/create-ranking-formulas.md)
* [AI モデル](../offers/ranking/ai-models.md)

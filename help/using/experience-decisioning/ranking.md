---
title: ランキングメソッド
description: ランキングメソッドの使用方法を説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: c1d69bc9-4486-4037-b218-f4f704b2ba9c
source-git-commit: c4ab97999d000d969f6f09f4d84be017d1288f94
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 25%

---

# ランキングメソッド {#rankings}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [エクスペリエンス判定の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目の管理
   * [項目カタログの設定](catalogs.md)
   * [決定項目の作成](items.md)
   * [項目コレクションの管理](collections.md)
* 項目の選択の設定
   * [決定ルールの作成](rules.md)
   * **[ランキングメソッドの作成](ranking.md)**
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)

>[!ENDSHADEBOX]

ランキングメソッドを使用すると、特定のプロファイルに対して表示する項目をランク付けできます。 ランキングメソッドを作成したら、そのメソッドを判定戦略に割り当てて、最初に選択する項目を定義できます。

ランキングメソッドには、 **[!UICONTROL 設定]** / **[!UICONTROL ランキングメソッド]** メニュー。 次の 2 種類のランキングメソッドを使用できます。

* **数式** を使用すると、項目の優先度スコアを考慮するのではなく、最初に表示する項目を決定するルールを定義できます。

* **AI モデル** を使用すると、複数のデータポイントを活用して、最初に表示する項目を決定する、トレーニング済みモデルシステムを使用できます。

![](assets/ranking-create.png)

各タイプのランキング方法とその作成方法に関する詳細については、次の URL にある決定管理ドキュメントを参照してください。

* [ランキング式](../offers/ranking/create-ranking-formulas.md)
* [AI モデル](../offers/ranking/ai-models.md)

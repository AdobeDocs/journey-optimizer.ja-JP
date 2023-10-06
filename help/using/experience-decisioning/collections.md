---
title: コレクション
description: コレクションの操作方法を学ぶ
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 099d1439-34f7-47fe-9181-0e9ce2032a01
source-git-commit: c4ab97999d000d969f6f09f4d84be017d1288f94
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 20%

---

# コレクション {#collections}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [エクスペリエンス判定の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目の管理
   * [項目カタログの設定](catalogs.md)
   * [決定項目の作成](items.md)
   * **[項目コレクションの管理](collections.md)**
* 項目の選択の設定
   * [決定ルールの作成](rules.md)
   * [ランキングメソッドの作成](ranking.md)
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)

>[!ENDSHADEBOX]

コレクションを使用すると、好みに応じて判定項目を分類およびグループ化できます。 これらのカテゴリは、決定項目の属性を活用するルールを作成することで作成されます。

例えば、決定項目のカタログスキーマに「カテゴリ」カスタム属性を追加したとします。 これにより、「カテゴリ」属性に「ヨガ」値を持つすべての判定項目を含むコレクションを作成できます。

コレクションのリストには、 **[!UICONTROL 項目]** メニュー。

コレクションを作成するには、次の手順に従います。

1. に移動します。 **[!UICONTROL 項目]** > **[!UICONTROL コレクション]** をクリックします。 **[!UICONTROL コレクションを作成]**.
1. コレクションの名前と説明を入力します。
1. 1 つまたは複数のルールを追加して、コレクションに含める項目を決定します。 その手順は次のとおりです。

   1. 基準として使用する項目属性を選択します。 属性リストには、カタログスキーマで定義されているすべての標準属性とカスタム属性が含まれます。 [項目のカタログの詳細を表示](catalogs.md)
   1. 目的の演算子を選択し、フィルターに使用する値を入力します。
   1. この手順を繰り返して、必要な数のルールを追加します。 複数のルールを追加する場合、 **および** および **または** 演算子を使用して組み合わせることができます。 これをおこなうには、オペレーターバッジをクリックして、2 つの選択肢を切り替えます。

   ![](assets/collection-create.png)

1. 収集ルールを定義したら、「 **[!UICONTROL 作成]**. コレクションがリストに表示されます。

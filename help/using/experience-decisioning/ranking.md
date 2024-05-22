---
title: ランキング方法
description: ランキング方法の使用方法を学ぶ
feature: Experience Decisioning, Ranking
topic: Integrations
role: User
level: Intermediate
badge: label="限定提供"
exl-id: c1d69bc9-4486-4037-b218-f4f704b2ba9c
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---

# ランキング方法 {#rankings}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_formulas"
>title="ランキング式の作成"
>abstract="式を使用すると、項目の優先度スコアを考慮するのではなく、最初に提示する項目を決定するルールを定義できます。ランキング方法を作成したら、その方法を選択戦略に割り当てて、最初に選択する項目を定義できます。"

ランキング方法を使用すると、特定のプロファイルに対して表示する項目をランク付けできます。ランキング方法を作成したら、その方法を選択戦略に割り当てて、最初に選択する項目を定義できます。

次の 2 種類のランキング方法が使用できます。

* **式**&#x200B;を使用すると、項目の優先度スコアを考慮するのではなく、最初に提示する項目を決定するルールを定義できます。

* **AI モデル**&#x200B;を使用すると、複数のデータポイントを活用するトレーニング済みモデルシステムを使用して、最初に提示する項目を決定できます。

## ランキング方法の作成 {#create}

ランキング方法を作成するには、次の手順に従います。

1. **[!UICONTROL 戦略の設定]**&#x200B;メニューに移動し、使用するランキングのタイプに応じて&#x200B;**[!UICONTROL 数式]**&#x200B;または **[!UICONTROL AI モデル]**&#x200B;メニューを選択します。

1. 画面の右上隅にある「**[!UICONTROL 数式を作成]**」または「**[!UICONTROL AI モデルを作成]**」ボタンをクリックします。

   ![](assets/ranking-create.png)

1. ニーズに合わせて数式または AI モデルを設定して、保存します。

   ランキング式と AI モデルを作成する方法について詳しくは、意思決定管理ドキュメントを参照してください。

   * [ランキング式](../offers/ranking/create-ranking-formulas.md)
   * [AI モデル](../offers/ranking/ai-models.md)


## 数式での決定項目属性の活用 {#items}

ランキング式は **PQL 構文**&#x200B;で表され、プロファイル属性、[コンテキストデータ](context-data.md)、決定項目に関連する属性などの様々な属性を利用できます。

数式で決定項目に関連する属性を活用するには、ランキング式のコードで以下の構文に従っていることを確認してください。詳しくは、各節を展開してください。

+++決定項目の標準属性の活用

![](assets/formula-attribute.png)

+++

+++決定項目のカスタム属性の活用

![](assets/formula-attribute-custom.png)

+++

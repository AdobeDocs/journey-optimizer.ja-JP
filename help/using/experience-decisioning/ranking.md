---
title: ランキング方法
description: ランキング方法の使用方法を学ぶ
feature: Experience Decisioning, Ranking
topic: Integrations
role: User
level: Intermediate
badge: label="限定提供"
exl-id: c1d69bc9-4486-4037-b218-f4f704b2ba9c
source-git-commit: 018ff365780c5064afd94c8f842ca0498fe06065
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 55%

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

+++ カスタム [!DNL Customer Journey Analytics] 指標でのモデルの最適化

>[!NOTE]
>
>この機能は、管理者権限を持つ [!DNL Customer Journey Analytics] 顧客のみが使用できます。
>
>開始する前に、Journey Optimizer データセットをデフォルトのデータビューに書き出すために、Journey OptimizerとCustomer Journey Analyticsが統合されていることを確認してください。 [ でデータを活用する方法  [!DNL Journey Optmizer]  学ぶ  [!DNL Customer Journey Analytics]](../reports/cja-ajo.md)

パーソナライズされた最適化モデルは、ビジネス目標を定義し、顧客データを活用して、パーソナライズされたオファーを提供し、KPI を最大化するためのビジネス指向モデルをトレーニングできる AI モデルの一種です。 パーソナライズされた AI モデルを作成する方法について詳しくは、[ 意思決定管理ドキュメント ](../offers/ranking/personalized-optimization-model.md) を参照してください。

デフォルトでは、パーソナライズされた最適化モデルは、最適化指標として **オファークリック数** を使用します。 [!DNL Customer Journey Analytics] を使用している場合は、独自のカスタム指標 [!DNL Decisioning] 活用してモデルを最適化できます。

これを行うには、パーソナライズされた AI モデル作成画面にアクセスし、「**[!UICONTROL コンバージョンイベント]**」ドロップダウンを展開します。 デフォルトの [!DNL Customer Journey Analytics] データビュー [ のすべての指標 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views){target="_blank"} リストに表示されます。 モデルを最適化する指標を選択し、通常どおり AI モデルの作成を完了します。

![](assets/ai-ranking-custom-metrics.png)

>[!NOTE]
>
>デフォルトでは、[!DNL Customer Journey Analytics] の指標は「ラストタッチ」アトリビューションモデルを使用し、コンバージョンの直前に発生したタッチポイントにクレジットの 100% を割り当てます。
>
>アトリビューションモデルは変更できますが、すべてのアトリビューションモデルが AI モデルの最適化に最適とは限りません。 モデルの精度とパフォーマンスを確保するために、最適化目標に合ったアトリビューションモデルを慎重に選択することをお勧めします。
>
>使用可能なアトリビューションモデルとその使用に関するガイダンスについて詳しくは、[[!DNL Customer Journey Analytics]  ドキュメント ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/attribution){target="_blank"} を参照してください。

+++

## 数式での決定項目属性の活用 {#items}

ランキング式は **PQL 構文**&#x200B;で表され、プロファイル属性、[コンテキストデータ](context-data.md)、決定項目に関連する属性などの様々な属性を利用できます。

数式で決定項目に関連する属性を活用するには、ランキング式のコードで以下の構文に従っていることを確認してください。詳しくは、各節を展開してください。

+++決定項目の標準属性の活用

![](assets/formula-attribute.png)

+++

+++決定項目のカスタム属性の活用

![](assets/formula-attribute-custom.png)

+++

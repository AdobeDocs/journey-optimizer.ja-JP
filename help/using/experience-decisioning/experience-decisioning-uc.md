---
title: エクスペリエンス判定の使用例
description: コードベースのチャネルでの実験を使用して、意思決定を作成する方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 18%

---

# エクスペリエンス判定の使用例 {#experience-decisioning-uc}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [エクスペリエンス判定の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目の管理
   * [項目カタログの設定](catalogs.md)
   * [決定項目の作成](items.md)
   * [項目コレクションの管理](collections.md)
* 項目の選択の設定
   * [決定ルールの作成](rules.md)
   * [ランキングメソッドの作成](ranking.md)
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)
* **[使用例を通じて学ぶ](experience-decisioning-uc.md)**

>[!ENDSHADEBOX]

この使用例では、異なる判定ポリシーを含む 2 つの配信処理を定義し、ターゲットオーディエンスに対して最も効果が高い配信を測定します。

## 品目と戦略の作成

最初に、項目を作成し、コレクションにグループ化し、ルールとランキングメソッドを設定する必要があります。 これらの要素を使用すると、選択戦略を構築できます。

1. に移動します。 **[!UICONTROL エクスペリエンス判定]** > **[!UICONTROL 項目]** 複数のオファー項目を作成します。 オーディエンスまたはルールを使用して制約を設定し、各項目を特定のプロファイルのみに制限します。 [詳細情報](items.md)

   <!--
   1. From the items list, click the **[!UICONTROL Edit schema]** button  and edit the custom attributes if needed. [Learn how to work with catalogs](catalogs.md)-->

1. 作成 **コレクション** を使用して、好みに応じて判定項目を分類およびグループ化します。 [詳細情報](collections.md)

1. 作成 **決定ルール** を使用して、どの決定項目を表示できるかを決定します。 [詳細情報](rules.md)

1. 作成 **ランキングメソッド** を選択し、判定戦略内で適用して、判定項目の選択の優先順位を決定します。 [詳細情報](ranking.md)

1. ビルド **選択戦略** コレクション、決定ルール、ランキング方法を活用して、プロファイルへの表示に適した決定項目を特定する [詳細情報](selection-strategies.md)

## 決定ポリシーの作成

Web サイトやモバイルアプリで訪問者に最適な動的なオファーやエクスペリエンスを提示するには、コードベースのキャンペーンに決定ポリシーを追加します。

それぞれ異なる判定ポリシーを含む 2 つの配信処理を定義します。

1. キャンペーンを作成し、 **[!UICONTROL コードベースのエクスペリエンス（ベータ版）]** アクション。 [詳細情報](../code-based/create-code-based.md)

   >[!NOTE]
   >
   >コードベースのエクスペリエンス機能は、現在、一部のユーザーのみが利用できるベータ版として利用できます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。

1. キャンペーンの概要ページで、「 **[!UICONTROL 実験を作成]** をクリックして、content experiment の設定を開始します。 [詳細情報](../campaigns/content-experiment.md)

1. を選択します。 **[!UICONTROL 決定]** アイコン、クリック **[!UICONTROL 決定の作成]** 決定の詳細を入力します。 [詳細情報](create-decision.md)

   ![](assets/decision-code-based-create.png)

1. 決定の選択戦略を定義します。 クリック **[!UICONTROL 方法を追加]**.

1. 「**[!UICONTROL 作成]**」をクリックします。新しい決定が以下に追加されます。 **[!UICONTROL 決定]**.

   ![](assets/decision-code-based-decision-added.png)

1. その他のアクションアイコン（3 つのドット）をクリックし、「 」を選択します。 **[!UICONTROL 追加]**. これで、必要なすべての決定属性をこの内部に追加できます。

   ![](assets/decision-code-based-add-decision.png)

1. また、式エディタで使用できる他のアトリビュート（プロファイルアトリビュートなど）を追加することもできます。

   ![](assets/decision-code-based-decision-profile-attribute.png)

1. 治療 B を構築し、上記の手順を繰り返して、別の決定を作成します。

1. コンテンツを保存します。



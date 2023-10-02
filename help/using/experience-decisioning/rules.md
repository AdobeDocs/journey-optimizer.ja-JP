---
title: 判定ルール
description: 決定ルールの操作方法を説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 033a11b8-c848-4e4a-b6f0-62fa0a2152bf
source-git-commit: 7437268e87cc2c71bec394fbef1b512b31946cf5
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 8%

---

# 判定ルール {#rules}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [Experience Decisioning の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目を管理
   * [項目カタログを設定](catalogs.md)
   * [決定項目の作成](items.md)
   * [項目コレクションを管理](collections.md)
* 項目の選択を設定
   * **[決定ルールの作成](rules.md)**
   * [ランキングメソッドの作成](ranking.md)
* [選択戦略を作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)

>[!ENDSHADEBOX]

決定ルールを使用すると、決定項目レベルで直接または特定の選択戦略内で制約を適用することで、決定項目のオーディエンスを定義できます。 これにより、どのアイテムを誰に提示するかを正確に制御できます。

例えば、女性向けに設計されたヨガ関連の製品を使用した判定項目があるシナリオを考えてみましょう。 決定ルールを使用すると、これらの項目を、性別が「女性」で、「ヨガ」に「目標地点」を示したプロファイルにのみ表示するように指定できます。

項目および選択戦略レベルの決定ルールに加えて、キャンペーンレベルで、意図したオーディエンスに対して追加のパラメーターを作成することもできます。 [詳細情報](../campaigns/create-campaign.md)

決定ルールのリストには、 **[!UICONTROL 設定]** / **[!UICONTROL 決定ルール]** メニュー。

<!--![](assets/decision-rules-list.png)-->

>[!IMPORTANT]
>
>現時点では、決定ルールはJourney Optimizerを使用して管理されます **決定管理** メニュー。 その結果、 **[!UICONTROL 決定ルール]** Experience Decisioning のリストには、Journey Optimizerの両方から作成されたルールが含まれます **[!UICONTROL 決定管理]** または **[!UICONTROL エクスペリエンス判定]** メニュー。

コレクションを作成するには、次の手順に従います。

1. に移動します。 **[!UICONTROL 設定]** / **[!UICONTROL 決定ルール]**.
1. Journey Optimizerの決定管理ユーザーインターフェイスが中央の領域に表示されます。 詳しくは、 [決定管理ドキュメント](../offers/offer-library/creating-decision-rules.md) を使用して、必要に応じてルールを作成します。

1. ルールを作成すると、そのルールがリストに表示され、決定項目と選択戦略で使用して、決定項目のプロファイルへの表示を制御できます。

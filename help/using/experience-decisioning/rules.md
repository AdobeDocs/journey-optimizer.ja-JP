---
title: 決定ルール
description: 決定ルールの操作方法を学ぶ
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 033a11b8-c848-4e4a-b6f0-62fa0a2152bf
source-git-commit: c13cd73229b2fab80722663afae9fe24b660c0f9
workflow-type: ht
source-wordcount: '323'
ht-degree: 100%

---

# 決定ルール {#rules}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_rules"
>title="決定ルールの作成"
>abstract="決定ルールを使用すると、決定項目レベルで直接、または特定の選択戦略内で制約を適用することで、決定項目のオーディエンスを定義できます。これにより、アイテムを提示する対象を正確に制御できます。"

>[!BEGINSHADEBOX 「このドキュメントガイドの内容は次のとおりです」]

* [Experience Decisioning の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目の管理：[項目カタログの設定](catalogs.md) - [決定項目の作成](items.md) - [項目コレクションの管理](collections.md)
* 項目の選択の設定：**[決定ルールの作成](rules.md)** - [ランキングメソッドの作成](ranking.md)
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーを作成](create-decision.md)

>[!ENDSHADEBOX]

決定ルールを使用すると、決定項目レベルで直接、または特定の選択戦略内で制約を適用することで、決定項目のオーディエンスを定義できます。これにより、アイテムを提示する対象を正確に制御できます。

例えば、女性向けに作られたヨガ関連製品を特集した決定項目があるシナリオを考えてみましょう。決定ルールを使用すると、性別が「女性」で、「ヨガ」に「Point of Interest」を示したプロファイルにのみ、これらの項目を表示するように指定できます。

>[!NOTE]
>
>項目および選択戦略レベルの決定ルールに加えて、キャンペーンレベルで意図したオーディエンスを定義することもできます。[詳細情報](../campaigns/create-campaign.md#audience)


決定ルールのリストには、**[!UICONTROL 設定]**／**[!UICONTROL 決定ルール]**&#x200B;メニューからアクセスできます。

<!--![](assets/decision-rules-list.png)-->

>[!IMPORTANT]
>
>現時点では、決定ルールは Journey Optimizer の&#x200B;**意思決定管理**&#x200B;メニューを使用して管理されています。その結果、エクスペリエンス判定の&#x200B;**[!UICONTROL 決定ルール]**&#x200B;リストには、Journey Optimizer **[!UICONTROL 意思決定管理]**&#x200B;または&#x200B;**[!UICONTROL エクスペリエンス判定]**&#x200B;メニューの両方から作成されたルールが含まれます。

ルールを作成するには、次の手順に従います。

1. **[!UICONTROL 設定]**／**[!UICONTROL 決定ルール]**&#x200B;に移動します。
1. Journey Optimizer の意思決定管理ユーザーインターフェイスが中央の領域に表示されます。[決定管理ドキュメント](../offers/offer-library/creating-decision-rules.md)に詳しく記載されている手順に従い、必要に応じてルールを作成します。

1. ルールを作成すると、そのルールがリストに表示され、決定項目と選択戦略で使用して、決定項目のプロファイルへの表示を制御できます。

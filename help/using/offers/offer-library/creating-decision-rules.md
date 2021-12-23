---
title: 決定ルールの作成
description: Adobe Experience Platform での決定ルールを作成する方法を説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 401ce05b-412b-4fa0-a516-bf75727f6387
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---

# 決定ルールの作成 {#creating-decision-rules}

Adobe Experience Platform で利用可能なデータに基づいて、オファーの決定ルールを作成できます。決定ルールは、オファーを表示する対象を決定します。

例えば、性別が女性で地域が北東部の場合にのみ「婦人冬服」オファーを表示するように指定できます。

➡️ [ビデオでこの機能を確認する](#video)

作成した決定ルールのリストには、 **[!UICONTROL コンポーネント]**&#x200B;メニューからアクセスできます。

![](../../assets/decision_rules_list.png)

決定ルールを作成するには、次の手順に従います。

1. 「**[!UICONTROL ルール]**」タブに移動し、「**[!UICONTROL ルールを作成]**」をクリックします。

   ![](../../assets/offers_decision_rule_creation.png)

1. ルールに名前を付け、説明を入力したあと、ルールを必要に応じて設定します。

   それには、ルールの条件の作成に役立つ&#x200B;**セグメントビルダー**&#x200B;を使用できます。[詳細情報](../../segment/about-segments.md)

   この例では、「ゴールド」ロイヤルティレベルの顧客がルールのターゲットになります。

   ![](../../assets/offers_decision_rule_creation_segment.png)

   >[!NOTE]
   >
   >決定ルールを作成するために用意されているセグメントビルダーは、**[!UICONTROL Audience Destinations]** サービスで使用されるものと比較して、特異性がいくつかあります。例えば、「**[!UICONTROL セグメント]**」タブは使用できません。ただし、セグメントビルダーのドキュメントで説明されているグローバルプロセスは、オファーの決定ルールを作成する場合にも有効です。

1. 「**[!UICONTROL 保存]**」をクリックして確認します。

1. ルールを作成すると、ルールリストに表示されます。選択するとプロパティが表示され、編集することも削除することもできます。

   ![](../../assets/rule_created.png)

>[!CAUTION]
>
>イベントベースのオファーは、現在 [!DNL Journey Optimizer] ではサポートされていません。 [イベント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=ja#events){target=&quot;_blank&quot;}に基づいて決定ルールを作成しても、それをオファーで活用することはできません。

## チュートリアルビデオ {#video}

>[!NOTE]
>
>このビデオは、Adobe Experience Platformで構築された Offer Decisioning アプリケーションサービスに当てはまります。ただし、Journey Optimizer のコンテキストでオファーを使用する際の一般的なガイダンスを提供しています。

>[!VIDEO](https://video.tv.adobe.com/v/329373?quality=12)

---
title: 決定ルールの作成
description: Adobe Experience Platform での決定ルールを作成する方法を説明します。
source-git-commit: 741fe2b614e3ded57c4a7ecd9b7333bdd99ab359
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 97%

---

# 決定ルールの作成 {#creating-decision-rules}

Adobe Experience Platform で利用可能なデータに基づいて、オファーの決定ルールを作成できます。決定ルールは、オファーを表示する対象を決定します。

例えば、性別が女性で地域が北東部の場合にのみ「婦人冬服」オファーを表示するように指定できます。

![](../../assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

作成した決定ルールのリストには、**[!UICONTROL コンポーネント]**&#x200B;メニューからアクセスできます。

![](../../assets/decision_rules_list.png)

決定ルールを作成するには、次の手順に従います。

1. 「**[!UICONTROL ルール]**」タブに移動し、「**[!UICONTROL ルールを作成]**」をクリックします。

   ![](../../assets/offers_decision_rule_creation.png)

1. ルールに名前を付け、説明を入力し、必要に応じてルールを設定します。

   これをおこなうには、Adobe Experience Platform の&#x200B;**セグメントビルダー**&#x200B;を使用して、ルールの条件を作成できます。使用方法について詳しくは、[専用のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html)を参照してください。

   この例では、「ゴールド」ロイヤルティレベルの顧客をターゲットします。

   ![](../../assets/offers_decision_rule_creation_segment.png)

   >[!NOTE]
   >
   >決定ルールを作成するために用意されているセグメントビルダーは、**[!UICONTROL Audience Destinations]** サービスで使用されるものと比較して、特異性がいくつかあります。例えば、「**[!UICONTROL セグメント]**」タブは使用できません。ただし、セグメントビルダーのドキュメントで説明されているグローバルプロセスは、オファーの決定ルールを作成する場合にも有効です。

1. 「**[!UICONTROL 保存]**」をクリックして確認します。

1. ルールを作成すると、ルールリストに表示されます。選択するとプロパティが表示され、編集することも削除することもできます。

   ![](../../assets/rule_created.png)

## チュートリアルビデオ {#video}

>[!NOTE]
>
>このビデオは、Adobe Experience Platformで構築された Offer Decisioning アプリケーションサービスに当てはまります。ただし、Journey Optimizer のコンテキストでオファーを使用する際の一般的なガイダンスを提供しています。

>[!VIDEO](https://video.tv.adobe.com/v/329373?quality=12)

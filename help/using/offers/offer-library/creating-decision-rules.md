---
title: 決定ルールの作成
description: 「オファーを表示可能」を定義するための意思決定ルールの作成方法について説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 401ce05b-412b-4fa0-a516-bf75727f6387
source-git-commit: 55d9befff9b9bf1bc81c6553cd76f015fdd3116e
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# 決定ルールの作成 {#create-decision-rules}

Adobe エクスペリエンスプラットフォームのデータに基づいた意思決定ルールを作成することができます。 決定ルールは、どのユーザーにどのオファーが表示されるかを決定するために使用されます。

例えば、「女性」と「女性」および「地域 = 「北東」」の場合にのみ表示されるように指定することができます。

➡️ [ ビデオでのこの機能の検出](#video)

作成した判断規則のリストは、メニューからアクセスでき **[!UICONTROL Components]** ます。

![](../assets/decision_rules_list.png)

決定ルールを作成するには、次の手順に従います。

1. タブに移動して **[!UICONTROL Rules]** 、をクリック **[!UICONTROL Create rule]** します。

   ![](../assets/offers_decision_rule_creation.png)

1. ルールの名前と説明を入力します。その後、必要に応じてルールを設定します。

   これを行うために、セグメントビルダー **を使用して** ルールの条件を作成できます。[詳細情報](../../segment/about-segments.md)

   <!--In this example, the rule will target customers that have the "Gold" loyalty level.-->

   ![](../assets/offers_decision_rule_creation_segment.png)

   >[!NOTE]
   >
   >Decision rules を作成するためのセグメントビルダーには、このサービスで **[!UICONTROL Audience Destinations]** 使用されるものと比較して、特定の項目が含まれています。 例えば、 **[!UICONTROL Segments]** このタブを使用することはできません。 ただし、セグメントビルダー ](../../segment/about-segments.md) マニュアルに [ 記載されているグローバルプロセスは、意志決定ルールを作成する場合でも有効です。詳細については、Adobe エクスペリエンスプラットフォームセグメンテーションサービスのマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html) を参照して [ ください。

1. ワークスペースで新しいフィールドを追加および設定すると、 **[!UICONTROL Segment properties]** そのセグメントに属する見積もりプロファイルに関する情報がペインに表示されます。 データを更新するには、をクリック **[!UICONTROL Refresh estimate]** します。

   ![](../assets/offers_decision_rule_creation_estimate.png)

   >[!NOTE]
   >
   >ルールパラメーターには、プロファイルにないデータ (コンテキストデータなど) が含まれている場合は、プロファイル見積を使用できません。 例えば、現在の気象に80度の≥が必要な適格性ルールを指定します。

1. 「確認」をクリック **[!UICONTROL Save]** します。

1. ルールを作成すると、そのルールがリストに **[!UICONTROL Rules]** 表示されます。 このオプションを選択して、プロパティを表示したり、編集または削除したりすることができます。

   ![](../assets/rule_created.png)

>[!CAUTION]
>
>イベントベースのオファーは、で [!DNL Journey Optimizer] は現在サポートされていません。 イベント ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#events) {target = &quot;_blank&quot;} に [ 基づいて意思決定ルールを作成すると、申し出に活用できなくなります。

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329373?quality=12)

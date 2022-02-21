---
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: 3c8c059e5e3953807b9fc2d8d0eded0d00e49003
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 100%

---

# Adobe Experience Platform セグメントの概要 {#about-segments}

[!DNL Journey Optimizer] では、**[!UICONTROL セグメント]**&#x200B;メニューから直接、リアルタイム顧客プロファイルデータを使用して Adobe Experience Platform セグメントを作成して、ジャーニーに活用することができます。

セグメントはセグメント化サービス自体からも作成できます。詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を参照してください。

ジャーニーでセグメントを活用するには、次のように様々な方法があります。

* 「**セグメントを読み取り**」オーケストレーションアクティビティを使用して、指定したセグメントに属するすべての個人をジャーニーにエントリさせる。ジャーニーに含まれるメッセージは、そのセグメントに属する複数の個人に送信されます。「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、すべてのシルバー顧客をジャーニーにエントリさせ、一連のパーソナライズされたメッセージをそれらの顧客に送信できます。

   「**[!UICONTROL セグメントを読み取り]**」アクティビティの使用方法について詳しくは、[この節](../building-journeys/read-segment.md#configuring-segment-trigger-activity)を参照してください。

* 「**セグメントの選定**」イベントアクティビティを使用して、Adobe Experience Platform セグメントのエントリと離脱に基づいて、個人をジャーニーにエントリさせたり進行させたりする。例えば、新規のシルバー顧客全員をジャーニーにエントリさせ、それらの顧客にメッセージを送信することができます。このアクティビティの使用方法について詳しくは、[この節](../building-journeys/segment-qualification-events.md)を参照してください。

* シンプルな式エディターまたは高度な式エディターを使用して、ジャーニーに&#x200B;**複雑な条件**&#x200B;を組み込むことができます。詳しくは、[この節](../building-journeys/condition-activity.md#using-a-segment)を参照してください。

## Adobe Journey Optimizer での評価方法 {#evaluation-method-in-journey-optimizer}

Adobe Journey Optimizer では、オーディエンスは、次の評価方法のいずれかを使用してセグメント定義から生成されます。

* ストリーミングセグメンテーション - セグメントのオーディエンスリストは、新しいデータがシステムに流入するのに応じて、リアルタイムで最新の状態に保たれます。
* バッチセグメンテーション - セグメントのオーディエンスリストは、過去 1 時間に到着したデータに基づいて、1 時間ごとに更新されます。

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメントルールの評価の複雑さとコストに基づいて、セグメント定義ごとにシステムによって決定されます。

セグメントリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各セグメントの評価方法を確認できます。

まずセグメントを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。

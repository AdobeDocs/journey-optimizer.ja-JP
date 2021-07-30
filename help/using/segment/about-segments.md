---
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: ジャーニー
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 100%

---

# セグメントの基本を学ぶ {#about-segments}

[!DNL Journey Optimizer] では、**[!UICONTROL セグメント]**&#x200B;メニューから直接、リアルタイム顧客プロファイルデータを使用して Adobe Experience Platform セグメントを作成して、ジャーニーに活用することができます。

なお、セグメントはセグメント化サービス自体からも作成できます。詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

ジャーニーでセグメントを活用するには、次のように様々な方法があります。

* 「**セグメントを読み取り**」オーケストレーションアクティビティを使用して、指定したセグメントに属するすべての個人をジャーニーにエントリさせる。ジャーニーに含まれるメッセージは、そのセグメントに属する複数の個人に送信されます。「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、すべてのシルバー顧客をジャーニーにエントリさせ、一連のパーソナライズされたメッセージをそれらの顧客に送信できます。

   「**[!UICONTROL セグメントを読み取り]**」アクティビティの使用方法について詳しくは、[この節](../building-journeys/read-segment.md#configuring-segment-trigger-activity)を参照してください。

* 「**セグメントの選定**」イベントアクティビティを使用して、Adobe Experience Platform セグメントのエントリと離脱に基づいて、個人をジャーニーにエントリさせたり進行させたりする。例えば、新規のシルバー顧客全員をジャーニーにエントリさせ、それらの顧客にメッセージを送信することができます。このアクティビティの使用方法について詳しくは、[この節](../building-journeys/segment-qualification-events.md)を参照してください。

* シンプルな式エディターまたは高度な式エディターを使用して、ジャーニーに&#x200B;**複雑な条件**&#x200B;を組み込むことができます。詳しくは、[この節](../building-journeys/condition-activity.md#using-a-segment)を参照してください。

## Adobe Journey Optimizer での評価方法 {#evaluation-method-in-journey-optimizer}

Adobe Journey Optimizer では、オーディエンスは、次の評価方法のいずれかを使用してセグメント定義から生成されます。

* ストリーミングセグメント化 - 新規データがシステムに流入する間、セグメントのオーディエンスリストはリアルタイムで最新の状態に保たれます。
* バッチセグメント化 - セグメントのオーディエンスリストは、過去 1 時間に到達したデータに基づいて 1 時間ごとに更新されます。

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメントルールの評価の複雑さとコストに基づいて、セグメント定義ごとにシステムによって決定されます。

セグメントリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各セグメントの評価方法を確認できます。

まずセグメントを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。

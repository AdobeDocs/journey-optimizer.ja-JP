---
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: ジャーニー
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 100%

---

# Adobe Experience Platform セグメントについて {#about-segments}

[!DNL Journey Optimizer] では、**[!UICONTROL セグメント]**&#x200B;メニューから直接、リアルタイム顧客プロファイルデータを使用して Adobe Experience Platform セグメントを作成して、ジャーニーに活用することができます。

セグメントはセグメント化サービス自体からも作成できます。詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を参照してください。

ジャーニーでセグメントを活用するには、次のように様々な方法があります。

* 「**セグメントを読み取り**」オーケストレーションアクティビティを使用して、指定したセグメントに属するすべての個人をジャーニーにエントリさせる。ジャーニーに含まれるメッセージは、そのセグメントに属する複数の個人に送信されます。「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、すべてのシルバー顧客をジャーニーにエントリさせ、一連のパーソナライズされたメッセージをそれらの顧客に送信できます。

   「**[!UICONTROL セグメントを読み取り]**」アクティビティの使用方法について詳しくは、[この節](../building-journeys/read-segment.md#configuring-segment-trigger-activity)を参照してください。

* 「**セグメントの選定**」イベントアクティビティを使用して、Adobe Experience Platform セグメントのエントリと離脱に基づいて、個人をジャーニーにエントリさせたり進行させたりする。例えば、新規のシルバー顧客全員をジャーニーにエントリさせ、それらの顧客にメッセージを送信することができます。このアクティビティの使用方法について詳しくは、[この節](../building-journeys/segment-qualification-events.md)を参照してください。

* シンプルな式エディターまたは高度な式エディターを使用して、ジャーニーに&#x200B;**複雑な条件**&#x200B;を組み込むことができます。詳しくは、[この節](../building-journeys/condition-activity.md#using-a-segment)を参照してください。

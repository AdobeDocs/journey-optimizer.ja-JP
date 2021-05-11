---
title: Adobe Experience Platformセグメントについて
description: Adobe Experience Platformセグメントの設定方法
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 4%

---

# Adobe Experience Platformセグメントについて{#about-segments}

![](../assets/do-not-localize/badge.png)

Journey Optimizerでは、**[!UICONTROL セグメント]**&#x200B;メニューから直接、リアルタイム顧客プロファイルデータを使用してAdobe Experience Platformセグメントを作成でき、ジャーニーに活用できます。

セグメントはSegmentationサービス自体からも作成できます。 詳しくは、[Adobe Experience Platformセグメントサービスドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を参照してください。

様々な方法で、ジャーニーー内のセグメントを活用できます。

* **セグメント**&#x200B;の読み取りオーケストレーションアクティビティを使用して、指定したセグメントに属するすべての個人をジャーニーに入れます。 ジャーニーに含まれるメッセージは、そのセグメントに属する個人に送信されます。 「シルバー顧客」セグメントがあるとします。 このアクティビティを使用すると、すべての銀の顧客にジャーニーを送信し、パーソナライズされた一連のメッセージを送信できます。

   **[!UICONTROL セグメント]**&#x200B;を読むアクティビティの使い方について詳しくは、[このセクション](../building-journeys/read-segment.md#configuring-segment-trigger-activity)を参照してください。

* **セグメント資格**&#x200B;イベントアクティビティを使用して、Adobe Experience Platformのセグメントの入口と出口に基づいて、個人がジャーニーに入るか進むようにします。 例えば、新規のシルバー顧客全員にジャーニーを入力させ、メッセージを送信させることができます。 このアクティビティの使い方の詳細は、[](../building-journeys/segment-qualification-events.md)を参照してください。

* ジャーニーーで&#x200B;**複雑な条件**&#x200B;を作成するには、単純なエディターまたは高度な式エディターを使用します。 詳しくは、[この節](../building-journeys/condition-activity.md#using-a-segment)を参照してください。

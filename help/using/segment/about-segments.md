---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: 6c255d66fb89ba756add062d8a4315dd622fd8e7
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 100%

---

# Adobe Experience Platform セグメントの概要 {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="セグメント"
>abstract="Adobe Experience Platform では、リアルタイム顧客プロファイルデータを活用することで、お客様の独自の行動や好みを取り込むターゲットセグメントを簡単に作成できます。"

[!DNL Journey Optimizer] では、**[!UICONTROL セグメント]**&#x200B;メニューから直接、リアルタイム顧客プロファイルデータを使用して Adobe Experience Platform セグメントを作成して、ジャーニーやキャンペーンに活用することができます。

さらに、セグメントはセグメント化サービス自体からも作成できます。詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を参照してください。

## [!DNL Journey Optimizer] でセグメントを使用します。 {#segments-in-journey-optimizer}

**[!DNL Journey Optimizer]** でセグメントを活用するには、次のように様々な方法があります。

* セグメントを&#x200B;**キャンペーンのオーディエンス**&#x200B;として選択：選択したセグメントに属するすべての個人にメッセージが送信されます。 [キャンペーンのオーディエンスを定義する方法を学ぶ](../campaigns/create-campaign.md#define-the-audience-audience).

* ジャーニーの&#x200B;**セグメントの読み取り**&#x200B;オーケストレーションアクティビティを使用すると、セグメント内のすべての個人をジャーニーにエントリさせることができ、ジャーニーに含まれるメッセージを受け取ることができます。

  「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、すべてのシルバー顧客をジャーニーにエントリさせ、一連のパーソナライズされたメッセージをそれらの顧客に送信できます。[セグメントの読み取りアクティビティの設定方法を学びます](../building-journeys/read-segment.md#configuring-segment-trigger-activity)。

* ジャーニーの「**セグメントの選定**」イベントアクティビティを使用し、Adobe Experience Platform セグメントのエントリと離脱に基づいて、個人をジャーニーにエントリさせたり進行させたりします。

  例えば、新規のシルバー顧客全員をジャーニーにエントリさせ、それらの顧客にメッセージを送信することができます。このアクティビティの使用方法について詳しくは、[セグメントの選定アクティビティの設定方法を学ぶ](../building-journeys/segment-qualification-events.md)を参照してください。

* ジャーニーでの&#x200B;**条件** アクティビティを使用し、セグメントメンバーシップに基づいて条件を作成します。 [条件でのセグメントの使用方法を学びます](../building-journeys/condition-activity.md#using-a-segment)。

## オーディエンスの評価方法{#evaluation-method-in-journey-optimizer}

Adobe Journey Optimizer では、オーディエンスは、次の2 つの評価方法のいずれかを使用してセグメント定義から生成されます。

* **ストリーミングセグメント化**：新規データがシステムに流入するのに応じて、セグメントのオーディエンスリストはリアルタイムで最新の状態に保たれます。

  ストリーミングセグメント化は、ユーザーのアクティビティに応じてセグメントを更新する継続的なデータ選択プロセスです。セグメントを作成して保存すると、Journey Optimizer で受け取るデータに対してセグメント定義が 適用されます。つまり、個人は、プロファイルデータの変更に応じてセグメントに追加または削除され、ターゲットオーディエンスが常に関連性の高いものとなります。

* **バッチセグメント化**：セグメントのオーディエンスリストは 24 時間ごとに評価されます。

  バッチセグメント化は、ストリーミングセグメント化の代わりに使用でき、セグメント定義を通じてすべてのプロファイルデータを一度に処理します。 これにより、オーディエンスのスナップショットが作成され、保存して使用するために書き出すことができます。 ただし、ストリーミングセグメント化とは異なり、バッチセグメント化ではオーディエンスリストがリアルタイムで継続的に更新されず、バッチ処理後に取り込まれる新しいデータは次のバッチ処理までセグメントに反映されません。」

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメントルールの評価の複雑さとコストに基づいて、セグメント定義ごとにシステムによって決定されます。セグメントリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各セグメントの評価方法を確認できます。

![](assets/evaluation-method.png)

>[!NOTE]
>
>この **[!UICONTROL 評価方法]** 列が表示されない場合は、リストの右上にある設定ボタンを使用して追加する必要があります。

まずセグメントを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。

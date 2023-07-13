---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform Audiences について
description: Adobe Experience Platform Audiences の使用方法を説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 28%

---

# Adobe Experience Platform Audiences の概要 {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="オーディエンス"
>abstract="Adobe Experience Platformでは、リアルタイム顧客プロファイルデータを活用することで、セグメント定義を簡単に作成して、顧客固有の行動や好みをキャプチャするターゲットを絞り込んだオーディエンスを作成できます。"

[!DNL Journey Optimizer] では、リアルタイム顧客プロファイルデータを使用して、Adobe Experience Platformオーディエンスを **[!UICONTROL オーディエンス]** メニューを開き、それらをジャーニーやキャンペーンで使用します。

詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を参照してください。

## でのオーディエンスの使用 [!DNL Journey Optimizer] {#segments-in-journey-optimizer}

オーディエンスを **[!DNL Journey Optimizer]** 様々な方法で次の手順を実行します。

* のオーディエンスを選択 **campaign**：選択したオーディエンスに属するすべての個人にメッセージが送信されます。 [キャンペーンのオーディエンスを定義する方法を学ぶ](../campaigns/create-campaign.md#define-the-audience-audience).

* の使用 **オーディエンスの閲覧** ジャーニーのオーケストレーションアクティビティを使用して、オーディエンス内のすべての個人をジャーニーにエントリさせ、ジャーニーに含まれるメッセージを受け取ることができます。

  「シルバーカスタマー」オーディエンスがあるとします。 このアクティビティを使用すると、すべてのシルバー顧客をジャーニーにエントリさせ、一連のパーソナライズされたメッセージをそれらの顧客に送信できます。[「オーディエンスの閲覧」アクティビティの設定方法を説明します](../building-journeys/read-audience.md#configuring-segment-trigger-activity).

* 以下を使用： **オーディエンスの選定** イベントアクティビティを使用して、Adobe Experience Platformオーディエンスのエントリと離脱に基づいて、個人がジャーニーにエントリしたりジャーニーに進んだりできるようにします。

  例えば、新規のシルバー顧客全員をジャーニーにエントリさせ、それらの顧客にメッセージを送信することができます。このアクティビティの使用方法について詳しくは、 [オーディエンスの選定アクティビティの設定方法を説明します](../building-journeys/audience-qualification-events.md).

* 以下を使用： **条件** ジャーニーのアクティビティを参照して、オーディエンスのメンバーシップに基づいて条件を作成します。 [条件でのオーディエンスの使用方法を説明します](../building-journeys/condition-activity.md#using-a-segment).

## オーディエンスの評価方法{#evaluation-method-in-journey-optimizer}

Adobe Journey Optimizer では、オーディエンスは、次の2 つの評価方法のいずれかを使用してセグメント定義から生成されます。

* **ストリーミングセグメント化**:オーディエンスのプロファイルリストは、新しいデータがシステムに送られるたびに、リアルタイムで最新の状態に保たれます。

  ストリーミングセグメント化は、継続的なデータ選択プロセスで、ユーザーのアクティビティに応じてオーディエンスを更新します。 セグメント定義を作成し、結果のオーディエンスを保存すると、Journey Optimizerへの受信データに対してセグメント定義が適用されます。 つまり、個人はプロファイルデータの変更に応じてオーディエンスに追加または削除され、ターゲットオーディエンスが常に関連性の高いものになります。

* **バッチセグメント化**:オーディエンスのプロファイルリストは 24 時間ごとに評価されます。

  バッチセグメント化は、ストリーミングセグメント化の代わりに使用でき、セグメント定義を通じてすべてのプロファイルデータを一度に処理します。 これにより、オーディエンスのスナップショットが作成され、保存して使用するために書き出すことができます。 ただし、ストリーミングのセグメント化とは異なり、バッチセグメント化ではオーディエンスリストがリアルタイムで継続的に更新されず、バッチ処理後に取り込まれる新しいデータは次のバッチ処理までオーディエンスに反映されません。」

バッチセグメント化とストリーミングセグメント化の間の決定は、セグメント定義ルールの評価の複雑さとコストに基づいて、オーディエンスごとにシステムがおこないます。 各オーディエンスの評価方法は、 **[!UICONTROL 評価方法]** オーディエンスリストの列。

![](assets/evaluation-method.png)

>[!NOTE]
>
>この **[!UICONTROL 評価方法]** 列が表示されない場合は、リストの右上にある設定ボタンを使用して追加する必要があります。

オーディエンスを初めて定義した後は、プロファイルは、認定時にオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。

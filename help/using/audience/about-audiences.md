---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform オーディエンスについて
description: Adobe Experience Platform オーディエンスの使用方法を説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: 298562247af79b9dd504a957c197856d702d0f6b
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 93%

---

# Adobe Experience Platform オーディエンスの基本を学ぶ {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="オーディエンス"
>abstract="Adobe Experience Platform では、リアルタイム顧客プロファイルデータを活用することで、セグメント定義を簡単に作成して、顧客の固有の行動や好みを取り込むターゲットオーディエンスを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_audience"
>title="キャンペーンオーディエンスを選択"
>abstract="このリストには、使用可能なすべてのAdobe Experience Platformオーディエンスが表示されます。 キャンペーンのターゲットにするオーディエンスを選択します。 キャンペーンで設定したメッセージは、選択したオーディエンスに属するすべての個人に送信されます。 [詳しくは、オーディエンスを参照してください](../audience/about-audiences.md)。"

[!DNL Journey Optimizer] では、**[!UICONTROL オーディエンス]**&#x200B;メニューからリアルタイム顧客プロファイルデータを直接使用して Adobe Experience Platform オーディエンスを作成および活用し、それらをジャーニーやキャンペーンに使用することができます。

詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を参照してください。

## [!DNL Journey Optimizer] でのオーディエンスの使用 {#segments-in-journey-optimizer}

**[!DNL Journey Optimizer]** でオーディエンスを活用するには、次のように様々な方法があります。

* **キャンペーン**&#x200B;のオーディエンスを選択します。選択したオーディエンスに属するすべての個人にメッセージが送信されます。[詳しくは、キャンペーンのオーディエンスを定義する方法を参照してください](../campaigns/create-campaign.md#define-the-audience-audience)。

* ジャーニーの&#x200B;**オーディエンスを読み取り**&#x200B;オーケストレーションアクティビティを使用して、オーディエンス内のすべての個人をジャーニーにエントリさせ、ジャーニーに含まれるメッセージを受け取らせます。

  「シルバー顧客」オーディエンスがあるとします。このアクティビティを使用すると、すべてのシルバー顧客をジャーニーにエントリさせ、パーソナライズされた一連のメッセージをそれらの顧客に送信できます。[詳しくは、「オーディエンスを読み取り」アクティビティの設定方法を参照してください](../building-journeys/read-audience.md#configuring-segment-trigger-activity)。

* ジャーニーの&#x200B;**オーディエンスの選定**&#x200B;イベントアクティビティを使用し、Adobe Experience Platform オーディエンスのエントリと離脱に応じて、個人をジャーニーにエントリさせたりジャーニー内で進行させたりします。

  例えば、新規のシルバー顧客全員をジャーニーにエントリさせ、それらの顧客にメッセージを送信することができます。このアクティビティの使用方法について詳しくは、[「オーディエンスの選定」アクティビティの設定方法](../building-journeys/audience-qualification-events.md)を参照してください。

* ジャーニーの&#x200B;**条件**&#x200B;アクティビティを使用し、オーディエンスメンバーシップに基づいて条件を作成します。[詳しくは、条件でのオーディエンスの使用方法を参照してください](../building-journeys/condition-activity.md#using-a-segment)。

## オーディエンスの評価方法{#evaluation-method-in-journey-optimizer}

Adobe Journey Optimizer では、オーディエンスは、次の2 つの評価方法のいずれかを使用してセグメント定義から生成されます。

* **ストリーミングセグメント化**：新規データがシステムに流入するのに応じて、オーディエンスのプロファイルリストがリアルタイムで最新の状態に保たれます。

  ストリーミングセグメント化は、ユーザーのアクティビティに応じてオーディエンスを更新する継続的なデータ選択プロセスです。セグメント定義を作成して、結果のオーディエンスを保存すると、Journey Optimizer への受信データに対してセグメント定義が適用されます。つまり、個人は、プロファイルデータの変更に応じてオーディエンスに追加またはオーディエンスから削除され、ターゲットオーディエンスが常に関連性の高いものとなります。

* **バッチセグメント化**：オーディエンスのプロファイルリストが 24 時間ごとに評価されます。

  バッチセグメント化は、ストリーミングセグメント化の代わりに使用でき、セグメント定義を通じてすべてのプロファイルデータを一度に処理します。 これにより、オーディエンスのスナップショットが作成され、保存して使用するために書き出すことができます。 ただし、ストリーミングセグメント化とは異なり、バッチセグメント化ではオーディエンスリストがリアルタイムで継続的に更新されることはなく、バッチ処理後に取り込まれる新しいデータは次のバッチ処理までオーディエンスに反映されません。

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメント定義ルールの評価の複雑さとコストに基づいて、オーディエンスごとにシステムによって決定されます。オーディエンスリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各オーディエンスの評価方法を確認できます。

![](assets/evaluation-method.png)

>[!NOTE]
>
>この **[!UICONTROL 評価方法]**&#x200B;列が表示されない場合は、リストの右上にある設定ボタンを使用して追加する必要があります。

まずオーディエンスを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。

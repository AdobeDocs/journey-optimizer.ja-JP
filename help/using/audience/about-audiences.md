---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform オーディエンスについて
description: Adobe Experience Platform オーディエンスの使用方法を説明します
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: 51c6717d5d5d317c4ff1040194f2e831bea89222
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 99%

---

# Adobe Experience Platform オーディエンスの基本を学ぶ {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="オーディエンス"
>abstract="Adobe Experience Platform では、リアルタイム顧客プロファイルデータを活用することで、セグメント定義を簡単に作成して、顧客の固有の行動や好みを取り込むターゲットオーディエンスを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_audience"
>title="キャンペーンオーディエンスを選択"
>abstract="このリストには、使用可能なすべての Adobe Experience Platformオーディエンスが表示されます。キャンペーンのターゲットにするオーディエンスを選択します。キャンペーンで設定したメッセージは、選択したオーディエンスに属するすべての個人に送信されます。[詳しくは、オーディエンスを参照してください](../audience/about-audiences.md)。"

[!DNL Journey Optimizer] では、**[!UICONTROL オーディエンス]**&#x200B;メニューからリアルタイム顧客プロファイルデータを直接使用して Adobe Experience Platform オーディエンスを作成および活用し、それらをジャーニーやキャンペーンに使用することができます。詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja){target="_blank"}を参照してください。

## [!DNL Journey Optimizer] でのオーディエンスの使用 {#segments-in-journey-optimizer}

キャンペーンとジャーニーでは、[セグメント定義](../audience/creating-a-segment-definition.md)を使用して生成された Adobe Experience Platform オーディエンスを選択できます。

>[!NOTE]
>
>また、[オーディエンスの構成](../audience/get-started-audience-orchestration.md)または [CSV ファイルからアップロード済み](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja#import-audience){target="_blank"}を使用して作成された Adobe Experience Platform オーディエンスをターゲットにすることもできます。これらの機能は現在、Private Beta として使用可能です。

**[!DNL Journey Optimizer]** でオーディエンスを活用するには、次のように様々な方法があります。

* **キャンペーン**&#x200B;のオーディエンスを選択します。選択したオーディエンスに属するすべての個人にメッセージが送信されます。[詳しくは、キャンペーンのオーディエンスを定義する方法を参照してください](../campaigns/create-campaign.md#define-the-audience-audience)。

* ジャーニーの&#x200B;**オーディエンスを読み取り**&#x200B;オーケストレーションアクティビティを使用して、オーディエンス内のすべての個人をジャーニーにエントリさせ、ジャーニーに含まれるメッセージを受け取らせます。

  「シルバー顧客」オーディエンスがあるとします。このアクティビティを使用すると、すべてのシルバー顧客をジャーニーにエントリさせ、パーソナライズされた一連のメッセージをそれらの顧客に送信できます。[詳しくは、「オーディエンスを読み取り」アクティビティの設定方法を参照してください](../building-journeys/read-audience.md#configuring-segment-trigger-activity)。

* ジャーニーの&#x200B;**オーディエンスの選定**&#x200B;イベントアクティビティを使用し、Adobe Experience Platform オーディエンスのエントリと離脱に応じて、個人をジャーニーにエントリさせたりジャーニー内で進行させたりします。

  例えば、新規のシルバー顧客全員をジャーニーにエントリさせ、それらの顧客にメッセージを送信することができます。このアクティビティの使用方法について詳しくは、[「オーディエンスの選定」アクティビティの設定方法](../building-journeys/audience-qualification-events.md)を参照してください。

* ジャーニーの&#x200B;**条件**&#x200B;アクティビティを使用し、オーディエンスメンバーシップに基づいて条件を作成します。[詳しくは、条件でのオーディエンスの使用方法を参照してください](../building-journeys/condition-activity.md#using-a-segment)。

## オーディエンスの評価方法 {#evaluation-method-in-journey-optimizer}

Adobe Journey Optimizer では、オーディエンスは、次の 3 つの評価方法のいずれかを使用してセグメント定義から生成されます。

+++ ストリーミングセグメント化

新規データがシステムに流入するのに応じて、オーディエンスのプロファイルリストがリアルタイムで最新の状態に保たれます。

ストリーミングセグメント化は、ユーザーのアクティビティに応じてオーディエンスを更新する継続的なデータ選択プロセスです。セグメント定義を作成して、結果のオーディエンスを保存すると、Journey Optimizer への受信データに対してセグメント定義が適用されます。つまり、個人は、プロファイルデータの変更に応じてオーディエンスに追加またはオーディエンスから削除され、ターゲットオーディエンスが常に関連性の高いものとなります。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/streaming-segmentation.html){target="_blank"}

>[!NOTE]
>
>ストリーミングセグメント化条件として適切なイベントを使用するようにしてください。[詳細情報](#streaming-segmentation-events-guardrails)

+++

+++ バッチセグメント化

オーディエンスのプロファイルリストが 24 時間ごとに評価されます。

バッチセグメント化は、ストリーミングセグメント化の代わりに使用でき、セグメント定義を通じてすべてのプロファイルデータを一度に処理します。 これにより、オーディエンスのスナップショットが作成され、保存して使用するために書き出すことができます。 ただし、ストリーミングセグメント化とは異なり、バッチセグメント化ではオーディエンスリストがリアルタイムで継続的に更新されることはなく、バッチ処理後に取り込まれる新しいデータは次のバッチ処理までオーディエンスに反映されません。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja#batch){target="_blank"}

+++

+++ エッジセグメント化

エッジセグメント化は、Adobe Experience Platform のセグメントを[エッジで](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"}, enabling same-page and next-page personalization use cases. Currently only select query types can be evaluated with edge segmentation. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/edge-segmentation.html?lang=ja#query-types){target="_blank"}瞬時に評価する機能です。

+++

使用する評価方法を理解している場合は、ドロップダウンリストを使用して選択します。また、虫眼鏡の付いた参照アイコンフォルダーアイコンをクリックして、使用可能なセグメント定義の評価方法のリストを表示することもできます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=ja#segment-properties){target="_blank"}

![](assets/evaluation-methods.png)

<!--The determination between batch segmentation and streaming segmentation is made by the system for each audience, based on the complexity and the cost of evaluating the segment definition rule. You can view the evaluation method for each audience in the **[!UICONTROL Evaluation method]** column of the audience list.
    
![](assets/evaluation-method.png)

>[!NOTE]
>
>If the **[!UICONTROL Evaluation method]** column does not display, you  need to add it using configuration button on the top right of the list.-->

まずオーディエンスを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。

### ストリーミングセグメント化によるイベントの使用 {#streaming-segmentation-events-guardrails}

ストリーミングセグメント化は、価値の高いユースケースでのリアルタイムのパーソナライゼーションに役立ちます。ただし、セグメント化条件として使用する適切な[イベント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=ja#events){target="_blank"}を選択することが重要です。

したがって、ストリーミングセグメント化の最適なパフォーマンスを得るには、次のイベントを使用しないでください。

* **開封済みメッセージ**&#x200B;インタラクションタイプのイベント

  オーディエンスを作成する際、**開封済みメッセージ**&#x200B;インタラクションイベントの使用は信頼性が低くなりました。これは、ユーザーアクティビティの実際の指標ではなく、セグメント化のパフォーマンスに悪影響を与える可能性があるためです。理由については、この[アドビのブログ投稿](https://blog.adobe.com/en/publish/2021/06/24/what-apples-mail-privacy-protection-means-for-email-marketers){target="_blank"}を参照してください。

  したがって、アドビでは、ストリーミングセグメント化で&#x200B;**開封済みメッセージ**&#x200B;インタラクションイベントを使用しないことをお勧めします。代わりに、クリック数、購入数、ビーコンデータなどの実際のユーザーアクティビティのシグナルを使用します。

* **送信済みメッセージ**&#x200B;フィードバックステータスのイベント

  **送信済みメッセージ**&#x200B;フィードバックイベントは、多くの場合、メール送信前の頻度や抑制の確認に使用されます。アドビでは、パフォーマンスを低下させ、システムの劣化を引き起こす可能性があるので、このイベントを使用しないことをお勧めします。

  したがって、頻度または抑制ロジックには、**送信済みメッセージ**&#x200B;フィードバックイベントではなくビジネスルールを使用します。個々のプロファイルの日別頻度制限が近日中に使用可能になり、ビジネスルールの既存の月別頻度を補完します。

>[!NOTE]
>
>**開封済みメッセージ**&#x200B;および&#x200B;**送信済みメッセージ**&#x200B;イベントは、パフォーマンスを問題とすることなくバッチセグメント化で使用できます。

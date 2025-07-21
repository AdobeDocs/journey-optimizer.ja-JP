---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの基本を学ぶ
description: Journey Optimizer でのキャンペーンについて学ぶ
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: キャンペーン, 方法, 開始, Optimizer
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 68%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="キャンペーンスケジュール"
>abstract="デフォルトでは、キャンペーンは手動でアクティブ化すると開始され、メッセージが 1 回送信されるとすぐに終了します。メッセージを送信する特定の日付を柔軟に設定できます。さらに、繰り返しアクションキャンペーンの終了日を指定できます。 アクショントリガーでは、環境設定に応じてメッセージ送信頻度を設定することもできます。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_start"
>title="キャンペーン開始"
>abstract="メッセージを送信する日時を指定します。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_end"
>title="キャンペーン終了"
>abstract="繰り返しキャンペーンの実行を停止するタイミングを指定します。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_triggers"
>title="キャンペーンのアクショントリガー"
>abstract="キャンペーンのメッセージを送信する頻度を定義します。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_throttling"
>title="スロットルレートコントロール"
>abstract="スロットルレートコントロール"

>[!CONTEXTUALHELP]
>id="ajo_homepage_card3"
>title="キャンペーンの作成"
>abstract="**Adobe Journey Optimizer** を使用すると、様々なチャネルを使用して、特定のオーディエンスに 1 回限りのコンテンツを配信できます。ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。"

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="キャンペーンを作成して、様々なチャネルで特定のオーディエンスに 1 回限りのコンテンツを配信します。キャンペーンを作成する前に、チャネル設定と Adobe Experience Platform オーディエンスが使用できる状態になっていることを確認します。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="キャンペーンのタイプ"
>abstract="**スケジュール済みキャンペーン**&#x200B;は、即時または指定した日付に実行され、マーケティングタイプのメッセージを送信することを目的としています。**API トリガー**&#x200B;のキャンペーンは、API 呼び出しを使用して実行されます。これらは、マーケティングメッセージ（ユーザーの同意が必要なプロモーションメッセージ）またはトランザクションメッセージ（特定のコンテキストで登録解除済みのプロファイルにも送信できる非商用メッセージ）を送信することを目的としています。"

Journey Optimizer キャンペーンを使用すると、様々なチャネルを使用して、特定のオーディエンスに 1 回限りのコンテンツを配信できます。ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。

![](assets/gs-campaigns.png)

Journey Optimizerでは、様々なタイプのキャンペーンを作成できます。

* **アクションキャンペーン**

  アクションキャンペーン（またはスケジュール済みキャンペーン）を使用すると、プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングのユースケースに対するシンプルなアドホックバッチ通信が可能になります。

* **API トリガーキャンペーン**

  API トリガーキャンペーンを使用すると、マーケティングコミュニケーションが適切なタイミングでオーディエンスに到達したり、トランザクションメッセージ/操作メッセージがパスワードリセットなどの個人に到達したりできます。この場合、プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータを使用したパーソナライゼーションが必要になる可能性があります。

<!--* **Orchestrated campaigns**

    Campaign Orchestration in Adobe Journey Optimizer powers sophisticated, brand-initiated marketing campaigns across channels, helping you drive engagement, revenue, and customer loyalty at scale.

    While cross-channel marketing is essential, orchestrated campaigns make it seamless. With a visual, drag-and-drop interface, you can design and automate complex marketing workflows, from segmentation to message delivery, across multiple channels. Everything happens in one intuitive environment, built for speed, control, and efficiency.-->

## 開始する前に {#campaign-prerequisites}

[!DNL Journey Optimizer] で最初のキャンペーンの作成を開始する前に、次の前提条件を確認してください。

1. **適切な権限が必要です**。キャンペーンは、Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign ビューアなど、キャンペーンに関連する **[!UICONTROL 製品プロファイル]** へのアクセス権を持つユーザーのみが使用できます。 キャンペーンにアクセスできない場合は、権限を拡張する必要があります。

   +++キャンペーン関連の役割の割り当て方法を説明します

   1. [!DNL Permissions] 製品でユーザーに役割を割り当てるには、「**[!UICONTROL 役割]**」タブに移動し、ビルトインのキャンペーン関連の&#x200B;**[!UICONTROL 役割]**&#x200B;である Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign 閲覧者のいずれかを選択します。

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

      まだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/users)を参照してください。

   これにより、ユーザーをインスタンスへリダイレクトするメールがユーザーに送られます。

+++

1. **オーディエンスが必要です**。キャンペーンを作成するには、まずオーディエンスを使用可能にする必要があります。[ オーディエンスの基本を学ぶ ](../audience/about-audiences.md)。

1. **チャネル設定が必要です**。チャンネルを選択できるようにするには、対応するチャネル設定（例：プリセット）を作成し、使用可能にする必要があります。[ チャネル設定の設定方法を学ぶ ](../configuration/channel-surfaces.md)。

## さらに深く掘り下げましょう

これで [!DNL Journey Optimizer] のキャンペーンを理解できたので、ドキュメントの節で詳しく説明し、最初のキャンペーンの作成を開始します。

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img alt="アクションキャンペーン" src="assets/do-not-localize/gs-action-campaign.png" width="50%"></a><br/><a href="create-campaign.md">アクションキャンペーン</a></td>
<td><a href="api-triggered-campaigns.md"><img alt="SMS" src="assets/do-not-localize/gs-api-triggered-campaign.png" width="50%"></a><br/><a href="api-triggered-campaigns.md">API トリガーキャンペーン</a></td>
</tr></table>

<!--
<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img alt="action campaigns" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">Action campaigns</a></td>
<td><a href="api-triggered-campaigns.md"><img alt="sms" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API triggered campaigns</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img alt="push" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">Orchestrated campaigns</a></td>
</tr></table>-->

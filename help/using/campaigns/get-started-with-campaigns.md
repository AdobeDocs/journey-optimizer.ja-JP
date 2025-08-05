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
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 74%

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

Journey Optimizer では、様々なタイプのキャンペーンを作成できます。

* **アクションキャンペーン**

  アクションキャンペーン（またはスケジュール済みキャンペーン）を使用すると、プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングのユースケースに対するシンプルなアドホックバッチ通信が可能になります。

* **API トリガーキャンペーン**

  API トリガーキャンペーンを使用すると、適切なタイミングでオーディエンスにリーチするマーケティング通信や、パスワードのリセットなどの個人に対するトランザクション／運用メッセージが可能になります。これらの場合、プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータも使用したパーソナライゼーションが必要になる可能性があります。

* **調整されたキャンペーン**

  Adobe Journey Optimizerの Campaign Orchestration は、あらゆるチャネルにわたる高度なブランド主導のマーケティングキャンペーンを強化し、エンゲージメント、売上高、顧客ロイヤルティを大規模に推進するのに役立ちます。

  クロスチャネルマーケティングは不可欠ですが、オーケストレートキャンペーンはシームレスに行います。 視覚的なドラッグ&amp;ドロップインターフェイスを使用すると、複数のチャネルをまたいで、セグメント化からメッセージ配信に至る複雑なマーケティングワークフローをデザインして自動化できます。 すべてが、速度、制御、効率のために構築された、1 つの直感的な環境で行われます。

## 前提条件 {#prerequisites}

キャンペーンを作成する前に、以下の前提条件を確認してください。

### 権限

キャンペーンは、以下に示す適切な権限を持つユーザーのみが使用できます。 [Journey Optimizerの組み込みの役割の詳細情報 ](../administration/ootb-product-profiles.md)

>[!BEGINTABS]

>[!TAB アクションキャンペーン]

Campaign 管理者
Campaign 承認者
キャンペーンマネージャー
Campaign ビューア

>[!TAB API トリガーキャンペーン]

Campaign 管理者
Campaign 承認者
キャンペーンマネージャー
Campaign ビューア

>[!TAB  調整されたキャンペーン ]

調整された Campaign 管理者
調整された Campaign 承認者
調整されたキャンペーンマネージャー
調整された Campaign ビューア

>[!ENDTABS]

Campaign の機能にアクセスできない場合は、管理者に連絡して必要な権限をリクエストしてください。

+++キャンペーン関連の役割の割り当て方法を説明します

1. [!DNL Permissions] 製品でユーザーに役割を割り当てるには、「**[!UICONTROL 役割]**」タブに移動し、上記の組み込みのキャンペーン関連 **[!UICONTROL 役割]** のいずれかを選択します。

1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

   まだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/users)を参照してください。

これにより、ユーザーをインスタンスへリダイレクトするメールがユーザーに送られます。

+++

### オーディエンス

キャンペーンを作成するには、まずオーディエンスを使用可能にする必要があります。[オーディエンスの基本を学ぶ](../audience/about-audiences.md)。

### チャネル設定

チャンネルを選択できるようにするには、対応するチャネル設定（例：プリセット）を作成し、使用可能にする必要があります。[詳しくは、チャネル設定の指定方法を参照してください](../configuration/channel-surfaces.md)。

## さらに深く掘り下げましょう

これで、[!DNL Journey Optimizer] のキャンペーンについて理解できたので、これらのドキュメントの節をより深く掘り下げて、最初のキャンペーンの作成を開始します。

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img width="70%" alt="アクションキャンペーン" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">アクションキャンペーン</a></td>
<td><a href="api-triggered-campaigns.md"><img width="70%" alt="SMS" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API トリガーキャンペーン</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img width="70%" alt="プッシュ" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">調整されたキャンペーン</a></td>
</tr></table>

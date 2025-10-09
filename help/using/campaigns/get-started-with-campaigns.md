---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの基本を学ぶ
description: Journey Optimizer でのキャンペーンについて学ぶ
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: キャンペーン, 方法, 開始, Optimizer
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 801b90201c3ffcbfb7b038abac2bf99209a14c7a
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 61%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="キャンペーンスケジュール"
>abstract="デフォルトでは、キャンペーンは手動でアクティブ化すると開始され、メッセージが 1 回送信されるとすぐに終了します。メッセージを送信する特定の日付を柔軟に設定できます。さらに、繰り返しのアクションキャンペーンの終了日を指定できます。アクショントリガーでは、環境設定に応じてメッセージ送信頻度を設定することもできます。"

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
>title="レート制御"
>abstract="目的のレート制限を指定して、キャンペーンのレート制御を設定します。この機能は、ランディングページやカスタマーケアプラットフォームなどのダウンストリームシステムの過負荷を防ぐのに特に役立ちます。"

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
>abstract="キャンペーンのタイプを選択します。使用可能なチャネルは、選択したタイプによって異なります。<br>**スケジュールキャンペーン**（アクションキャンペーン）- 特定の時間に実行するようにスケジュールできる、シンプルな 1 回限りのバッチ通信に最適です。<br>**API トリガーキャンペーン** - API 呼び出しを通じてアクティベートされ、外部システムから直接自動化されたイベントベースのメッセージングが可能になります。<br>**オーケストレーションキャンペーン** - 視覚的なドラッグ＆ドロップキャンバスを提供し、オーディエンスのセグメント化からチャネルをまたいでパーソナライズされたメッセージの配信まで、複雑なマルチステップのマーケティングワークフローをデザインおよび自動化します。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_orchestration"
>title="キャンペーン"
>abstract="セグメント化フローを作成し、クロスチャネルメッセージを作成して、キャンペーンを計画します。サポートされているチャネル：メール、SMS、プッシュ通知。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_scheduled_marketing"
>title="キャンペーン"
>abstract="単一または繰り返しのアウトバウンド配信アクションや、進行中のインバウンドアクションを配信します。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_scheduled_transactional"
>title="キャンペーン"
>abstract="単一または繰り返しのアウトバウンドトランザクションアクションを配信します。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_api_marketing"
>title="キャンペーン"
>abstract="ターゲットオーディエンスにパーソナライズされたマーケティングコミュニケーションを配信します。サポートされているチャネル：メール、SMS、プッシュ通知。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_api_transactional"
>title="キャンペーン"
>abstract="個々のプロファイルまたはプロファイルのセットにトランザクションコミュニケーションを配信します。サポートされているチャネル：メール、SMS、プッシュ通知。"

[!DNL Journey Optimizer] キャンペーンを使用すると、複数のチャネルをまたいで特定のオーディエンスに 1 回限りのコンテンツを配信できます。 アクションを段階的に実行するジャーニーとは異なり、キャンペーンは、アクションを即座に、または定義されたスケジュールで、同時に実行します。

![](assets/gs-campaigns.png)

## キャンペーンのタイプ

[!DNL Journey Optimizer] では、3 つのキャンペーンタイプをサポートしています。 各タイプは異なるユースケースに適合し、異なるチャネルをサポートします。

![](assets/campaign-modal.png)

>[!BEGINTABS]

>[!TAB 調整されたキャンペーン]

**調整されたキャンペーン** は、チャネルをまたいで高度でブランド主導のマーケティングキャンペーンを強化し、エンゲージメント、収益、顧客の忠誠度を大規模に推進するのに役立ちます。

クロスチャネルマーケティングは不可欠ですが、調整されたキャンペーンはこれをシームレスにします。視覚的なドラッグ＆ドロップインターフェイスを使用すると、複数のチャネルをまたいで、セグメント化からメッセージ配信まで、複雑なマーケティングワークフローをデザインおよび自動化できます。すべてが、速度、コントロール、効率のために作成された、1 つの直感的な環境で実行されます。

➡️[ オーケストレートキャンペーンの操作方法を説明します ](../orchestrated/gs-orchestrated-campaigns.md)。

>[!TAB  アクションキャンペーン（またはスケジュール済みキャンペーン） ]

**アクションキャンペーン** スケジュール済みキャンペーンとも呼ばれ、シンプルなアドホックバッチ通信を可能にします。

* **スケジュール型 – マーケティング** - プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングのユースケースの場合。 受信者がオプトインされる必要があります。
* **スケジュール型 – トランザクション** - マーケティングキャンペーンとは異なり、トランザクションキャンペーンでは受信者がオプトインする必要はありません。 このカテゴリは、中断、緊急事態、キャンセルに関連する通信に使用します。 サポートされるチャネル：メール、SMS、プッシュ通知。

➡️[ アクションキャンペーンの操作方法を学ぶ ](create-campaign.md)

>[!TAB API トリガーキャンペーン]

**API トリガーキャンペーン** を使用すると、API 呼び出しを使用してキャンペーンの実行をトリガーできます。 これらの通信は、パスワードのリセット プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータも使用して、パーソナライズ機能が必要になる場合に送信できます。

* **API トリガー – マーケティング** - ターゲットオーディエンスに対してパーソナライズされたマーケティングコミュニケーションを送信します。
* **API トリガー – トランザクション** – 個人が実行したアクションに続いて、メッセージを送信します（パスワードのリセットリクエスト、買い物かごの購入など）。

➡️[API トリガーキャンペーンの操作方法を学ぶ ](api-triggered-campaigns.md)


>[!ENDTABS]

## キャンペーンタイプ別にサポートされるチャネル {#channels}

次の表に、様々なキャンペーンタイプをまたいだ各チャネルの可用性を示し、サポート対象を示します。

| チャネル | アクション （マーケティング） | アクション（トランザクション） | API トリガー（マーケティング） | API トリガー（トランザクション） | 調整 |
|----------------------|---------------------|-------------------------|----------------------------|--------------------------------|--------------|
| メール | ✅ | ✅ | ✅ | ✅ | ✅ |
| SMS | ✅ | ✅ | ✅ | ✅ | ✅ |
| プッシュ通知 | ✅ | ✅ | ✅ | ✅ | ✅ |
| アプリ内 | ✅ | — | — | — | — |
| ダイレクトメール | ✅ | — | — | — | — |
| Web | ✅ | — | — | — | — |
| コードベースの費用。 | ✅ | — | — | — | — |
| コンテンツカード | ✅ | — | — | — | — |
| WhatsApp | ✅ | — | — | — | — |
| 折れ線グラフ | ✅ | — | — | — | — |

## 前提条件 {#prerequisites}

キャンペーンを使用する前に、以下の前提条件を確認してください。

* **オーディエンス** キャンペーンを作成するには、オーディエンスを使用可能にする必要があります。 [オーディエンスの基本を学ぶ](../audience/about-audiences.md)。

* **チャネル設定** - チャネルを選択するには、対応するチャネル設定（プリセット）を作成し、使用可能にする必要があります。 [詳しくは、チャネル設定の指定方法を参照してください](../configuration/channel-surfaces.md)。

* **権限** - キャンペーンは、以下に示す適切な権限を持つユーザーのみが使用できます。 Campaign の機能にアクセスできない場合は、管理者に連絡して必要な権限をリクエストしてください。 [Journey Optimizer のビルトインの役割の詳細情報](../administration/ootb-product-profiles.md)

  | キャンペーンのタイプ | 権限 |
  |----------------------------|----------------------------------------------------------------------------|
  | **アクションキャンペーン** | Campaign 管理者 <br>Campaign 承認者 <br>Campaign マネージャー <br>Campaign ビューア |
  | **API トリガーキャンペーン** | Campaign 管理者 <br>Campaign 承認者 <br>Campaign マネージャー <br>Campaign ビューア |
  | **調整されたキャンペーン** | Campaign 管理者が調整 <br> た Campaign 承認者 <br>Campaign マネージャーが調整 <br> た Campaign ビューア |

  +++キャンペーン関連の役割の割り当て方法を説明します

   1. [!DNL Permissions] 製品でユーザーに役割を割り当てるには、「**[!UICONTROL 役割]**」タブに移動し、上で詳しく説明したビルトインのキャンペーン関連の&#x200B;**[!UICONTROL 役割]**&#x200B;のいずれかを選択します。

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

      まだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/users)を参照してください。

  これにより、ユーザーをインスタンスへリダイレクトするメールがユーザーに送られます。

  +++

## さらに深く掘り下げましょう

これで、[!DNL Journey Optimizer] のキャンペーンについて理解できたので、これらのドキュメントの節をより深く掘り下げて、最初のキャンペーンの作成を開始します。

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img width="70%" alt="アクションキャンペーン" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">アクションキャンペーン</a></td>
<td><a href="api-triggered-campaigns.md"><img width="70%" alt="SMS" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API トリガーキャンペーン</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img width="70%" alt="プッシュ" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">調整されたキャンペーン</a></td>
</tr></table>

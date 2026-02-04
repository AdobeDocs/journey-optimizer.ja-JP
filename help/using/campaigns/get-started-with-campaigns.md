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
source-git-commit: a7d2557790054e7c6e28ca3ffa937f454c4b004c
workflow-type: tm+mt
source-wordcount: '1510'
ht-degree: 100%

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
>title="キャンペーンタイプ"
>abstract="キャンペーンのタイプを選択します。使用可能なチャネルは、選択したタイプによって異なります。<br>**スケジュールキャンペーン**（アクションキャンペーン）- 特定の時間に実行するようにスケジュールできる、シンプルな 1 回限りのバッチ通信に最適です。<br>**API トリガーキャンペーン** - API 呼び出しを通じてアクティブ化され、外部システムから直接自動化されたイベントベースのメッセージングが可能になります。<br>**オーケストレーションキャンペーン** - 視覚的なドラッグ＆ドロップキャンバスを提供し、オーディエンスのセグメント化からチャネルをまたいでパーソナライズされたメッセージの配信まで、複雑なマルチステップのマーケティングワークフローをデザインおよび自動化します。"

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

Adobe Journey Optimizer を使用すると、複数のチャネルをまたいで特定のオーディエンスに対してターゲットにする 1 回限りのコンテンツを配信できます。キャンペーンを使用すると、調整されたマーケティングアクションを同時に実行し、適切なメッセージを適切なタイミングでオーディエンスに届けることができます。

このガイドでは、キャンペーンの基本を理解し、ユースケースに適したキャンペーンタイプを選択し、影響力のあるカスタマーエクスペリエンスを提供するキャンペーンを自信を持ってデザインするのに役立つ明確なロードマップについて説明します。

## キャンペーンとは

**キャンペーン**&#x200B;とは、1 つ以上のチャネルをまたいで特定のオーディエンスにコンテンツを配信する、調整されたマーケティングアクションです。アクションが順番に実行されるジャーニーとは異なり、キャンペーンは、アクションを即時に、または定義されたスケジュールに従って同時実行します。

[!DNL Journey Optimizer] キャンペーンを使用すると、次の操作を実行できます。

* ターゲットオーディエンスセグメントに **1 回限りのコンテンツまたは繰り返しコンテンツ**&#x200B;を配信
* メール、プッシュ通知、SMS、アプリ内、web など、**調整されたマルチチャネル通信**&#x200B;を実行
* API 呼び出し経由の&#x200B;**自動応答**&#x200B;のトリガーにより、リアルタイムのイベント駆動型メッセージを実現
* 視覚的なオーケストレーションツールで&#x200B;**複雑なマーケティングワークフロー**&#x200B;をデザイン

![](assets/gs-campaigns.png)

➡️ **作成を開始する準備は整っていますか？** 数分で[最初のキャンペーンを作成できます](create-campaign.md)。

## キャンペーンタイプの選択 {#campaign-types}

**作成を開始する前に**、ユースケースに適したキャンペーンのタイプを理解することが重要です。Adobe Journey Optimizer では、それぞれ異なるシナリオとアクティブ化メカニズム向けにデザインされた、次の 3 つのキャンペーンタイプをサポートしています。

![](assets/campaign-modal.png)

>[!BEGINTABS]

>[!TAB オーケストレーションキャンペーン]

**用途：**&#x200B;複雑なマルチステップのマーケティングワークフロー

**オーケストレーションキャンペーン**&#x200B;は、視覚的なドラッグ＆ドロップキャンバスを提供し、高度なマーケティングワークフローをデザインおよび自動化します。オーディエンスのセグメント化から、チャネルをまたいだパーソナライズされたメッセージ配信まで、すべてが速度とコントロールを目的に作成された、1 つの直感的な環境で実行されます。

**最適な用途：**&#x200B;マルチステップの顧客エンゲージメントプログラム、複雑なセグメント化とターゲティング戦略、クロスチャネルキャンペーンオーケストレーション、大規模なブランド主導型マーケティング、複数の決定ポイントがある高度なワークフローオートメーション。

➡️ [オーケストレーションキャンペーンの詳細情報](../orchestrated/gs-orchestrated-campaigns.md)

>[!TAB アクションキャンペーン（スケジュール済み）]

**用途：**&#x200B;シンプルなスケジュール済みバッチ通信

**アクションキャンペーン**（スケジュール済みキャンペーンとも呼ばれる）は、特定の時間に実行される、わかりやすい 1 回限りのバッチ通信または繰り返しバッチ通信に最適です。

**2 つのカテゴリ：**

* **マーケティング** - プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意、またはポリシーの更新。受信者はオプトインしている必要があります。
* **トランザクション** - 中断、緊急事態、キャンセル。オプトインは必要ありません。

**最適な用途：**&#x200B;顧客セグメントへの毎月のニュースレター、時間的制約のあるプロモーションのお知らせ、季節のマーケティングキャンペーン、製品ローンチのお知らせ、サービス中断の通知。

➡️ [アクションキャンペーンの詳細情報](create-campaign.md)

>[!TAB API トリガーキャンペーン]

**用途：**&#x200B;外部システムとのリアルタイムなイベント駆動型メッセージ

**API トリガーキャンペーン**&#x200B;は、API 呼び出しを通じてアクティブ化され、外部システムから直接自動化されたメッセージングが可能になります。これらのキャンペーンは、API ペイロードからのプロファイル属性とリアルタイムコンテキストデータの両方を使用したパーソナライゼーションをサポートしています。

**2 つのカテゴリ：**

* **マーケティング** - ターゲットオーディエンスへのパーソナライズされたマーケティング通信
* **トランザクション** - 個々のアクション（パスワードのリセット、買い物かごの購入など）の後のメッセージ

**最適な用途：**&#x200B;パスワードのリセットの確認、買い物かご放棄対策、注文確認と発送状況の更新、アカウントアクティビティ通知、リアルタイムのパーソナライズされたレコメンデーション。

➡️ [API トリガーキャンペーンの詳細情報](api-triggered-campaigns.md)

>[!ENDTABS]

>[!NOTE]
>
>選択するタイプがわからないですか？スケジュールバッチ通信用の&#x200B;**アクションキャンペーン**&#x200B;またはリアルタイムメッセージ用の **API トリガーキャンペーン**&#x200B;から初めてください。これらは、最も一般的なユースケースを対象としています。

## 前提条件 {#prerequisites}

キャンペーンを使用する前に、以下の準備が整っていることを確認してください。

* **オーディエンス** - キャンペーンを作成する前に、Adobe Experience Platform でオーディエンスを使用可能にする必要があります。[オーディエンスの基本を学ぶ →](../audience/about-audiences.md)

* **チャネル設定** - 使用するチャネルで、チャネル設定（プリセット）を作成し、使用可能にする必要があります。[チャネル設定の指定 →](../configuration/channel-surfaces.md)

* **権限** - キャンペーンタイプに基づく適切な権限が必要です。キャンペーン機能にアクセスできない場合は、管理者にお問い合わせください。[ビルトインの役割の詳細情報 →](../administration/ootb-product-profiles.md)

  +++キャンペーン権限リスト

  | キャンペーンタイプ | 権限 |
  |-------------|---------------|
  | **アクションキャンペーン**&#x200B;および **API トリガーキャンペーン** | キャンペーン管理者<br>キャンペーン承認者<br>キャンペーンマネージャー<br>キャンペーンビューアー |
  | **オーケストレーションキャンペーン** | オーケストレーションキャンペーン管理者<br>オーケストレーションキャンペーン承認者<br>オーケストレーションキャンペーンマネージャー<br>オーケストレーションキャンペーンビューアー |

  +++

  +++キャンペーン権限の割り当て方法

   1. [!DNL Permissions] 製品の「**[!UICONTROL 役割]**」タブに移動し、ビルトインのキャンペーン関連の&#x200B;**[!UICONTROL 役割]**&#x200B;を 1 つ選択します。

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

  まだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/users){target="_blank"}を参照してください。

  これにより、ユーザーをインスタンスへリダイレクトするメールがユーザーに送られます。

  +++

## キャンペーン作成ワークフロー {#workflow}

成功するキャンペーンを作成するには、明確で繰り返し可能なプロセスに従います。ステップバイステップのワークフローを次に示します。

+++&#x200B;1. キャンペーンを計画

開始する前に、目的を明確にします。

* **目標は何ですか？**（例：コンバージョンの推進、エンゲージメントの向上、顧客への通知）
* **オーディエンスは誰ですか？**（例：Adobe Experience Platform から作成または選択）
* **適合するキャンペーンタイプはどれですか？**（上記の[キャンペーンタイプ](#campaign-types)を参照）
* **使用するチャネルは何ですか？**（メール、プッシュ、SMS、アプリ内、web など）→ [キャンペーンタイプ別にサポートされるチャネルを参照](../channels/gs-channels.md#channels)
* **いつ実行すればよいですか？**（即時、スケジュール済みまたは API トリガー）

+++

+++&#x200B;2. キャンペーンプロパティを設定

キャンペーンの基盤を設定します。

1. キャンペーンの&#x200B;**名前と説明を入力**&#x200B;して、キャンペーンを識別しやすくします
2. **キャンペーンタイプ**（アクション、API トリガー、オーケストレーション）を選択します
3. **オーディエンスを選択します**
4. 競合管理を使用する場合は、**優先度を設定**&#x200B;します
5. **スケジュール**（アクションキャンペーンの場合）または API の詳細（API トリガーの場合）を設定します

**タイプ固有のガイド：**[アクションキャンペーンプロパティ](campaign-properties.md) | [API トリガーキャンペーンプロパティ](api-triggered-campaign-properties.md) | [オーケストレーションキャンペーン設定](../orchestrated/create-orchestrated-campaign.md)

+++

+++&#x200B;3. コンテンツをデザイン

オーディエンスに魅力的なメッセージを作成します。

* **E メールデザイナー**&#x200B;を使用して、リッチなメールエクスペリエンスを実現
* 画像とディープリンクを使用した&#x200B;**プッシュ通知**&#x200B;を設定
* パーソナライゼーションを使用して **SMS／MMS** メッセージをデザイン
* **アプリ内**&#x200B;および **web** エクスペリエンスを作成
* プロファイル属性とコンテキストデータを使用して&#x200B;**パーソナライゼーション**&#x200B;を追加

**タイプ固有のガイド：**[アクションキャンペーンコンテンツ](campaign-content.md) | [API トリガーキャンペーンコンテンツ](api-triggered-campaign-content.md) | [オーケストレーションキャンペーンコンテンツ](../orchestrated/create-orchestrated-campaign.md)

+++

+++&#x200B;4. レビューとテスト

キャンペーンをアクティブ化する前に、次の点を常にレビューします。

* テストプロファイルを使用して&#x200B;**コンテンツをプレビュー**
* 適切なオーディエンスを確保するために&#x200B;**ターゲティングを確認**
* **スケジュール**&#x200B;とアクティブ化の設定を確認
* 承認ワークフローを使用している場合は、**承認をリクエスト**
* シードリストを使用して&#x200B;**配信品質をテスト**

**タイプ固有のガイド：**[アクションキャンペーンのレビュー](review-activate-campaign.md) | [API トリガーキャンペーンのレビュー](review-activate-api-triggered-campaign.md) | [オーケストレーションキャンペーンのレビュー](../orchestrated/create-orchestrated-campaign.md)

+++

+++&#x200B;5. キャンペーンをアクティブ化

レビューが完了したら、キャンペーンをアクティブ化します。

* **手動アクティブ化** - すぐにアクティブ化するか、スケジュール済みの時間にアクティブ化します
* **API アクティブ化** - API トリガーキャンペーンの場合は、アクティブ化エンドポイントを使用します
* **承認プロセス** - 必要に応じて、関係者の承認を待ちます

メモ：アクティブなキャンペーンは編集できません（変更するには、複製する必要があります）

**タイプ固有のガイド：**[アクションキャンペーンのアクティブ化](review-activate-campaign.md) | [API トリガーキャンペーンのアクティブ化](review-activate-api-triggered-campaign.md) | [オーケストレーションキャンペーンのアクティブ化](../orchestrated/create-orchestrated-campaign.md)

+++

+++&#x200B;6. 監視と分析

キャンペーンが実行する仕組みを追跡します。

* キャンペーンレポートと分析を表示
* 配信率とエンゲージメント指標を監視
* エラーとバウンスを追跡
* コンバージョンと ROI を分析
* インサイトを使用して最適化

**タイプ固有のガイド：**[アクションキャンペーンレポート](../reports/campaign-global-report-cja.md) | [API トリガーキャンペーン監視](api-triggered-campaigns.md#monitor) | [オーケストレーションキャンペーン分析](../orchestrated/create-orchestrated-campaign.md)

+++

## さらに深く掘り下げましょう {#get-started-types}

[!DNL Journey Optimizer] のキャンペーンを理解できたところで、キャンペーンタイプを選択して開始します。

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img width="70%" alt="アクションキャンペーン" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">アクションキャンペーン</a></td>
<td><a href="api-triggered-campaigns.md"><img width="70%" alt="SMS" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API トリガーキャンペーン</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img width="70%" alt="プッシュ" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">オーケストレーションキャンペーン</a></td>
</tr></table>

キャンペーンに慣れたら、次の強力な機能を探索します。

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg?lang=ja)

**スケジュールとタイミング**

特定の日時でキャンペーンをスケジュールし、繰り返し配信を設定し、送信時間を最適化して効果を最大化します（アクションおよび API トリガーキャンペーン）。

[スケジュールの詳細情報](campaign-schedule.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg?lang=ja)

**レート制御**

ランディングページやカスタマーケアプラットフォームなどのダウンストリームシステムの過負荷を防ぐには、メッセージのスループットを制限します。

[レート制御の制限](create-campaign.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg?lang=ja)

**オーディエンスのターゲティング**

特定の Adobe Experience Platform オーディエンスを正確にターゲットにし、オーディエンスの選定を動的に管理します。

[キャンペーンオーディエンスの選択](campaign-audience.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg?lang=ja)

**承認ワークフロー**

キャンペーン公開前にレビューと承認のプロセスを実装し、品質とコンプライアンスを確保します（アクションおよび API トリガーキャンペーン）。

[レビューとアクティブ化](review-activate-campaign.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/clock.svg?lang=ja)

**クワイエットアワー**

指定した時間枠にメッセージを配信しないようにすることで、 顧客の環境設定を適用します（アクションおよび API トリガーキャンペーン）。

[クワイエットアワーの設定](../conflict-prioritization/quiet-hours.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg?lang=ja)

**最適化**

ターゲティングルールとコンテンツ実験を使用して、パーソナライズされたコンテンツを配信し、エンゲージメントを最大化します。

[キャンペーンの最適化](../content-management/gs-message-optimization.md)
:::

::::

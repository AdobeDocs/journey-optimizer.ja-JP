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
source-git-commit: 8ea2a0fe685678d41004d549443a1757eb30c765
workflow-type: tm+mt
source-wordcount: '1549'
ht-degree: 31%

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

Adobe Journey Optimizerを使用すると、複数のチャネルをまたいで、特定のオーディエンスにターゲットを設定した 1 回限りのコンテンツを提供できます。 キャンペーンを使用すると、調整されたマーケティングアクションを同時に実行し、適切なメッセージを適切なタイミングでオーディエンスに届けることができます。

このガイドは、キャンペーンの基本を理解し、ユースケースに適したキャンペーンタイプを選択し、効果的なカスタマーエクスペリエンスを提供するキャンペーンを自信を持って設計するのに役立つ明確なロードマップを提供します。

## キャンペーンとは

**キャンペーン** は、1 つ以上のチャネルをまたいで特定のオーディエンスにコンテンツを配信する調整されたマーケティングアクションです。 アクションが順番に実行されるジャーニーとは異なり、キャンペーンは、アクションを即座に、または定義されたスケジュールで、同時に実行します。

[!DNL Journey Optimizer] を使用すると、次のことができます。

* ターゲットオーディエンスセグメントへの **1 回限りのコンテンツまたは繰り返しコンテンツ** の配信
* メール、プッシュ、SMS、アプリ内、web など **調整されたマルチチャネル通信** を実行
* API 呼び出しを介したトリガー&#x200B;**自動応答** により、リアルタイムのイベント駆動型メッセージを実現
* 視覚的なオーケストレーションツールを使用した **複雑なマーケティングワークフロー** の設計

![](assets/gs-campaigns.png)

➡️ **作成を開始する準備はできていますか？** 最初のキャンペーンを作成 [&#x200B; を数分で &#x200B;](create-campaign.md) 成します。

## キャンペーンタイプを選択 {#campaign-types}

**作成を開始する前に**、ユースケースに適したキャンペーンのタイプを理解することが重要です。 Adobe Journey Optimizerは、それぞれ異なるシナリオとアクティブ化メカニズム向けに設計された、次の 3 つのキャンペーンタイプをサポートします。

![](assets/campaign-modal.png)

>[!BEGINTABS]

>[!TAB  アクションキャンペーン （スケジュール済み） ]

**用途：** シンプルでスケジュールに沿ったバッチ通信

**アクションキャンペーン** （スケジュール済みキャンペーンとも呼ばれます）は、特定の時間に実行されるわかりやすい 1 回限りのバッチ通信または繰り返しバッチ通信に最適です。

**2 つのカテゴリ：**

* **マーケティング** - プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意事項、ポリシーの更新。 受信者はオプトインしている必要があります。
* **トランザクション** – 中断、緊急事態、キャンセル。 オプトインは必要ありません。

**最適な対象：** 顧客セグメントへの月次ニュースレター、時間依存のプロモーションのお知らせ、季節的なマーケティングキャンペーン、製品発売に関するお知らせ、サービス中断の通知など。

➡️[&#x200B; アクションキャンペーンについて学ぶ &#x200B;](create-campaign.md)

>[!TAB API トリガーキャンペーン]

**用途：** 外部システムとのリアルタイムのイベント駆動型メッセージ

**API トリガーキャンペーン** API 呼び出しを通じてアクティブ化し、外部システムから直接 Automated Messaging を有効にします。 これらのキャンペーンは、API ペイロードのプロファイル属性とリアルタイムコンテキストデータの両方を使用したパーソナライゼーションをサポートしています。

**2 つのカテゴリ：**

* **マーケティング** - ターゲットオーディエンスに対するパーソナライズされたマーケティングコミュニケーション
* **トランザクション** – 個々のアクション（パスワードのリセット、買い物かごの購入など）に続くメッセージ

**最適な対象：** パスワードリセットの確認、買い物かごの放棄の回復、注文の確認と配送の更新、アカウントのアクティビティの通知、リアルタイムでパーソナライズされたレコメンデーション。

➡️ [API トリガーキャンペーンについて学ぶ &#x200B;](api-triggered-campaigns.md)

>[!TAB オーケストレーションキャンペーン]

**使用するタイミング：** 複雑な複数手順のマーケティングワークフロー

**調整されたキャンペーン** は、高度なマーケティングワークフローを設計および自動化するための視覚的なドラッグ&amp;ドロップキャンバスを提供します。 オーディエンスのセグメント化から、チャネルをまたいでパーソナライズされたメッセージ配信に至るまで、すべてが迅速かつ制御可能に構築された直感的な 1 つの環境で行われます。

**最適な対象：** 複数手順の顧客エンゲージメントプログラム、複雑なセグメント化およびターゲティング戦略、クロスチャネルキャンペーンオーケストレーション、大規模なブランド主導のマーケティング、複数の決定ポイントを備えた高度なワークフロー自動化。

➡️[&#x200B; オーケストレートキャンペーンについて学ぶ &#x200B;](../orchestrated/gs-orchestrated-campaigns.md)

>[!ENDTABS]

>[!NOTE]
>
>どのタイプを選択するか不明な場合は、 スケジュールされたバッチ通信用の **アクションキャンペーン** またはリアルタイムメッセージ用の **API トリガーキャンペーン** から開始します。これらは、最も一般的なユースケースをカバーしています。

## キャンペーン作成ワークフロー {#workflow}

成功するキャンペーンを作成するには、明確で繰り返し可能なプロセスに従います。 ステップバイステップのワークフローを次に示します。

**1. プラン** → **2. 設定** → **3. デザイン** → **4. 確認** → **5. 有効化** → **6. 監視**

### &#x200B;1. キャンペーンの計画 {#plan}

開始する前に、目的を明確にします。

* **目標は何ですか？** （例：コンバージョンの促進、エンゲージメントの向上、顧客への通知）
* **観客はだれですか。** （例：Adobe Experience Platformからビルドまたは選択）
* **適合するキャンペーンタイプはどれですか？** （上記の [&#x200B; キャンペーンタイプ &#x200B;](#campaign-types) を参照）
* **どのチャネルを使用しますか？** （メール、プッシュ、SMS、アプリ内、web など）→[&#x200B; キャンペーンタイプ別のサポートされるチャネルを参照 &#x200B;](../channels/gs-channels.md#channels)
* **実行するタイミング** （即時、スケジュール済みまたは API トリガー）

### &#x200B;2. キャンペーンプロパティの設定 {#configure}

キャンペーンの基盤を設定します。

1. **名前と説明** キャンペーンを識別しやすくします
2. **キャンペーンタイプを選択** （アクション、API トリガー、オーケストレーションのいずれか）
3. **オーディエンスの選択**
4. **優先度を設定** （競合管理を使用する場合）
5. **スケジュールの設定** （アクションキャンペーンの場合）または API の詳細（API トリガーの場合）

**タイプ固有のガイド：**&#x200B;[&#x200B; アクションキャンペーンのプロパティ &#x200B;](campaign-properties.md) | [API トリガー型キャンペーンプロパティ &#x200B;](api-triggered-campaign-properties.md) | [&#x200B; キャンペーン設定を調整 &#x200B;](../orchestrated/create-orchestrated-campaign.md)

### &#x200B;3. コンテンツのデザイン {#design}

オーディエンスに魅力的なメッセージを作成します。

* リッチなメールエクスペリエンスには **メールDesigner** を使用します
* 画像とディープリンクを使用した **プッシュ通知** の設定
* パーソナライゼーションを使用した **SMS/MMS メッセージ** のデザイン
* **アプリ内** エクスペリエンスと **web** エクスペリエンスの作成
* プロファイル属性とコンテキストデータを使用した **パーソナライゼーション** の追加

**タイプ固有のガイド：**&#x200B;[&#x200B; アクションキャンペーンコンテンツ &#x200B;](campaign-content.md) | [API トリガー型キャンペーンコンテンツ &#x200B;](api-triggered-campaign-content.md) | [&#x200B; キャンペーンコンテンツの調整 &#x200B;](../orchestrated/create-orchestrated-campaign.md)

### 4.確認とテスト {#review}

アクティブ化の前にキャンペーンを常に確認してください。

* テストプロファイルを使用した **コンテンツのプレビュー**
* **ターゲティングを確認** して、適切なオーディエンスを確保します
* **スケジュールとアクティブ化** 設定の確認
* **承認をリクエスト** 承認ワークフローを使用している場合
* シードリストを使用した **配信品質のテスト**

**タイプ固有のガイド：**&#x200B;[&#x200B; アクションキャンペーンのレビュー &#x200B;](review-activate-campaign.md) | [API トリガーキャンペーンのレビュー &#x200B;](review-activate-api-triggered-campaign.md) | [&#x200B; 調整されたキャンペーンのレビュー &#x200B;](../orchestrated/create-orchestrated-campaign.md)

### &#x200B;5. キャンペーンのアクティブ化 {#activate}

レビューが完了したら、キャンペーンをアクティブ化します。

* **手動アクティベーション** – 即時またはスケジュールされた時間にアクティブ化します
* **API アクティベーション** - API トリガーキャンペーンの場合は、アクティベーションエンドポイントを使用します
* **承認プロセス** – 必要に応じて、関係者の承認を待ちます
* 注意：アクティブなキャンペーンは編集できません（変更するには複製する必要があります）

**タイプ固有のガイド：**&#x200B;[&#x200B; アクションキャンペーンのアクティブ化 &#x200B;](review-activate-campaign.md) | [API トリガーキャンペーンのアクティブ化 &#x200B;](review-activate-api-triggered-campaign.md) | [&#x200B; オーケストレーションされたキャンペーンのアクティブ化 &#x200B;](../orchestrated/create-orchestrated-campaign.md)

### 6.監視と分析 {#monitor}

キャンペーンのパフォーマンスを追跡：

* キャンペーンレポートと分析の表示
* 配信率とエンゲージメント指標の監視
* エラーとバウンスの追跡
* コンバージョンと ROI の分析
* 最適化のためのインサイトの使用

**タイプ固有のガイド：**&#x200B;[&#x200B; アクションキャンペーンレポート &#x200B;](../reports/campaign-global-report-cja.md) | [API トリガーキャンペーン監視 &#x200B;](api-triggered-campaigns.md#monitor) | [&#x200B; キャンペーン分析の調整 &#x200B;](../orchestrated/create-orchestrated-campaign.md)

➡️ **開始する準備ができましたか？** キャンペーンタイプを選択します。
* [アクションキャンペーン→ールの作成](create-campaign.md)
* [API トリガーキャンペーン→ールの作成](api-triggered-campaigns.md)
* [オーケストレーションされたキャンペーン→の作成](../orchestrated/gs-orchestrated-campaigns.md)

## 前提条件 {#prerequisites}

キャンペーンを使用する前に、次の点を確認します。

### 必要な設定

* **オーディエンス** - キャンペーンを作成する前に、オーディエンスをAdobe Experience Platformで使用できる必要があります。 [&#x200B; オーディエンス→ースの基本を学ぶ &#x200B;](../audience/about-audiences.md)

* **チャネル設定** - チャネル設定（プリセット）を作成し、使用するチャネルで使用可能にする必要があります。 [&#x200B; チャネル設定のセットアップ→](../configuration/channel-surfaces.md)

* **権限** - キャンペーンタイプに基づく適切な権限が必要です。 Campaign の機能にアクセスできない場合は、管理者にお問い合わせください。 [&#x200B; 組み込みの役割→ついて説明します &#x200B;](../administration/ootb-product-profiles.md)。

  | キャンペーンタイプ | 権限 |
  |----------------------------|----------------------------------------------------------------------------|
  | **アクションキャンペーン** | キャンペーン管理者<br>キャンペーン承認者<br>キャンペーンマネージャー<br>キャンペーンビューアー |
  | **API トリガーキャンペーン** | キャンペーン管理者<br>キャンペーン承認者<br>キャンペーンマネージャー<br>キャンペーンビューアー |
  | **オーケストレーションキャンペーン** | オーケストレーションキャンペーン管理者<br>オーケストレーションキャンペーン承認者<br>オーケストレーションキャンペーンマネージャー<br>オーケストレーションキャンペーンビューアー |

+++キャンペーン権限の割り当て

1. **[!UICONTROL 製品の]** 役割 [!DNL Permissions] タブに移動し、組み込みのキャンペーン関連の **[!UICONTROL 役割]** のいずれかを選択します。

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

   まだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/users){target="_blank"}を参照してください。

   これにより、ユーザーをインスタンスへリダイレクトするメールがユーザーに送られます。

   +++

## Campaign 機能 {#capabilities}

キャンペーンに慣れたら、次の強力な機能を探索します。

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg)

**スケジュールとタイミング**

キャンペーンを特定の日時にスケジュールし、繰り返し配信を設定し、最大効果が得られるように送信時間を最適化します。 （アクションおよび API トリガーキャンペーン）

[スケジュールについて学ぶ](campaign-schedule.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**レートコントロール**

ランディングページやカスタマーケアプラットフォームなどのダウンストリームシステムでの過負荷を防ぐために、メッセージのスループットを制限します。 （アクションおよび API トリガーキャンペーン）

[コントロールレートの制限](create-campaign.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**オーディエンスのターゲティング**

特定のAdobe Experience Platform オーディエンスを正確にターゲット設定し、オーディエンスの選定を動的に管理します。

[キャンペーンオーディエンスを選択](campaign-audience.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**承認ワークフロー**

キャンペーンを開始する前にレビューおよび承認プロセスを実装し、品質とコンプライアンスを確保します。 （アクションおよび API トリガーキャンペーン）

[レビューしてアクティブ化](review-activate-campaign.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/clock.svg)

**通知のない時間帯**

指定した時間枠にメッセージを配信しないようにすることで、顧客の好みを尊重します。 （アクションおよび API トリガーキャンペーン）

[クワイエットアワーの設定](quiet-hours.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**最適化**

ターゲティングルールとコンテンツ実験を使用して、パーソナライズされたコンテンツを配信し、エンゲージメントを最大化します。

[キャンペーンの最適化](campaigns-message-optimization.md)
:::

::::

## キャンペーンタイプの基本を学ぶ {#get-started-types}

これで [!DNL Journey Optimizer] でキャンペーンを理解できたので、開始するにはキャンペーンタイプを選択します。

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img width="70%" alt="アクションキャンペーン" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">アクションキャンペーン</a></td>
<td><a href="api-triggered-campaigns.md"><img width="70%" alt="SMS" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API トリガーキャンペーン</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img width="70%" alt="プッシュ" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">調整されたキャンペーン</a></td>
</tr></table>

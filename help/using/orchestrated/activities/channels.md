---
solution: Journey Optimizer
product: journey optimizer
title: 複数手順キャンペーンでのチャネルアクティビティの追加
description: 複数ステップのキャンペーンでチャネルアクティビティを追加する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: ffe1e77c-6c4f-4f23-9183-d715a4c7c402
source-git-commit: 30e22bc1a2ab95dbbef1fb35a01cd2f5d5b02423
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 31%

---

# チャネルアクティビティ {#channel}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_email"
>title="メールアクティビティ"
>abstract="メールアクティビティを使用すると、調整されたキャンペーン内で、1 回限りのメッセージと繰り返しメッセージの両方でメールを送信できます。これは、調整された同じキャンペーン内で計算されたターゲットにメールを送信するプロセスを自動化するのに役立ちます。チャネルアクティビティを複数の手順のキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_sms"
>title="SMS アクティビティ"
>abstract="SMS アクティビティを使用すると、調整されたキャンペーン内で、1 回限りのメッセージと繰り返しメッセージで SMS を送信できます。これは、調整された同じキャンペーン内で計算されたターゲットに SMS を送信するプロセスを自動化するのに役立ちます。チャネルアクティビティを複数の手順のキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push"
>title="プッシュアクティビティ"
>abstract="プッシュアクティビティを使用すると、調整されたキャンペーンの一部としてプッシュ通知を送信できます。これにより、1 回限りのキャンペーンと調整された繰り返しのキャンペーンの両方の配信が可能になり、調整された同じキャンペーン内の定義済みターゲットへのプッシュ通知の送信が自動化されます。チャネルアクティビティをキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。"

<!--
UNUSED IDs in BJ

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push_ios"
>title="Push iOS activity"
>abstract="The Push iOS activity let you send iOS Push notifications as part of your orchestrated campaign. It enables the delivery of both one-time and recurring orchestrated campaigns, automating the sending iOS Push notifications to a predefined target within the same workflow. You can combine channel activities into the campaign canvas to create cross-channel campaigns that can trigger actions based on customer behavior and data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push_android"
>title="Push Android activity"
>abstract="The Push Android activity ket you send Android Push notifications as part of your orchestrated campaign. It enables the delivery of both one-time and recurring messages, automating the sending Android Push notifications to a predefined target within the same orchestrated campaign. You can combine channel activities into the orchestrated campaign canvas to create cross-channel campaigns that can trigger actions based on customer behavior and data."

-->

>[!CONTEXTUALHELP]
>id="ajo_orchestration_directmail"
>title="ダイレクトメールアクティビティ"
>abstract="ダイレクトメールアクティビティでは、調整されたキャンペーン内でのダイレクトメール送信が促進され、1 回限りのメッセージと繰り返しメッセージの両方を送信できます。これは、ダイレクトメールプロバイダーが必要とする抽出ファイルを生成するプロセスを自動化するのに役立ちます。チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。"


+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ ルールビルダーの操作 ](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](../build-query.md)<br/><br/>[ 式の編集 ](../edit-expressions.md)<br/><br/>[ リターゲティング ](../retarget.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションの変更 ](change-dimension.md) - <b>[ チャネルアクティビティ ](channels.md)</b> - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) [ ](save-audience.md) [ ](split.md) [ ](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

[!DNL Adobe Journey Optimizer] を使用すると、メール、SMS、プッシュ通知などのチャネルをまたいでマーケティングキャンペーンを自動化および実行できます。 これらのチャネルアクティビティをキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーにできるクロスチャネルオーケストレーションされたキャンペーンを作成できます。

例：
* メール、SMS およびプッシュを使用して、ウェルカムシリーズを送信します。
* 購入後に、フォローアップメールを送信します。
* SMS を使用してパーソナライズされた誕生日の挨拶を送信します。

チャネルアクティビティを使用すると、複数のタッチポイントで顧客を引きつけてコンバージョンを促進する、包括的でパーソナライズされたキャンペーンを作成できます。

>[!PREREQUISITES]
>
>チャネルアクティビティを追加する前に、[ オーディエンスを作成アクティビティ ](build-audience.md) を使用してターゲットオーディエンスを定義します。

## チャネルアクティビティを追加し、そのプロパティを定義します {#add}

1. チャネルアクティビティをキャンバスに追加します。 使用可能なチャネルアクティビティは、**[!UICONTROL メール]**、**[!UICONTROL SMS]** および **[!UICONTROL プッシュ]** です。

   ![ 使用可能なアクティビティを含むキャンバスを示す画像 ](../assets/channel-add.png)

1. アクティビティを選択し、選択したチャネルに応じて **[!UICONTROL メールを編集]**、**[!UICONTROL SMS を編集]** または **[!UICONTROL プッシュを編集]** をクリックします。

   ![ メールアクティビティでキャンバスを示す画像 ](../assets/channel-edit.png)

1. 「**[!UICONTROL プロパティ]**」タブで、説明を入力し、「**[!UICONTROL アクション]**」タブに切り替えてアクティビティを設定します。

## チャネル設定と設定の指定 {#configuration}

「**[!UICONTROL アクション]**」タブを使用して、メッセージのチャネル設定を選択し、トラッキング、コンテンツ実験、多言語コンテンツなどの追加設定を指定します。

1. チャネル設定を選択します。

   設定は、[システム管理者](../../start/path/administrator.md)によって定義されます。ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。 [ チャネル設定の設定方法を学ぶ ](../../configuration/channel-surfaces.md)。

   ![ 「アクション」セクションを示す画像 ](../assets/channel-actions.png)

1. エンゲージメントの追跡（メールおよび SMS の場合）

   「**[!UICONTROL アクショントラッキング]**」セクションを使用すると、メールや SMS 配信に対する受信者の反応をトラッキングできます。 キャンペーンが実行されると、キャンペーンレポートからトラッキング結果にアクセスできるようになります。[詳しくは、キャンペーンレポートを参照してください](../../reports/campaign-global-report-cja.md)

1. （プッシュ用の）迅速配信モードを有効にします。

   迅速配信モードは、キャンペーンを通じて大量のプッシュメッセージを非常に高速に送信できるようにする [!DNL Journey Optimizer] アドオンです。 迅速配信は、メッセージ配信の遅延がビジネス上の重要な問題になる状況で、携帯電話に緊急のプッシュアラートを送信するときに使用します（ニュースチャネルアプリをインストールしたユーザーにニュース速報を流すなど）。 迅速配信モードを使用する際のパフォーマンスについて詳しくは、[Adobe Journey Optimizer 製品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html)を参照してください。

1. コンテンツ実験を作成します。

   「**[!UICONTROL コンテンツ実験]**」セクションを使用して、複数の配信処理を定義し、ターゲットオーディエンスに最適なパフォーマンスを発揮する配信処理を測定します。 「**[!UICONTROL 実験を作成]**」ボタンをクリックし、[ コンテンツ実験を作成 ](../../content-management/content-experiment.md) の節で説明している手順に従います。

1. 多言語コンテンツの追加。

   「**[!UICONTROL 言語]**」セクションを使用すると、キャンペーン内の複数の言語でコンテンツを作成できます。 それには、「**[!UICONTROL 言語を追加]**」ボタンをクリックし、目的の **[!UICONTROL 言語設定]** を選択します。 多言語機能のセットアップおよび使用方法について詳しくは、この節を参照してください。[ 多言語コンテンツの基本を学ぶ ](../../content-management/multilingual-gs.md)

   ![ 「コンテンツ実験」セクションを示す画像 ](../assets/channel-experiment.png)

チャネルアクティビティを設定したら、「**[!UICONTROL コンテンツ]**」タブを選択してコンテンツを定義します。

## コンテンツの定義 {#content}

「**[!UICONTROL コンテンツ]**」タブに切り替えて、メッセージを作成します。 手順は、選択したチャネルによって異なります。 メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;" >
<td><a href="../../email/create-email.md"><img alt="メール" src="../../channels/assets/do-not-localize/email.png"></a><br/><a href="../../email/create-email.md"><strong>メールの作成</strong></a></td>
<td><a href="../../sms/create-sms.md"><img alt="SMS" src="../../channels/assets/do-not-localize/sms.png"></a><br/><a href="../../sms/create-sms.md"><strong>SMS の作成</strong></a></td>
<td><a href="../../push/create-push.md"><img alt="プッシュ" src="../../channels/assets/do-not-localize/push.png"></a><a href="../../push/create-push.md"><strong>プッシュ通知の作成</strong></a></td>
</tr></table>

## パーソナライゼーションの追加

オーケストレートキャンペーンのPersonalizationは、他の **[!UICONTROL Journey Optimizer]** キャンペーンやジャーニーと同様に機能しますが、オーケストレーションされたキャンバスに固有の重要な違いがいくつかあります。

調整されたキャンペーンからパーソナライゼーションエディターにアクセスする場合、2 つの主なフォルダーには、以下に詳しく説明するように、パーソナライゼーションに使用できる属性が含まれています。

* **[!UICONTROL プロファイル属性]**

  このフォルダーには、[!DNL Adobe Experience Platform] のすべてのプロファイル関連データが含まれます。 これらは、名前、メールアドレス、場所、ユーザープロファイルで取得されるその他の特性などの標準的な属性です。

* **[!UICONTROL ターゲット属性]** （オーケストレーションされたキャンペーンに固有）

  このフォルダーは、オーケストレーションされたキャンペーンに固有です。 キャンペーンキャンバス内で直接計算された属性が含まれます。 次の 2 つのサブフォルダーが含まれます。

   * **`<Targeting dimension>`** （「受信者」、「購入」など）：キャンペーンのターゲットとなるディメンションに関連するすべての属性が含まれます。

   * **`Enrichment`**: **[!UICONTROL エンリッチメント]** アクティビティを通じて追加されたデータをキャンバスに含めます。 これにより、外部データセットや、オーケストレーション中に組み込まれた追加のロジックに基づいて、メッセージをパーソナライズできます。 [ エンリッチメントアクティビティの使用方法を学ぶ ](../activities/enrichment.md)

パーソナライゼーションエディターの使用方法について詳しくは、[ パーソナライゼーションの概要 ](../../personalization/personalize.md) を参照してください

## コンテンツのチェックとテスト

コンテンツを作成したら、「**[!UICONTROL コンテンツをシミュレート]**」ボタンを使用して、テストプロファイルや CSV/JSON ファイルからアップロードしたサンプル入力データまたは手動で追加したサンプル入力データで、コンテンツをプレビューおよびテストします。 [詳細情報](../../content-management/preview-test.md)

![ 「コンテンツをシミュレート」ボタンを示す画像 ](../assets/channel-simulate.png)

## 次の手順 {#next}

メッセージコンテンツの準備が整ったら、**[!UICONTROL 戻る]** 矢印を使用して、オーケストレーションされたキャンペーンに戻ります。 その後、キャンバスでアクティビティオーケストレーションを完了し、キャンペーンを公開して、メッセージの送信を開始できます。 [ オーケストレートキャンペーンを開始および監視する方法について説明します ](../start-monitor-campaigns.md)

![ 「戻る」ボタンを示す画像 ](../assets/channel-back.png)

<!--
## Examples {#cross-channel-workflow-sample}

Here is a cross-channel orchestrated campaign example with a segmentation and two deliveries. The orchestrated campaign targets all customers who live in Paris and who are interested in coffee machines. Among this population, an email is sent to the regular customers and an SMS is sent to the VIP clients.

![](../assets/workflow-channel-example.png)

<!--
description, which use case you can perform (common other activities that you can link before of after the activity)

how to add and configure the activity

example of a configured activity within a workflow
The Email delivery activity allows you to configure the sending an email in a workflow. 

-->

<!--You can also create a recurring orchestrated campaign to send a personalized SMS every first day of the month at 8 PM to all customers living in Paris.

![](../assets/workflow-channel-example2.png)-->

<!-- Scheduled emails available?

This can be a single send email and sent just once, or it can be a recurring email.
* Single send emails are standard emails, sent once.
* Recurring emails allow you to send the same email multiple times to different targets over a defined period. You can aggregate the deliveries per period in order to get reports that correspond to your needs.

When linked to a scheduler, you can define recurring emails.
Email recipients are defined upstream of the activity in the same workflow, via an Audience targeting activity.

-->


<!--The message preparation is triggered according to the workflow execution parameters. From the message dashboard, you can select whether to request or not a manual confirmation to send the message (required by default). You can start the workflow manually or place a scheduler activity in the workflow to automate execution.-->

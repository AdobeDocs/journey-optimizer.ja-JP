---
solution: Journey Optimizer
product: journey optimizer
title: 複数手順キャンペーンでのチャネルアクティビティの追加
description: 複数ステップのキャンペーンでチャネルアクティビティを追加する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: ffe1e77c-6c4f-4f23-9183-d715a4c7c402
source-git-commit: d8b83bc46526f721d4dfaf62cf8ba4cbf5a56ce7
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 30%

---

# チャネルアクティビティ {#channel}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](../gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](../configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](../gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](../orchestrate-activities.md)<br/><br/><br/>[ キャンペーンの開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) | [ クエリの操作Modeler](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリ ](../build-query.md)<br/><br/>[ 編集式を作成 ](../edit-expressions.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションの変更 ](change-dimension.md) - **[チャネルアクティビティ](activities/channels.md)** - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) [&#128279;](split.md) [&#128279;](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

[!DNL Adobe Journey Optimizer] を使用すると、様々なチャネルをまたいでマーケティングキャンペーンを自動化および実行できます。 チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーにできるクロスチャネルの調整されたキャンペーンを作成できます。

例えば、メール、SMS、プッシュなど、様々なチャネルをまたいだ一連のメッセージを含むウェルカムメールキャンペーンを作成できます。また、顧客が購入を完了した後や、SMS を使用してパーソナライズされた誕生日メッセージを顧客に送信した後に、フォローアップメールを送信することもできます。

チャネルアクティビティを使用すると、複数のタッチポイントで顧客を引きつけてコンバージョンを促進する、包括的でパーソナライズされたキャンペーンを作成できます。 サポートされるチャネルは、メール、SMS およびプッシュです。

## 前提条件 {#channel-activity-prereq}

関連するアクティビティを使用して、調整されたキャンペーンの作成を開始します。

* チャネルアクティビティを挿入する前に、オーディエンスを定義する必要があります。オーディエンスは配信のメインターゲット、つまりメッセージを受信するプロファイルです。[ オーディエンスを作成アクティビティの使用方法を学ぶ ](build-audience.md)

* 繰り返し配信を送信するには、調整したキャンペーンを **[!UICONTROL スケジューラー]** アクティビティで開始します。 また、「**[!UICONTROL スケジューラー]**」アクティビティを 1 回限りのワンショット配信に使用して、その配信の連絡日を設定することもできます。この連絡日は、配信設定でも設定できます。[ 調整されたキャンペーンのスケジュール設定方法を説明します ](../create-orchestrated-campaign.md#schedule)

## チャネルを設定アクティビティ {#create-a-delivery-in-a-workflow}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_email"
>title="メールアクティビティ"
>abstract="メール アクティビティを使用すると、1 回限りのメッセージと繰り返しメッセージの両方について、オーケストレーションされたキャンペーン内でメールを送信できます。 同じ調整されたキャンペーン内で計算されたターゲットにメールを送信するプロセスを自動化する役割を果たします。 チャネルアクティビティを複数の手順のキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_sms"
>title="SMS アクティビティ"
>abstract="SMS アクティビティを使用すると、1 回限りのメッセージと繰り返しメッセージの両方について、オーケストレーションされたキャンペーン内で SMS を送信できます。 同じオーケストレーションされたキャンペーン内で計算されたターゲットに SMS を送信するプロセスを自動化する役割を果たします。 チャネルアクティビティを複数の手順のキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push"
>title="プッシュアクティビティ"
>abstract="プッシュ アクティビティを使用すると、調整されたキャンペーンの一部としてプッシュ通知を送信できます。 1 回限りのキャンペーンと繰り返しのオーケストレートキャンペーンの両方を配信でき、同じオーケストレートキャンペーン内の事前定義済みターゲットにプッシュ通知を自動的に送信できます。 チャネルアクティビティをキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーにできるクロスチャネルキャンペーンを作成できます。"

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
>abstract="ダイレクトメールアクティビティは、1 回限りのメッセージと繰り返しメッセージの両方について、オーケストレーションされたキャンペーン内でのダイレクトメール送信を容易にします。 これは、ダイレクトメールプロバイダーが必要とする抽出ファイルを生成するプロセスを自動化するのに役立ちます。チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーにできるクロスチャネルキャンペーンを作成できます。"

オーケストレーションされたキャンペーンのコンテキストで配信を設定するには、次の手順に従います。

### チャネルアクティビティを追加し、そのプロパティを定義します {#add}

1. チャネルアクティビティをキャンバスに追加します。 使用可能なチャネルアクティビティは、**[!UICONTROL メール]**、**[!UICONTROL SMS]** および **[!UICONTROL プッシュ]** です。

   ![ 使用可能なアクティビティを含むキャンバスを示す画像 ](../assets/channel-add.png)

1. 追加されたアクティビティを選択し、選択したチャネルに応じて **[!UICONTROL メールを編集]**、**[!UICONTROL SMS を編集]** または **[!UICONTROL プッシュを編集]** ボタンをクリックします。

   ![ メールアクティビティでキャンバスを示す画像 ](../assets/channel-edit.png)

1. **[!UICONTROL プロパティ]** タブで、キャンペーンの説明を入力します。

### チャネル設定と設定の指定 {#configuration}

1. **[!UICONTROL アクション]** タブを選択し、メッセージに使用するチャネル設定を選択します。

   設定は、[システム管理者](../../start/path/administrator.md)によって定義されます。ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。 [ チャネル設定の設定方法を学ぶ ](../../configuration/channel-surfaces.md)。

1. メールおよび SMS の場合、トラッキングオプションを使用すると、メールまたは SMS 配信に対する受信者の反応を監視できます。

   キャンペーンが実行されると、キャンペーンレポートからトラッキング結果にアクセスできるようになります。[詳しくは、キャンペーンレポートを参照してください](../reports/campaign-global-report-cja.md)

1. プッシュ通知の場合、「**[!UICONTROL 迅速配信モード]**」オプションを使用すると、プッシュチャネルで 3,000 万未満のオーディエンスサイズに高速メッセージ送信を実行できます。

   迅速配信モードは、大量のプッシュメッセージを非常に高速に送信できるようにする **[!DNL Journey Optimizer]** アドオンです。 [詳細情報](../push/create-push.md#rapid-delivery)

1. 「**[!UICONTROL コンテンツ実験]**」セクションでは、複数の配信処理を定義して、ターゲットオーディエンスに最適なパフォーマンスを発揮する配信処理を測定できます。

   これを行うには、「**[!UICONTROL 実験を作成]**」ボタンをクリックし、[ コンテンツ実験の機能を作成 ](../../content-management/content-experiment.md) の節で説明されている手順に従います。

1. 「**[!UICONTROL 言語]**」セクションでは、キャンペーン内で複数の言語のコンテンツを作成できます。

   それには、「**[!UICONTROL 言語を追加]**」ボタンをクリックし、目的の **[!UICONTROL 言語設定]** を選択します。 多言語機能のセットアップおよび使用方法について詳しくは、この節を参照してください。[ 多言語コンテンツの基本を学ぶ ](../../content-management/multilingual-gs.md)

### コンテンツの定義 {#content}

「**[!UICONTROL コンテンツ]**」タブを選択して、メッセージのコンテンツを定義します。 コンテンツの作成プロセスは、選択したチャネルによって異なります。

メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。

<table style="table-layout:fixed"><tr style="border: 0;">
<td><a href="../../email/create-email.md"><img alt="メール" src="../../channels/assets/do-not-localize/email.png"></a>
<div align="center"><a href="../../email/create-email.md"><strong>メール</strong></a></div></td>
<td><a href="../sms/../create-sms.md"><img alt="SMS" src="../../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><a href="../../sms/create-sms.md"><strong>SMS</strong></a></div></td>
<td><a href="../push/create-push.md"><img alt="プッシュ" src="../../channels/assets/do-not-localize/push.png"></a>
<div align="center"><a href="../../push/create-push.md"><strong>プッシュ通知</strong></a></div></td>
</tr></table>

コンテンツを定義したら、「**[!UICONTROL コンテンツをシミュレート]**」ボタンを使用して、CSV／JSON ファイルからアップロードした、または手動で追加したテストプロファイルやサンプル入力データを使用して、そのコンテンツをプレビューおよびテストします。[詳細情報](../content-management/preview-test.md)

## 次の手順 {#next}

**[!UICONTROL 戻る]** 矢印を使用して、オーケストレーションされたキャンペーンに戻ります。

![ 「戻る」ボタンを示す画像 ](../assets/channel-back.png)

これで、キャンバスでアクティビティオーケストレーションを完了し、キャンペーンを公開してメッセージの送信を開始できます。 [ オーケストレートキャンペーンを開始および監視する方法について説明します ](../start-monitor-campaigns.md)

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

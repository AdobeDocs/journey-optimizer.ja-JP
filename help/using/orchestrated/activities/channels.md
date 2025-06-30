---
solution: Journey Optimizer
product: journey optimizer
title: 複数手順キャンペーンでのチャネルアクティビティの追加
description: 複数ステップのキャンペーンでチャネルアクティビティを追加する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: ffe1e77c-6c4f-4f23-9183-d715a4c7c402
source-git-commit: d8128190a51cac665c9f25b5077185a496ad7849
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 36%

---

# チャネルアクティビティ {#channel}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](../gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](../configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](../gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](../send-messages.md)<br/><br/>[ キャンペーンの開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) | [ クエリの操作Modeler](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリ ](../build-query.md)<br/><br/>[ 編集式を作成 ](../edit-expressions.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションを変更 ](change-dimension.md) - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) - [ 分割 ](split.md) [ ](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

Adobe Journey Optimizerを使用すると、インバウンドチャネルとアウトバウンドチャネルをまたいでマーケティングキャンペーンを自動化および実行できます。 チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーにできるクロスチャネルの調整されたキャンペーンを作成できます。 サポートされているチャネルは [ このページ ](../../channels/gs-channels.md) に一覧表示されます。

例えば、メール、SMS、プッシュ、ダイレクトメールなど、様々なチャネルをまたいで一連のメッセージを含むウェルカムメールキャンペーンを作成できます。また、顧客が購入を完了した後や、SMS を使用してパーソナライズされた誕生日メッセージを顧客に送信した後に、フォローアップメールを送信することもできます。

チャネルアクティビティを使用すると、複数のタッチポイントで顧客を引きつけてコンバージョンを促進する、包括的でパーソナライズされたキャンペーンを作成できます。

## 前提条件 {#channel-activity-prereq}

関連するアクティビティを使用して、調整されたキャンペーンの作成を開始します。

* チャネルアクティビティを挿入する前に、オーディエンスを定義する必要があります。オーディエンスは配信のメインターゲットであり、メッセージを受信するプロファイルとなります。

* 繰り返し配信を送信するには、調整したキャンペーンを **[!UICONTROL スケジューラー]** アクティビティで開始します。 また、「**[!UICONTROL スケジューラー]**」アクティビティを 1 回限りのワンショット配信に使用して、その配信の連絡日を設定することもできます。その連絡日は、配信設定でも設定できます。

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

1. チャネルアクティビティを追加します。 サポートされるチャネルは、**[!UICONTROL メール]**、**[!UICONTROL SMS]** または **[!UICONTROL プッシュ通知]** です

1. 「**配信のタイプ**」（単一または繰り返し）を選択します。

   * **単一の配信**&#x200B;は 1 回限りの配信で、ブラックフライデーのメールなど 1 回だけ送信されます。
   * **繰り返し配信** は、実行頻度に基づいて複数回送信されます。 オーケストレーションされたキャンペーンが実行されるたびに、オーディエンスが再計算され、更新されたオーディエンスに更新されたコンテンツと共に配信が送信されます。 例えば、週刊ニュースレターや毎年の誕生日メールなどがあります。

1. 配信&#x200B;**[!UICONTROL テンプレート]**&#x200B;を選択します。テンプレートは、チャネルに固有の事前設定済みの配信設定です。組み込みテンプレートは各チャネルで使用でき、デフォルトでは事前入力されます。

   ![](../assets/delivery-activity-in-wf.png)

   チャネルアクティビティ設定の左側のパネルからテンプレートを選択できます。以前に選択したオーディエンスがチャネルに対応していない場合は、テンプレートを選択できません。これを解決するには、**[!UICONTROL オーディエンスを作成]** アクティビティを更新して、ターゲットマッピングが正しいオーディエンスを選択します。

1. 「**[!UICONTROL 配信を作成]**」をクリックします。スタンドアロン配信の作成時と同様に、メッセージの設定とコンテンツを定義できます。また、コンテンツをテストし、シミュレートすることもできます。

1. オーケストレーションされたキャンペーンに戻ります。 オーケストレーションされたキャンペーンを続行する場合は、「**[!UICONTROL アウトバウンドトランジションを生成]**」オプションを切り替えて、チャネルアクティビティの後にトランジションを追加します。

1. 「**[!UICONTROL 開始]**」をクリックして、調整したキャンペーンを開始します。

   デフォルトでは、オーケストレーションされたキャンペーンを開始すると、メッセージはすぐに送信されずに、メッセージの準備ステージにトリガーします。

1. チャネルアクティビティを開き、「**[!UICONTROL 確認して送信]**」ボタンから送信を確定します。

1. 配信ダッシュボードで、「**[!UICONTROL 送信]**」をクリックします。

## 例 {#cross-channel-workflow-sample}

以下は、セグメント化と 2 つの配信を含むクロスチャネルオーケストレーションされたキャンペーンの例です。 オーケストレーションされたキャンペーンは、パリに在住し、コーヒーマシンに興味があるすべての顧客をターゲットにします。 この母集団の中で、通常の顧客にはメールが送信され、VIP クライアントには SMS が送信されます。

![](../assets/workflow-channel-example.png)

<!--
description, which use case you can perform (common other activities that you can link before of after the activity)

how to add and configure the activity

example of a configured activity within a workflow
The Email delivery activity allows you to configure the sending an email in a workflow. 

-->

また、毎月 1 日の午後 8 時に、パリに住むすべての顧客にパーソナライズされた SMS を送信する、繰り返しのオーケストレートキャンペーンを作成することもできます。

![](../assets/workflow-channel-example2.png)

<!-- Scheduled emails available?

This can be a single send email and sent just once, or it can be a recurring email.
* Single send emails are standard emails, sent once.
* Recurring emails allow you to send the same email multiple times to different targets over a defined period. You can aggregate the deliveries per period in order to get reports that correspond to your needs.

When linked to a scheduler, you can define recurring emails.
Email recipients are defined upstream of the activity in the same workflow, via an Audience targeting activity.

-->


<!--The message preparation is triggered according to the workflow execution parameters. From the message dashboard, you can select whether to request or not a manual confirmation to send the message (required by default). You can start the workflow manually or place a scheduler activity in the workflow to automate execution.-->

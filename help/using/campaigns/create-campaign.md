---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの作成
description: Journey Optimizer でキャンペーンを作成する方法を学ぶ
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: 作成, Optimizer, キャンペーン, サーフェス, メッセージ
exl-id: 617d623c-e038-4b5b-a367-5254116b7815
source-git-commit: c1ca6175e504dff5e89aaddc2105d150992a8b28
workflow-type: ht
source-wordcount: '1277'
ht-degree: 100%

---

# キャンペーンの作成 {#create-campaign}

新しいキャンペーンを作成するには、左側のパネルの&#x200B;**[!UICONTROL キャンペーン]**&#x200B;メニューを参照し、「**[!UICONTROL キャンペーンを作成]**」をクリックします。また、既存のライブキャンペーンを複製して新しいキャンペーンを作成することもできます。[方法についてはこちらを参照してください](modify-stop-campaign.md#duplicate)。

開始する前に、キャンペーンの前提条件について詳しくは、[このページ](get-started-with-campaigns.md#before-starting-campaign-prerequisites)を参照してください。

## キャンペーンタイプの選択 {#campaigntype}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="キャンペーンのタイプ"
>abstract="**スケジュール済みキャンペーン**&#x200B;は、即時または指定した日付に実行され、マーケティングタイプのメッセージを送信することを目的としています。**API トリガー**&#x200B;のキャンペーンは、API 呼び出しを使用して実行されます。これらは、マーケティングメッセージ（ユーザーの同意が必要なプロモーションメッセージ）またはトランザクションメッセージ（特定のコンテキストで登録解除済みのプロファイルにも送信できる非商用メッセージ）を送信することを目的としています。"

新しいキャンペーンを作成する際は、まずキャンペーンタイプを選択する必要があります。次の 3 つのキャンペーンタイプを使用できます。

1. **[!UICONTROL スケジュール済み - マーケティング]** - これらのキャンペーンは、即時または指定された日付に実行されます。スケジュール済みキャンペーンは、**マーケティング**&#x200B;メッセージの送信や、インバウンドアクションの作成を目的としています。ユーザーインターフェイスから設定および実行します。

1. **[!UICONTROL API トリガー - マーケティング]** - これらのキャンペーンは、API 呼び出しを使用して実行されます。ターゲットオーディエンスにパーソナライズされたマーケティングコミュニケーションを送信するには、このキャンペーンのタイプを選択します。[詳しくは、API を使用してキャンペーンをトリガーする方法を参照してください](api-triggered-campaigns.md)

1. **[!UICONTROL API トリガー - トランザクション]** - API トリガー - マーケティングキャンペーンと同様に、これらのキャンペーンは、API 呼び出しを使用して実行されます。API トリガートランザクションキャンペーンは、**トランザクション**&#x200B;メッセージ、つまり、個人が実行したアクション（パスワードのリセットリクエスト、買い物かごでの購入など）に続いて送信されるメッセージの送信を目的としています。[詳しくは、API を使用してキャンペーンをトリガーする方法を参照してください](api-triggered-campaigns.md)

   ![](assets/create-campaign-modal.png)

## キャンペーンのプロパティの定義 {#create}

キャンペーンを作成したら、プロパティを定義する必要があります。次の手順に従います。

1. 「**[!UICONTROL プロパティ]**」セクションで、キャンペーンの名前と説明を入力します。

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../content-management/content-experiment.md).-->

1. （オプション）「**タグ**」フィールドを使用して、Adobe Experience Platform 統合タグをキャンペーンに割り当てます。これにより、キャンペーンを簡単に分類し、キャンペーンリストからの検索を改善できます。[詳しくは、タグの操作方法を参照してください](../start/search-filter-categorize.md#tags)。

1. （オプション）アクセスラベルに基づいて、このキャンペーンへのアクセスを制限できます。アクセス制限を追加するには、このページの上部にある「**[!UICONTROL アクセスを管理]**」ボタンを参照します。権限のあるラベルのみを選択します。[詳しくは、オブジェクトレベルのアクセス制御を参照してください](../administration/object-based-access.md)。

## キャンペーンオーディエンスの定義 {#audience}

これで、キャンペーンのオーディエンスを選択できます。オーディエンスとは、類似した行動や特性を共有する一連のユーザーです。

>[!IMPORTANT]
>
>* [オーディエンス構成](../audience/get-started-audience-orchestration.md)からのオーディエンスおよび属性は現在、Healthcare Shield または Privacy and Security Shield では使用できません。
>
>* API トリガーキャンペーンの場合、オーディエンスは API 呼び出しを使用して設定する必要があります。

スケジュール済みマーケティングキャンペーンのターゲットとなる母集団を定義するには、次の手順に従います。

1. 「**オーディエンス**」セクションで、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform オーディエンスのリストを表示します。オーディエンスについて詳しくは、[この節](../audience/about-audiences.md)を参照してください。

1. 「**[!UICONTROL ID タイプ]**」フィールドで、選択したオーディエンスから個人を識別するために使用するキーのタイプを選択します。既存の ID タイプを使用することも、Adobe Experience Platform ID サービスを使用して新しい ID タイプを作成することもできます。標準 ID 名前空間について詳しくは、[このページ](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces#standard){target="_blank"}を参照してください。

   1 つのキャンペーンで使用できる ID タイプは 1 つだけです。様々な ID の中から選択した ID タイプを持たないセグメントに属する個人は、キャンペーンのターゲットにすることができません。

   ![](assets/create-campaign-namespace.png)

   ID タイプと名前空間について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja){target="_blank"}を参照してください。

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->


## チャネルの選択 {#channel}

ここでは、チャネルとその設定を選択します。次の手順に従います。

1. 「**[!UICONTROL アクション]**」セクションで、通信チャネルを選択します。

   使用可能なチャネルのリストは、ライセンスモデルとアドオンによって異なります。API トリガーキャンペーンの場合は、メール、SMS、プッシュ通知の各チャネルのみを使用できます。

1. チャネル設定を選択します。

   設定は、[システム管理者](../start/path/administrator.md)によって定義されます。ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。 [詳細情報](../configuration/channel-surfaces.md)。

   マーケティングキャンペーンタイプと互換性のあるチャネル設定のみがドロップダウンリストに一覧表示されます。

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >プッシュ通知キャンペーンを作成している場合、**[!UICONTROL 迅速配信モード]**&#x200B;を有効にできます。これは、大量のプッシュメッセージを非常に高速に送信できる Journey Optimizer アドオンです。[詳細情報](../push/create-push.md#rapid-delivery)

## コンテンツの編集 {#content}

ここでは、「**[!UICONTROL コンテンツを編集]**」ボタンから、メッセージのコンテンツを定義します。コンテンツの作成プロセスは、選択したチャネルによって異なります。

メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。


<table style="table-layout:fixed"><tr style="border: 0;">
<td><a href="../email/create-email.md"><img alt="メール" src="../channels/assets/do-not-localize/email.png"></a>
<div align="center"><a href="../email/create-email.md"><strong>メール</strong></a></div></td>
<td><a href="../sms/create-sms.md"><img alt="SMS" src="../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><a href="../sms/create-sms.md"><strong>SMS</strong></a></div></td>
<td><a href="../push/create-push.md"><img alt="プッシュ" src="../channels/assets/do-not-localize/push.png"></a>
<div align="center"><a href="../push/create-push.md"><strong>プッシュ通知</strong></a></div></td>
<td><a href="../direct-mail/create-direct-mail.md"><img alt="ダイレクトメール" src="../channels/assets/do-not-localize/direct-mail.jpg"></a>
<div align="center"><a href="../direct-mail/create-direct-mail.md"><strong>ダイレクトメール</strong></a></div></td>
</tr></table>

<table style="table-layout:fixed"><tr style="border: 0;">
<td><a href="../in-app/create-in-app.md"><img alt="アプリ内" src="../channels/assets/do-not-localize/inapp.jpg"></a>
<div align="center"><a href="../in-app/create-in-app.md"><strong>アプリ内</strong></a></div></td>
<td><a href="../web/create-web.md"><img alt="Web" src="../channels/assets/do-not-localize/web.jpg"></a>
<div align="center"><a href="../web/create-web.md"><strong>Web</strong></a></div></td>
<td><a href="../code-based/create-code-based.md"><img alt="コードベースのエクスペリエンス" src="../channels/assets/do-not-localize/code.png"></a>
<div align="center"><a href="../code-based/create-code-based.md"><strong>コードベースのエクスペリエンス</strong></a></div></td>
<td><a href="../content-card/create-content-card.md"><img alt="コンテンツカード" src="../channels/assets/do-not-localize/cards.png"></a>
<div align="center"><a href="../content-card/create-content-card.md"><strong>コンテンツカード</strong></a></div></td>
</tr></table>

コンテンツを定義したら、「**[!UICONTROL コンテンツをシミュレート]**」ボタンを使用して、CSV／JSON ファイルからアップロードした、または手動で追加したテストプロファイルやサンプル入力データを使用して、そのコンテンツをプレビューおよびテストします。[詳細情報](../content-management/preview-test.md)。キャンペーン作成画面に戻るには、左向き矢印をクリックします。

![](assets/create-campaign-design.png)

メッセージコンテンツ自体に加えて、次の設定を行うことができます。

1. （オプション）「**[!UICONTROL コンテンツ実験]**」セクションでは、「**[!UICONTROL 実験を作成]**」ボタンを使用して、どのコンテンツがより効果的かをテストできます。コンテンツ実験機能について詳しくは、[この節](../content-management/content-experiment.md)を参照してください。

1. 「**[!UICONTROL アクショントラッキング]**」セクションで、配信に対する受信者の反応を追跡するかどうかを指定します。クリック数や開封数を追跡できます。

   キャンペーンが実行されると、キャンペーンレポートからトラッキング結果にアクセスできるようになります。[キャンペーンレポートの詳細情報](../reports/campaign-global-report-cja.md)

## キャンペーンのスケジュール {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="キャンペーンスケジュール"
>abstract="デフォルトでは、キャンペーンは手動でアクティブ化すると開始され、メッセージが 1 回送信されるとすぐに終了します。メッセージを送信する特定の日付を柔軟に設定できます。さらに、繰り返しキャンペーンまたは API トリガーキャンペーンの終了日を指定できます。アクショントリガーでは、環境設定に応じてメッセージ送信頻度を設定することもできます。"

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

デフォルトでは、スケジュール済みキャンペーンは手動でアクティブ化した後に開始され、メッセージが 1 回送信された直後に終了します。

アクティブ化直後にキャンペーンを実行しない場合は、「**[!UICONTROL キャンペーン開始]**」オプションを使用して、メッセージを送信する日付を指定することができます。「**[!UICONTROL キャンペーン終了]**」オプションを使用すると、キャンペーンの実行を停止するタイミングを指定できます。

![](assets/create-campaign-schedule.png)

メール、SMS、プッシュ通知の各キャンペーンでは、キャンペーンのメッセージを送信する頻度を定義できます。これを行うには、キャンペーン作成画面にある「**[!UICONTROL アクショントリガー]**」オプションを使用して、キャンペーンの実行頻度を日単位、週単位または月単位のいずれにするかを指定します。

>[!NOTE]
>
>[!DNL Adobe Journey Optimizer] でキャンペーンをスケジュールする場合は、開始日時が目的の最初の配信に合っていることを確認します。繰り返しキャンペーンで、最初にスケジュールした時間が既に過ぎている場合、キャンペーンは繰り返しルールに従って、次に使用可能な時間スロットに繰り越されます。

## その他の設定 {#settings}

一部の設定は、キャンペーン用に選択された通信チャネルに固有のものであるか、特定のユースケースに使用されます。以下で詳しく説明します。

* メールの場合は、特定の IP ウォームアッププランのアクティベーションキャンペーンを作成できます。詳しくは、[この節](../configuration/ip-warmup-campaign.md)を参照してください。
* Web、アプリ内およびコードベースのチャネルの場合は、キャンペーンに優先度スコアを割り当てることができます。詳しくは、[この節](../conflict-prioritization/priority-scores.md)を参照してください。
* コンテンツカードキャンペーンの場合は、追加の配信ルールを有効にして、メッセージをトリガーするイベントと条件を選択できます。詳しくは、[この節](../content-card/create-content-card.md)を参照してください。
* アプリ内メッセージの場合は、「**[!UICONTROL トリガーを編集]**」ボタンを使用して、メッセージをトリガーするイベントと条件を選択できます。詳しくは、[この節](../in-app/create-in-app.md)を参照してください。

## 次の手順 {#next}

キャンペーンの設定とコンテンツの準備が整ったら、レビューしてアクティブ化できます。[詳細情報](review-activate-campaign.md)

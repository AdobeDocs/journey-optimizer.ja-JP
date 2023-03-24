---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの作成
description: Journey Optimizer でキャンペーンを作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Intermediate
keywords: 作成, Optimizer, キャンペーン, サーフェス, メッセージ
exl-id: 617d623c-e038-4b5b-a367-5254116b7815
source-git-commit: 8b1bf0b0469c1efc5194dae56ddddd9f05dbf722
workflow-type: ht
source-wordcount: '754'
ht-degree: 100%

---

# キャンペーンの作成 {#create-campaign}

>[!NOTE]
>
>新しいキャンペーンを作成する前に、サーフェスチャネル（メッセージプリセット）と Adobe Experience Platform セグメントが使用できる状態になっていることを確認します。詳しくは、以下の節を参照してください。
>
>* [チャネルサーフェスの作成](../configuration/channel-surfaces.md)
>* [セグメントの基本を学ぶ](../segment/about-segments.md)


新しいキャンペーンを作成するには、**[!UICONTROL Campaigns]** メニューにアクセスし、「**[!UICONTROL キャンペーンの作成]**」をクリックします。また、既存のライブキャンペーンを複製して新しいキャンペーンを作成することもできます。([詳細情報](modify-stop-campaign.md#duplicate))

![](assets/create-campaign.png)

## キャンペーンのタイプとチャネルを選択 {#campaigntype}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="キャンペーンのタイプ"
>abstract="送信日を指定したマーケティングメッセージには、**スケジュール型**&#x200B;タイプが最適です。ただし、パスワードのリセットやカートの放棄などのトランザクションメッセージを送信する場合は、**API トリガー**&#x200B;タイプが最適な選択肢です。"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_category"
>title="キャンペーンカテゴリ"
>abstract="カテゴリの値は、キャンペーンタイプの値に直接関連付けられます。 **マーケティング**&#x200B;カテゴリのスケジュールキャンペーンタイプとカテゴリ&#x200B;**トランザクション**&#x200B;の API トリガータイプ"

1. 「**[!UICONTROL プロパティ]**」セクションで、キャンペーンを実行する方法を指定します。次の 2 種類のキャンペーンを使用できます。

   * **[!UICONTROL スケジュール型]**：キャンペーンをすぐに実行するか、指定日に実行します。スケジュール済みキャンペーンは、**マーケティング**&#x200B;タイプのメッセージを送信することを目的としています。

   * **[!UICONTROL API トリガー]**：API 呼び出しを使用してキャンペーンを実行します。API トリガーキャンペーンは、**トランザクション**&#x200B;メッセージ、つまり、個人が実行したアクション（パスワードのリセット、カートの放棄など）に続いて送信されるメッセージを送信することを目的としています。[API を使用してキャンペーンをトリガーする方法についてはこちらを参照してください](api-triggered-campaigns.md)

1. 「**[!UICONTROL アクション]**」セクションで、メッセージの送信に使用するチャネルとチャネルサーフェスを選択します。

   サーフェスは、[システム管理者](../start/path/administrator.md)によって定義された設定です。ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。 [詳細情報](../configuration/channel-surfaces.md)。

   マーケティングキャンペーンタイプと互換性のあるチャネルサーフェスのみがドロップダウンリストに一覧表示されます。

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >プッシュ通知キャンペーンを作成している場合、**[!UICONTROL 迅速配信モード]**&#x200B;を有効にできます。これは、大量のプッシュメッセージを非常に高速に送信できる Journey Optimizer アドオンです。[詳細情報](../push/create-push.md#rapid-delivery)

1. 「**[!UICONTROL 作成]**」をクリックして、キャンペーンを作成します。

## キャンペーンのプロパティの定義 {#create}

1. キャンペーンのタイトルと説明を指定します。

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../campaigns/content-experiment.md).-->

1. カスタムまたはコアのデータ使用ラベルをキャンペーンに割り当てるには、「**[!UICONTROL アクセスを管理]**」ボタンをクリックします。 [オブジェクトレベルのアクセス制御（OLA）の詳細](../administration/object-based-access.md)

   ![](assets/create-campaign-properties.png)

## メッセージの作成 {#content}

「**[!UICONTROL アクション]**」セクションで、キャンペーンで送信するメッセージを作成します。

1. 「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、メッセージコンテンツを設定およびデザインします。

   メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。

   <table style="table-layout:fixed">
    <tr style="border: 0;">
    <td>
    <a href="../email/create-email.md">
    <img alt="リード" src="../assets/do-not-localize/email.jpg">
    </a>
    <div><a href="../email/create-email.md"><strong>メールの作成</strong>
    </div>
    <p>
    </td>
    <td>
    <a href="../push/create-push.md">
      <img alt="低頻度" src="../assets/do-not-localize/push.jpg">
    </a>
    <div>
    <a href="../push/create-push.md"><strong>プッシュ通知の作成</strong></a>
    </div>
    <p>
    </td>
    <td>
    <a href="../sms/create-sms.md">
      <img alt="検証" src="../assets/do-not-localize/sms.jpg">
    </a>
    <div>
    <a href="../sms/create-sms.md"><strong>SMS メッセージの作成</strong></a>
    </div>
    <p>
    </td>
    </tr>
    </table>

1. コンテンツを定義したら、**[!UICONTROL コンテンツをシミュレート]**&#x200B;ボタンを使用して、テストプロファイルを使用してコンテンツをプレビューおよびテストします([詳細情報](../email/preview.md))。

1. 矢印をクリックして、キャンペーン作成画面に戻ります。

   ![](assets/create-campaign-design.png)

1. 「**[!UICONTROL アクションのトラッキング]**」セクションで、受信者が配信に対する反応を追跡するかどうかを指定します。クリック数や開封数を追跡できます。

   キャンペーンが実行されると、キャンペーンレポートからトラッキング結果にアクセスできるようになります。[キャンペーンレポートについて詳しくはこちらを参照](../reports/campaign-global-report.md)

## オーディエンスを定義 {#audience}

1. ターゲットとするオーディエンスを定義します。それには、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform セグメントのリストを表示します。[セグメントについて詳しくはこちらを参照](../segment/about-segments.md)

   >[!NOTE]
   >
   >API トリガーキャンペーンの場合、オーディエンスは API 呼び出しを使用して設定する必要があります。([詳細情報](api-triggered-campaigns.md))

   「**[!UICONTROL ID 名前空間]**」フィールドで、選択したセグメントから個人を識別するために使用する名前空間を選択します。[名前空間について詳しくはこちらを参照](../event/about-creating.md#select-the-namespace)

   ![](assets/create-campaign-namespace.png)

   >[!NOTE]
   >
   >様々な ID の中から選択した ID（名前空間）を持たないセグメントに属する個人は、キャンペーンのターゲットになりません。

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

## キャンペーンのスケジュール {#schedule}

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

デフォルトでは、キャンペーンは手動でアクティブ化した後に開始され、メッセージが 1 回送信された直後に終了します。

キャンペーンのメッセージを送信する頻度を定義できます。これを行うには、キャンペーンの作成画面にある「**[!UICONTROL アクショントリガー]**」オプションを使用して、キャンペーンの実行頻度を日単位、週単位または月単位のいずれにするかを指定します。

アクティブ化直後にキャンペーンを実行しない場合は、「**[!UICONTROL キャンペーン開始]**」オプションを使用して、メッセージを送信する日時を指定することができます。「**[!UICONTROL キャンペーン終了]**」オプションを使用すると、繰り返しキャンペーンの実行を停止するタイミングを指定できます。

![](assets/create-campaign-schedule.png)

キャンペーンの準備が整ったら、キャンペーンをレビューして公開できます。 ([詳細情報](review-activate-campaign.md))

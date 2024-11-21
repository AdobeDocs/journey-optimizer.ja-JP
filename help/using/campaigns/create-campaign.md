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
source-git-commit: f9f2cd339680d0dbff1812e64c5082ca97a34771
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 68%

---

# キャンペーンの作成 {#create-campaign}

新しいキャンペーンを作成するには、**[!UICONTROL Campaigns]** メニューにアクセスし、「**[!UICONTROL キャンペーンの作成]**」をクリックします。また、既存のライブキャンペーンを複製して新しいキャンペーンを作成することもできます。([詳細情報](modify-stop-campaign.md#duplicate))

>[!NOTE]
>
>新しいキャンペーンを作成する前に、チャネル設定（メッセージサーフェス）と Adobe Experience Platform オーディエンスが使用できる状態になっていることを確認します。詳しくは、以下の節を参照してください。
>
>* [チャネル設定の作成](../configuration/channel-surfaces.md)
>* [オーディエンスの基本を学ぶ](../audience/about-audiences.md)

## キャンペーンタイプを選択 {#campaigntype}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="キャンペーンのタイプ"
>abstract="**スケジュール済みキャンペーン**&#x200B;は、即時または指定した日付に実行され、マーケティングタイプのメッセージを送信することを目的としています。**API トリガー**&#x200B;のキャンペーンは、API 呼び出しを使用して実行されます。これらは、マーケティングメッセージ（ユーザーの同意が必要なプロモーションメッセージ）またはトランザクションメッセージ（特定のコンテキストで登録解除済みのプロファイルにも送信できる非商用メッセージ）を送信することを目的としています。"

1. 実施するキャンペーンのタイプを選択します。

   * **[!UICONTROL Scheduled - Marketing]**：キャンペーンをすぐに実行するか、指定日に実行します。スケジュール済みキャンペーンは、**マーケティング**&#x200B;メッセージを送信することを目的としています。ユーザーインターフェイスから設定および実行されます。

   * **[!UICONTROL API トリガー - マーケティング／トランザクション]**：API 呼び出しを使用してキャンペーンを実行します。API トリガーキャンペーンは、**マーケティング**&#x200B;メッセージまたは&#x200B;**トランザクション**&#x200B;メッセージのいずれか、つまり、個人が実行したアクション（パスワードのリセット、買い物かごの購入など）に続いて送信されるメッセージを送信することを目的としています。[API を使用してキャンペーンをトリガーする方法についてはこちらを参照してください](api-triggered-campaigns.md)

   ![](assets/create-campaign-modal.png)

1. 「**[!UICONTROL 作成]**」をクリックして、キャンペーンを作成します。

## キャンペーンのプロパティの定義 {#create}

1. **[!UICONTROL プロパティ]** セクションで、キャンペーンの名前と説明を入力します。

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../content-management/content-experiment.md).-->

1. 「**タグ**」フィールドを使用すると、Adobe Experience Platform統合タグをキャンペーンに割り当てることができます。 これにより、キャンペーンを簡単に分類し、キャンペーンリストからの検索を改善できます。[ タグの操作方法については、こちらを参照してください ](../start/search-filter-categorize.md#tags)。

1. アクセスラベルに基づいて、このキャンペーンへのアクセスを制限できます。 アクセス制限を追加するには、このページの上部にある **[!UICONTROL アクセスを管理]** ボタンを参照します。 権限のあるラベルのみを選択してください。 [ オブジェクトレベルのアクセス制御の詳細情報 ](../administration/object-based-access.md)。

## キャンペーンオーディエンスの定義 {#audience}

オーディエンスとは、類似した行動や特性を共有する一連のユーザーです。キャンペーンのターゲットとなる母集団を定義するには、次の手順に従います。

1. 「**オーディエンス**」セクションで、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform オーディエンスのリストを表示します。オーディエンスについて詳しくは、[ この節 ](../audience/about-audiences.md) を参照してください。

1. 「**[!UICONTROL ID タイプ]**」フィールドで、選択したオーディエンスから個人を識別するために使用するキーのタイプを選択します。 既存の ID タイプを使用することも、Adobe Experience Platform ID サービスを使用して新しい ID タイプを作成することもできます。 標準 ID 名前空間の一覧については、[ このページ ](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces#standard){target="_blank"} を参照してください。

   1 つのキャンペーンで使用できる ID タイプは 1 つだけです。 様々な ID の中から選択した ID タイプを持たないセグメントに属する個人は、キャンペーンのターゲットにすることはできません。

   ![](assets/create-campaign-namespace.png)

   ID タイプと名前空間について詳しくは、[Adobe Experience Platform ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja){target="_blank"} を参照してください。

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

>[!IMPORTANT]
>
>* [オーディエンス構成](../audience/get-started-audience-orchestration.md)からのオーディエンスおよび属性は現在、Healthcare Shield または Privacy and Security Shield では使用できません。
>
>* API トリガーキャンペーンの場合、オーディエンスは API 呼び出しを使用して設定する必要があります。


## メッセージの作成とトラッキングの設定 {#content}

1. 「**[!UICONTROL アクション]**」セクションで、チャネルを選択します。

   使用可能なチャネルのリストは、ライセンスモデルによって異なります。 API トリガートランザクションキャンペーンの場合は、メール、SMS、プッシュ通知の各チャネルのみを使用できます。

1. チャネル設定を選択します。

   設定は、[システム管理者](../start/path/administrator.md)によって定義されます。ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。 [詳細情報](../configuration/channel-surfaces.md)。

   マーケティングキャンペーンタイプと互換性のあるチャネル設定のみがドロップダウンリストに一覧表示されます。

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >プッシュ通知キャンペーンを作成している場合、**[!UICONTROL 迅速配信モード]**&#x200B;を有効にできます。これは、大量のプッシュメッセージを非常に高速に送信できる Journey Optimizer アドオンです。[詳細情報](../push/create-push.md#rapid-delivery)

1. 「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、メッセージを設定およびデザインします。メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。

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

   コンテンツを定義したら、**[!UICONTROL コンテンツをシミュレート]**&#x200B;ボタンを使用して、テストプロファイルを使用してコンテンツをプレビューおよびテストします[詳細情報](../content-management/preview-test.md)。キャンペーンの作成画面に戻るには、左矢印をクリックします。

   ![](assets/create-campaign-design.png)

1. 「**[!UICONTROL コンテンツ実験]**」セクションでは、「**[!UICONTROL 実験を作成]**」ボタンを使用して、どのコンテンツがより効果的かをテストできます。 コンテンツ実験機能について詳しくは、[ この節 ](../content-management/content-experiment.md) を参照してください。

1. 「**[!UICONTROL アクションのトラッキング]**」セクションで、受信者が配信に対する反応を追跡するかどうかを指定します。クリック数や開封数を追跡できます。

   キャンペーンが実行されると、キャンペーンレポートからトラッキング結果にアクセスできるようになります。[キャンペーンレポートについて詳しくはこちらを参照](../reports/campaign-global-report-cja.md)

## キャンペーンのスケジュール {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="キャンペーンスケジュール"
>abstract="デフォルトでは、キャンペーンは手動によるアクティブ化で開始し、メッセージが 1 回送信された直後に終了します。 メッセージを送信する特定の日時を柔軟に設定できます。 さらに、繰り返しキャンペーンまたは API トリガーキャンペーンの終了日を指定できます。アクショントリガーでは、環境設定に応じてメッセージ送信頻度を設定することもできます。"

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

キャンペーンの準備が整ったら、レビューしてアクティブ化できます。 [詳細情報](review-activate-campaign.md)

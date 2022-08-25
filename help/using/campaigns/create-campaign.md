---
title: キャンペーンの作成
description: ' [!DNL Journey Optimizer] でキャンペーンを作成する方法を説明します'
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 7c4afc98-0d79-4e26-90f8-558bac037169
source-git-commit: 711fdf1dce0688d2e21d405a4e3e8777612b2f3b
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 86%

---

# キャンペーンの作成 {#create-campaign}

>[!NOTE]
>
>新しいキャンペーンを作成する前に、サーフェスチャネル（メッセージプリセット）と Adobe Experience Platform セグメントが使用できる状態になっていることを確認します。詳しくは、以下の節を参照してください。
>
>* [チャネルサーフェスの作成](../configuration/channel-surfaces.md)
>* [セグメントの基本を学ぶ](../segment/about-segments.md)


## キャンペーンの設定 {#configure}

キャンペーンの作成手順は次のとおりです。

1. **[!UICONTROL キャンペーン]**&#x200B;メニューにアクセスし、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

   ![](assets/create-campaign.png)

   >[!NOTE]
   >
   >また、既存のライブキャンペーンを複製して新しいキャンペーンを作成することもできます。[詳細情報](modify-stop-campaign.md#duplicate) <!-- check if only live campaigns-->

<!--1. In the **[!UICONTROL Properties]** section, specify when you want to execute the campaign:

    * **[!UICONTROL Scheduled]**: execute the campaign immediately or on a specified date. Scheduled campaigns are aimed at sending **marketing** type messages.
    * **[!UICONTROL API-triggered]**: execute the campaign using an API call. API-triggered campaigns are aimed at sending **transactional** messages, i.e. messages sent out following an action performed by an individual: password reset, card abandonment etc. [Learn how to trigger a campaign using APIs](api-triggered-campaigns.md)-->

1. 「**[!UICONTROL アクション]**」セクションで、メッセージの送信に使用するチャネルとチャネルサーフェスを選択し、「**[!UICONTROL 作成]**」をクリックします。

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >キャンペーンタイプ（マーケティングまたはトランザクション）と互換性のあるチャネルサーフェスのみがドロップダウンリストに一覧表示されます。

1. キャンペーンのタイトルと説明を指定します。

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../campaigns/content-experiment.md).-->

1. 「**[!UICONTROL アクション]**」セクションで、キャンペーンで送信するメッセージを設定します。

   1. 「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、メッセージコンテンツを設定およびデザインします。 [メッセージの詳細を表示](../messages/get-started-content.md)

      >[!NOTE]
      >
      >この **[!UICONTROL コンテンツをシミュレート]** ボタンをクリックすると、テストプロファイルを使用して、コンテンツをプレビューおよびテストできます。 [詳細情報](../design/preview.md)

   1. コンテンツの準備が整ったら、矢印をクリックしてキャンペーンの作成画面に戻ります。

      ![](assets/create-campaign-design.png)

   1. 「**[!UICONTROL アクショントラッキング]**」セクションで、配信に対する受信者の反応をトラッキングするかどうかを指定します。

      キャンペーンが実行されると、キャンペーンレポートからトラッキング結果にアクセスできるようになります。[キャンペーンレポートについて詳しくはこちらを参照](../reports/campaign-global-report.md)

1. ターゲットとするオーディエンスを定義します。それには、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform セグメントのリストを表示します。[セグメントについて詳しくはこちらを参照](../segment/about-segments.md)

   <!-- NOTE For API-triggered campaigns, the audience needs to be set via API call. [Learn more](api-triggered-campaigns.md)-->

   「**[!UICONTROL ID 名前空間]**」フィールドで、選択したセグメントから個人を識別するために使用する名前空間を選択します。[名前空間について詳しくはこちらを参照](../event/about-creating.md#select-the-namespace)

   ![](assets/create-campaign-namespace.png)

   >[!NOTE]
   >
   >様々な ID の中から選択した ID（名前空間）を持たないセグメントに属する個人は、キャンペーンのターゲットになりません。

1. キャンペーンの開始日と終了日を設定します。デフォルトでは、キャンペーンは手動でアクティブ化すると開始し、メッセージが 1 回送信されるとすぐに終了するように設定されています。

1. さらに、キャンペーンで設定されたアクションの実行頻度を指定できます。

   <!-- NOTE For API-triggered campaigns, scheduling at a specific date and time with recurrence is not available as action is triggered via API. However, start and end date are relevant to ensure that, if an API call is made prior of after the window, then those get errored.-->

   ![](assets/create-campaign-schedule.png)

<!--1. If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

キャンペーンの準備が整ったら、レビューして公開できます（[キャンペーンのレビューとアクティブ化](#review-activate)を参照）。

## キャンペーンのレビューとアクティブ化 {#review-activate}

キャンペーンを設定したら、アクティブ化する前にそのパラメーターとコンテンツをレビューする必要があります。それには、次の手順に従います。

1. キャンペーンの設定画面で、「**[!UICONTROL アクティブ化するレビュー]**」をクリックして、キャンペーンの概要を表示します。

   概要では、必要に応じてキャンペーンを変更し、パラメーターが正しくないか、または見つからないかを確認できます。

   >[!IMPORTANT]
   >
   >エラーが発生した場合は、キャンペーンをアクティブ化できません。続行する前にエラーを解決します。

   ![](assets/create-campaign-alerts.png)

1. キャンペーンが正しく設定されていることを確認してから、「**[!UICONTROL アクティブ化]**」をクリックします。

   ![](assets/create-campaign-review.png)

1. キャンペーンがアクティブ化され、ステータスが&#x200B;**[!UICONTROL ライブ]**（開始日を指定した場合は&#x200B;**[!UICONTROL スケジュール済み]**）になります。[キャンペーンのステータスについて詳しくはこちらを参照](get-started-with-campaigns.md#statuses)。キャンペーンで設定されたメッセージは、すぐに実行されるか、指定日に実行されます。

   >[!NOTE]
   >
   >この **[!UICONTROL 完了]** ステータスは、キャンペーンがアクティブ化されてから 3 日後、または繰り返し実行されている場合はキャンペーンの終了日に自動的に割り当てられます。
   >
   >終了日が指定されていない場合、キャンペーンのステータスは「ライブ」のままになります。 変更するには、キャンペーンを手動で停止する必要があります。 [キャンペーンの停止方法についてはこちらを参照](modify-stop-campaign.md)

1. キャンペーンがアクティブ化されると、キャンペーンを開いて、いつでもその情報を確認できます。概要では、ターゲットプロファイルの数と、配信されたアクションおよび失敗したアクションの数に関する統計情報を取得できます。

   「**[!UICONTROL レポート]**」ボタンをクリックして、専用レポートでさらに統計情報を取得することもできます。[詳細情報](../reports/campaign-global-report.md)

   ![](assets/create-campaign-summary.png)

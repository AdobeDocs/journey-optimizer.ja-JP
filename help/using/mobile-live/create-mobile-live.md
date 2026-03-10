---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティメッセージの作成
description: Journey Optimizer でライブアクティビティを作成する方法について説明します
topic: Content Management
role: User
level: Beginner
exl-id: 9864a136-e129-4279-bb09-081b72f584df
source-git-commit: c1a2e098b31769945221701a075b7f9f688b274f
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 66%

---

# ライブアクティビティの作成 {#create-mobile-live}

モバイル設定を指定し、Adobe Experience Platform Mobile SDK を実装したら、Journey Optimizer でライブアクティビティの作成を開始できます。

1. **[!UICONTROL キャンペーン]**&#x200B;メニューにアクセスし、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

1. **API トリガー**&#x200B;キャンペーンタイプを選択します。

   * オーディエンスベースのキャンペーンには、「**API トリガーマーケティング**」を選択します

   * 個々のキャンペーンには、「**API トリガートランザクション**」を選択します。

   >[!IMPORTANT]
   >
   > **API トリガートランザクション**&#x200B;には、「**[!UICONTROL 高スループット]**」オプションを有効にしないでください。

   ![](assets/create-live-1.png)

1. 「**[!UICONTROL プロパティ]**」セクションで、キャンペーンの「**[!UICONTROL タイトル]**」と「**[!UICONTROL 説明]**」を編集します。

1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL ライブアクティビティ]**」を選択し、新しい設定を選択または作成します。

   ライブアクティビティの設定について詳しくは、[このページ](mobile-live-configuration.md)を参照してください。

   ![](assets/create-live-2.png)

1. 「**[!UICONTROL 実験を作成]**」をクリックしてコンテンツ実験の設定を開始し、パフォーマンスを測定してターゲットオーディエンスに最適なオプションを特定するための処理を作成します。[詳細情報](../content-management/content-experiment.md)

1. 「**[!UICONTROL オーディエンス]**」タブから、**[!UICONTROL ID タイプ]**&#x200B;を選択します [詳細情報](../audience/about-audiences.md)

   >[!NOTE]
   >
   >**API トリガーマーケティング** キャンペーンの場合は、API ペイロードから APN channelID サブスクリプションを確認する前に、最初のセグメント化として機能する既存のオーディエンスを選択できます。

1. キャンペーンは、特定の日付に実行するか、繰り返し頻度で実行するように設計されています。キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/create-campaign.md#schedule)を参照してください。

1. 設定が完了したら、「**[!UICONTROL レビューしてアクティブ化]**」をクリックし、「**[!UICONTROL アクティブ化]**」をクリックします。

1. キャンペーンがアクティブ化されたら、提供された **cURL リクエスト** をライブアクティビティの開始、更新または終了イベントをトリガーするためのテンプレートとして使用します。 実行前に、特定のデータでサンプルペイロードを更新します。

   また、ペイロードに含める&#x200B;**[!UICONTROL キャンペーン ID]** 識別子もコピーします。

   ➡️ OAuth トークンや API キーを含む認証要件について詳しくは、[API トリガーキャンペーンドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/messaging/)を参照してください。

   ![](assets/create-live-3.png)

   +++ 単一のユースケースのペイロードの例（API トリガートランザクションキャンペーン）

   このペイロードの例は、**API トリガートランザクション** キャンペーンタイプを使用した個々のキャンペーン用です。 次のペイロード例のフィールドのほとんどは必須で、`requestId`、`dismissal-date`、`alert` のみがオプションです。

   ```json
   {
       "requestId": "your-request-id",
       "campaignId": "your-campaign-id",
       "recipients": [
   {
       "type": "aep",
       "userId": "testemail@gmail.com",
       "namespace": "email",
       "context": {
        "requestPayload": {
       "aps": {
       "content-available": 1,
       "timestamp": 1756984054,              // current epoch time
       "dismissal-date": 1756984084,         // optional – auto remove when event="end"
       "event": "update",                    // start | update | end
   
       // Fields from FoodDeliveryLiveActivityAttributes
       "content-state": {
         "orderStatus": "Delivered"
       },
   
       "attributes-type": "FoodDeliveryLiveActivityAttributes",
       "attributes": {
         "restaurantName": "Pizza",
         "liveActivityData": {
           "liveActivityID": "orderId1"       // customer reference ID
         }
       },
   
       "alert": {
         "title": "Order Delivered!",
         "body": "Your pizza has arrived."
       }
     }
   }
   }
   }
   ]
   }
   ```

   +++

   +++ ブロードキャストのユースケースのペイロードの例（API トリガーマーケティングキャンペーン）

   このペイロードの例は、**API トリガーマーケティング** キャンペーンタイプを使用したオーディエンスベースのキャンペーンの場合です。

   ```json
   {
       "requestId": "123400000",
       "campaignId": "d32e6f6c-56df-4a98-a2c0-6db6008f8f32",
       "audience": {
           "id": "508f9416-52d0-4898-ba47-08baaa22e9c7"
       },
       "context": {
           "requestPayload": {
               "aps": {
                   "input-push-channel": "V+8UslywEfAAAOq9SbTrLg==",  //apns-channel-id
                   "content-available": 1,
                   "timestamp": 1770808339,
                   "event": "update",   // start | update | end
   
                   // Fields from GameScoreLiveActivityAttributes
                   "content-state": {
                       "homeTeamScore": 33,
                       "awayTeamScore": 49,
                       "statusText": "Wingdom keeps scoring!"
                   },
                   "attributes-type": "GameScoreLiveActivityAttributes",
                   "attributes": {
                       "liveActivityData": {
                           "channelID": "V+8UslywEfAAAOq9SbTrLg=="   //apns-channel-id, must match the "input-push-channel" value
                       }
                   },
                   "alert": {
                       "title": "This is the title for game",
                       "body": "This is the body for body"
                   }
               }
           }
       }
   }
   ```

   +++

ライブアクティビティをデザインしたら、[ビルトインのレポート](../reports/campaign-global-report-cja-activity.md)を使用してライブアクティビティの影響の測定を追跡できます。

>[!TIP]
>
>ライブアクティビティが期待どおりに表示または更新されない場合は、[&#x200B; ライブアクティビティのトラブルシューティング &#x200B;](troubleshoot-mobile-live.md) の手順に従ったデバッグガイダンスを参照してください。

## チュートリアルビデオ

iOS ライブアクティビティをAdobe Journey Optimizerと連携して設定し、iPhoneのロック画面と Dynamic Island でリッチなリアルタイム更新を提供する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3479865?captions=jpn)

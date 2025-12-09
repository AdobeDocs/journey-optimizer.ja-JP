---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティメッセージの作成
description: Journey Optimizer でライブアクティビティを作成する方法について説明します
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: bfd36dddb5795cd8b6eeb164f70b6cf3fdcb5750
workflow-type: ht
source-wordcount: '317'
ht-degree: 100%

---

# ライブアクティビティの作成 {#create-mobile-live}

>[!BEGINSHADEBOX]

* [ライブアクティビティの基本を学ぶ](get-started-mobile-live.md)
* [ライブアクティビティの設定](mobile-live-configuration.md)
* [Adobe Experience Platform Mobile SDK とのライブアクティビティ統合](mobile-live-configuration-sdk.md)
* **[ライブアクティビティの作成](create-mobile-live.md)**
* [よくある質問](mobile-live-faq.md)
* [ライブアクティビティキャンペーンレポート](../reports/campaign-global-report-cja-activity.md)

>[!ENDSHADEBOX]

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

1. キャンペーンは、特定の日付に実行するか、繰り返し頻度で実行するように設計されています。キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/create-campaign.md#schedule)を参照してください。

1. 設定が完了したら、「**[!UICONTROL レビューしてアクティブ化]**」をクリックし、「**[!UICONTROL アクティブ化]**」をクリックします。

1. キャンペーンをアクティブ化したら、指定された **cURL リクエスト**&#x200B;をテンプレートとして使用して、ライブアクティビティの開始、更新、終了イベントをトリガーします。実行前に、特定のデータでサンプルペイロードを更新します。

   また、ペイロードに含める&#x200B;**[!UICONTROL キャンペーン ID]** 識別子もコピーします。

   ➡️ OAuth トークンや API キーを含む認証要件について詳しくは、[API トリガーキャンペーンドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/messaging/)を参照してください。

   ![](assets/create-live-3.png)

   +++ 個々のペイロードの例

   次のペイロード例のフィールドのほとんどは必須で、`requestId`、`dismissal-date`、`alert` のみがオプションです。

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

ライブアクティビティをデザインしたら、[ビルトインのレポート](../reports/campaign-global-report-cja-activity.md)を使用してライブアクティビティの影響の測定を追跡できます。

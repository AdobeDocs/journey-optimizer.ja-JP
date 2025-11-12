---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティメッセージの作成
description: Journey Optimizerでライブアクティビティを作成する方法を説明します
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 20%

---

# ライブアクティビティの作成 {#create-mobile-live}

>[!BEGINSHADEBOX]

* [ライブアクティビティの基本を学ぶ](get-started-mobile-live.md)
* [ライブアクティビティ設定](mobile-live-configuration.md)
* [Adobe Experience Platform Mobile SDKとライブアクティビティの統合](mobile-live-configuration-sdk.md)
* **[ライブアクティビティの作成](create-mobile-live.md)**
* [よくある質問](mobile-live-faq.md)
* [ライブアクティビティキャンペーンレポート](../reports/campaign-global-report-cja-activity.md)

>[!ENDSHADEBOX]

モバイル設定を行い、Adobe Experience Platform mobile SDKを実装したら、Journey Optimizerでライブアクティビティの作成を開始できます。

1. **[!UICONTROL キャンペーン]**&#x200B;メニューにアクセスし、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

1. **API トリガー** キャンペーンタイプを選択します。

   * オーディエンスベースのキャンペーン用に「**API トリガーマーケティング**」を選択します

   * 個々のキャンペーンに対して、「**API トリガートランザクション**」を選択します。

   >[!IMPORTANT]
   >
   > **API トリガートランザクション** では、「**[!UICONTROL 高スループット]**」オプションを有効にしないでください。


   ![](assets/create-live-1.png)

1. 「**[!UICONTROL プロパティ]**」セクションで、キャンペーンの「**[!UICONTROL タイトル]**」と「**[!UICONTROL 説明]**」を編集します。

1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL ライブアクティビティ]** を選択し、新しい設定を選択または作成します。

   ライブアクティビティ設定について詳しくは、[ このページ ](mobile-live-configuration.md) を参照してください。

   ![](assets/create-live-2.png)

1. 「**[!UICONTROL 実験を作成]**」をクリックしてコンテンツ実験の設定を開始し、パフォーマンスを測定してターゲットオーディエンスに最適なオプションを特定するための処理を作成します。[詳細情報](../content-management/content-experiment.md)

1. 「**[!UICONTROL オーディエンス]**」タブから、**[!UICONTROL ID タイプ]**[ 詳細情報 ](../audience/about-audiences.md) を選択します。

1. キャンペーンは、特定の日付に実行するか、繰り返し頻度で実行するように設計されています。キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/create-campaign.md#schedule)を参照してください。

1. 設定が完了したら、「**[!UICONTROL アクティブ化するレビュー]**」をクリックし、「**[!UICONTROL アクティブ化]**」をクリックします。

1. キャンペーンがアクティブ化されたら、提供された **cURL リクエスト** をライブアクティビティの開始、更新または終了イベントをトリガーするためのテンプレートとして使用します。 実行前に、特定のデータでサンプルペイロードを更新します。

   また、**[!UICONTROL キャンペーン ID]** 識別子もコピーして、ペイロードに含めてください。

   ➡️ OAuth トークンや API キーなどの認証要件については、[API トリガーキャンペーンのドキュメント ](https://developer.adobe.com/journey-optimizer-apis/references/messaging/) を参照してください。

   ![](assets/create-live-3.png)

   +++ 個々のペイロードの例

   次のペイロードの例に記載されているフィールドのほとんどは必須であり、`requestId`、`dismissal-date`、`alert` のみがオプションです。

       ```json
       {
       &quot;requestId&quot;: &quot;your-request-id&quot;,
       &quot;campaignId&quot;: &quot;your-campaign-id&quot;,
       &quot;recipients&quot;: [
       {
       &quot;type&quot;: &quot;aep&quot;,
       &quot;userId&quot;: &quot;testemail@gmail.com&quot;,
       &quot;namespace&quot;: &quot;email&quot;,
       &quot;context&quot;: {
       &quot;requestPayload&quot;: {
       &quot;aps&quot;: {
       &quot;content-available&quot;:1,
       &quot;timestamp&quot;:1756984054,              //現在のエポック時間 
       &quot;demission-date&quot;: 1756984084,         // オプション - event=&quot;end&quot;
 の場合に自動削除       &quot;event&quot;: &quot;update&quot;,                    //開始 |更新 |終了 
       
   FoodDeliveryLiveActivityAttributes の     // フィールド 
       &quot;content-state&quot;: {
       &quot;orderStatus&quot;: &quot;配信済み&quot;
       },
       
       &quot;attributes-type&quot;: &quot;FoodDeliveryLiveActivityAttributes&quot;,
       &quot;attributes&quot;: {
       &quot;restaurantName&quot;: &quot;ピザ&quot;,
       &quot;liveActivityData&quot;: {
       &quot;liveActivityID&quot;: &quot;orderId1&quot;       //顧客参照 ID
       }
       },
       
       &quot;アラート&quot;: {
       &quot;title&quot;: &quot;Order Delivered!&quot;,
        「body」:「あなたのピザが届きました」 
       }
       }
       }
       }
       }
       ]
       }
       ```
   +++

ライブアクティビティを設計した後、[ ビルトインレポート ](../reports/campaign-global-report-cja-activity.md) を使用して、ライブアクティビティの影響を測定して追跡できます。

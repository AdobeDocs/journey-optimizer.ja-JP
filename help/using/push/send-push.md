---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知の確認と送信
description: Journey Optimizer でプッシュ通知を確認し送信する方法を学ぶ
feature: Push
topic: Content Management
role: User
level: Beginner
exl-id: aad4e08a-3369-454d-9e32-974347a3b393
TQID: https://experienceleague.adobe.com/QXJ9G3btsn7ZEwSB2Bm0uGt89gsh8D7SnNZ-Vw2muXM
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: f8d2e9f0-69c9-40cd-890f-71336c8dfff7id: c96d2aa5-76a2-443d-8d23-5de95577c909
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 28eeed0d2b5dc3054c57004ead01de32151ab743
workflow-type: tm+mt
source-wordcount: 411
ht-degree: 78%

---

# プッシュ通知の確認と送信 {#send-push}

>[!BEGINSHADEBOX]

**このページ：** Adobe Journey Optimizerでプッシュ通知をプレビュー、検証、および送信する方法について説明します。

>[!ENDSHADEBOX]

## プッシュ通知のプレビュー {#preview-push}

メッセージコンテンツを定義したら、次のいずれかのシミュレーション方法を使用してコンテンツをプレビューできます。

* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックして、サンプル入力データまたはAI自動生成を使用してコンテンツのバリエーションをテストします。 [コンテンツバリエーションのシミュレート方法を学ぶ](../test-approve/simulate-sample-input.md)
* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、ドロップダウンから「**[!UICONTROL コンテンツをシミュレート（AEP プロファイル）]**」を選択して、テストプロファイルでプレビューします。 次に、コンテンツをプレビューするデバイスのタイプを選択できます：**[!UICONTROL iOS]**、**[!UICONTROL Android]**、または&#x200B;**[!UICONTROL Web]**。

![](assets/push_preview_3.png)

コンテンツをプレビューおよびテストする方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

## プッシュ通知の検証 {#push-validate}

エディターの上部セクションでアラートを確認する必要があります。 単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。 発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

* **警告**&#x200B;は、レコメンデーションとベストプラクティスを指します。

* **エラー**（例えば次のようなもの）が解決されない限り、ジャーニーのテストやアクティブ化はできません。

   * **[!UICONTROL メッセージのプッシュバージョンが空です]**：このエラーは、プッシュ通知の本文またはタイトルがない場合に表示されます。 プッシュ通知コンテンツを定義する方法については、[この節](create-push.md)で説明します。

   * **[!UICONTROL 設定が存在しません]**：選択した設定がメッセージの作成後に削除された場合は、メッセージを使用できません。 このエラーが発生した場合は、メッセージ&#x200B;**[!UICONTROL プロパティ]**&#x200B;で別の設定を選択します。 チャネル設定について詳しくは、[この節](../configuration/channel-surfaces.md)を参照してください。

   * **[!UICONTROL プッシュの iOS / Android ペイロードが 4KB の制限を超えています]**：プッシュ通知のサイズは、4KB を超えることはできません。 この制限を守るために、画像や絵文字の使用を減らすようにしてください。 プッシュ通知コンテンツの管理方法については、[この節](../push/create-push.md)を参照してください。

  ![](assets/push_alert.png)


>[!NOTE]
>
> 配信品質を高めるには、必ずプロバイダーがサポートする形式の電話番号を使用する必要があります。 例えば、Twilio と Sinch は E.164 形式の電話番号のみをサポートしています。

## プッシュ通知の送信{#push-send}

>[!IMPORTANT]
>
> キャンペーンが承認ポリシーの対象となっている場合、プッシュ通知を送信できるようにするには、承認をリクエストする必要があります。 [詳細情報](../test-approve/gs-approval.md)

プッシュメッセージの準備が整ったら、[ジャーニー](../building-journeys/journey-gs.md)または[キャンペーン](../campaigns/create-campaign.md)の設定を完了して送信します。

**関連トピック**

* [モバイル用プッシュチャネルの設定](push-configuration.md)
* [Web用プッシュチャネルの設定](push-configuration-web.md)
* [プッシュ通知レポート](../reports/journey-global-report-cja-push.md)
* [プッシュ通知の作成](create-push.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journey-action.md)
* [キャンペーンへのメッセージの追加](../campaigns/create-campaign.md)


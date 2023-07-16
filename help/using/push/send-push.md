---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知のプレビューとテスト
description: Journey Optimizer でプッシュ通知をプレビューしテストする方法を説明します
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: aad4e08a-3369-454d-9e32-974347a3b393
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: ht
source-wordcount: '380'
ht-degree: 100%

---

# プッシュ通知のプレビューとテスト {#send-push}

## プッシュ通知のプレビュー {#preview-push}

メッセージコンテンツを定義したら、テストプロファイルを使用してプレビューとテストを行うことができます。パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを使用して確認できます。

1. 「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

1. 「**[!UICONTROL テストプロファイルを管理]**」をクリックして、テストプロファイルを追加します。

1. 「**[!UICONTROL ID 名前空間]**」フィールドと「**[!UICONTROL ID 値]**」フィールドを使用して、テストプロファイルを検索します。そのあと、「**[!UICONTROL プロファイルを追加]**」をクリックします。

   ![](assets/push_preview_1.png)

1. テストプロファイルを選択したら、**[!UICONTROL テストプロファイルを追加]**&#x200B;ウィンドウを閉じます。

1. **プレビューとテスト**&#x200B;ウィンドウから、テストプロファイルデータをメッセージコンテンツに追加します。

   コンテンツをプレビューするデバイスの種類を **[!UICONTROL iOS]** または **[!UICONTROL Android]** から選択します。

   ![](assets/push_preview_3.png)

## プッシュ通知の検証 {#push-validate}


エディターの上部セクションでアラートを確認する必要があります。単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

* **警告**&#x200B;は、推奨事項やベストプラクティスを示しています。

* **エラー**（例えば次のようなもの）が解決されない限り、ジャーニーのテストやアクティブ化はできません。

   * **[!UICONTROL メッセージのプッシュバージョンが空です]**：このエラーは、プッシュ通知の本文またはタイトルがない場合に表示されます。プッシュ通知コンテンツを定義する方法については、[この節](create-push.md)で説明します。

   * **[!UICONTROL サーフェスが存在しません]**：選択したサーフェスがメッセージの作成後に削除された場合は、メッセージを使用できません。このエラーが発生した場合は、メッセージの&#x200B;**[!UICONTROL プロパティ]**&#x200B;で別のサーフェスを選択します。チャネルサーフェスについて詳しくは、[この節](../configuration/channel-surfaces.md)を参照してください。

   * **[!UICONTROL プッシュの iOS / Android ペイロードが 4KB の制限を超えています]**：プッシュ通知のサイズは、4KB を超えることはできません。この制限を守るために、画像や絵文字の使用を減らすようにしてください。プッシュ通知コンテンツの管理方法については、[この節](../push/create-push.md)を参照してください。

  ![](assets/push_alert.png)


>[!NOTE]
>
> 配信品質を高めるには、必ずプロバイダーがサポートする形式の電話番号を使用する必要があります。例えば、Twilio と Sinch は E.164 形式の電話番号のみをサポートしています。

## プッシュ通知の送信{#push-send}

プッシュメッセージの準備が整ったら、[ジャーニー](../building-journeys/journey-gs.md)または[キャンペーン](../campaigns/create-campaign.md)の設定を完了して送信します。

**関連トピック**

* [プッシュチャネルの設定](push-configuration.md)
* [プッシュ通知レポート](../reports/journey-global-report.md#push-global)
* [プッシュ通知の作成](create-push.md)
* [ジャーニーへのメッセージの追加](../building-journeys/journeys-message.md)
* [キャンペーンへのメッセージの追加](../campaigns/create-campaign.md)


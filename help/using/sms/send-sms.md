---
solution: Journey Optimizer
product: journey optimizer
title: SMS メッセージをプレビューしてテストします
description: Journey Optimizer で SMS メッセージをプレビューおよびテストする方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: 81ab92022329788c1feea24c7a621ef154d33422
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 53%

---

# SMS メッセージをプレビューしてテストします {#send-sms}

## SMS をプレビュー {#preview-sms}

メッセージコンテンツを定義したら、テストプロファイルを使用してプレビューとテストを行うことができます。パーソナライズされたコンテンツを挿入した場合は、このコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを使用して確認できます。

1. 「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

1. 「**[!UICONTROL テストプロファイルを管理]**」をクリックして、テストプロファイルを追加します。

1. 「**[!UICONTROL ID 名前空間]**」フィールドと「**[!UICONTROL ID 値]**」フィールドを使用して、テストプロファイルを検索します。そのあと、「**[!UICONTROL プロファイルを追加]**」をクリックします。

   ![](assets/sms_preview_3.png)

1. テストプロファイルを選択したら、**[!UICONTROL テストプロファイルを追加]**&#x200B;ウィンドウを閉じます。

1. 次の **プレビューとテスト** ウィンドウで、テストプロファイルデータがメッセージコンテンツに追加されます。

   ![](assets/sms_preview_2.png)


## SMS を検証{#sms-validate}

エディターの上部のセクションでアラートを確認する必要があります。 単純な警告もあれば、メッセージの送信を妨げる可能性もあります。 次の 2 種類のアラートが発生する可能性があります。警告とエラー。

* **警告**&#x200B;は、推奨奨事項とベストプラクティスを表します。例えば、SMS メッセージが空の場合に警告メッセージが表示されます。

* **エラー** ジャーニーが解決されていない限り、ジャーニーをテストまたはアクティブ化したり、キャンペーンをパブリッシュしたりすることはできません。 例えば、件名行が見つからない場合に警告するエラーメッセージが表示されます。

![](assets/sms-alert-button.png)

>[!NOTE]
>
> 配信品質を向上させるには、プロバイダーがサポートする形式で電話番号を使用します。 例えば、Twilio と Sinch は E.164 形式の電話番号のみをサポートしています。

## SMS を送信{#sms-send}

SMS メッセージの準備が整ったら、[ジャーニー](../building-journeys/journey-gs.md)または[キャンペーン](../campaigns/create-campaign.md)の設定を完了して送信します。

**関連トピック**

* [SMS チャネルの設定](sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [SMS メッセージの作成](create-sms.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)

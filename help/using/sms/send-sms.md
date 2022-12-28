---
solution: Journey Optimizer
product: journey optimizer
title: SMS メッセージのプレビュー
description: Journey Optimizer で SMS メッセージをプレビューおよびテストする方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 100%

---

# SMS メッセージの送信 {#send-sms}

## SMS メッセージのプレビュー {#preview-sms}

メッセージコンテンツを定義したら、テストプロファイルを使用してプレビューとテストを行うことができます。パーソナライズされたコンテンツを挿入してある場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを利用して確認できます。

1. 「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

1. 「**[!UICONTROL テストプロファイルを管理]**」をクリックして、テストプロファイルを追加します。

1. 「**[!UICONTROL ID 名前空間]**」フィールドと「**[!UICONTROL ID 値]**」フィールドを使用して、テストプロファイルを検索します。そのあと、「**[!UICONTROL プロファイルを追加]**」をクリックします。

   ![](assets/sms_preview_3.png)

1. テストプロファイルを選択したら、**[!UICONTROL テストプロファイルを追加]**&#x200B;ウィンドウを閉じます。

   ![](assets/sms_preview_1.png)

1. プレビューおよびテストウィンドウでは、メッセージコンテンツでテストプロファイルデータが活用されます。

   例えば、この SMS メッセージの場合、メッセージコンテンツは両方ともパーソナライズされます。

   ![](assets/sms_preview_2.png)

## SMS を検証{#sms-preview}

>[!NOTE]
>
> 配信品質を高めるには、必ずプロバイダーがサポートする形式の電話番号を使用する必要があります。例えば、Twilio と Sinch は E.164 形式の電話番号のみをサポートしています。

また、エディターの上部セクションでアラートを確認します。単純な警告もありますが、メッセージの使用を妨げる可能性のある警告もあります。次の 2 種類のアラートが発生する可能性があります。

* **警告**&#x200B;は、推奨奨事項とベストプラクティスを表します。例えば、SMS メッセージが空の場合はメッセージが表示されます。

* **エラー**&#x200B;が解決されない限り、ジャーニーのテストやアクティブ化はできません。例えば、件名がないことを警告するメッセージが表示されます。

![](assets/sms-alert-button.png)

SMS メッセージの準備が整ったら、[ジャーニー](../building-journeys/journey-gs.md)または[キャンペーン](../campaigns/create-campaign.md)の設定を完了して送信します。

**関連トピック**

* [SMS チャネルの設定](sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [SMS メッセージの作成](create-sms.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)

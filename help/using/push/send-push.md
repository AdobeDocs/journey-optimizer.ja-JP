---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知の送信
description: Journey Optimizerでプッシュ通知をプレビューし、テストする方法を説明します
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: aad4e08a-3369-454d-9e32-974347a3b393
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 63%

---

# プッシュ通知の送信 {#send-push}

## プッシュ通知をプレビューする {#preview-push}

メッセージコンテンツを定義したら、テストプロファイルを使用してプレビューとテストを行うことができます。パーソナライズされたコンテンツを挿入してある場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを利用して確認できます。

1. クリック **[!UICONTROL コンテンツをシミュレート]**.

1. クリック **[!UICONTROL テストプロファイルの管理]** をクリックして、テストプロファイルを追加します。

1. テストプロファイルを見つけるには、 **[!UICONTROL ID 名前空間]** および **[!UICONTROL ID 値]** フィールド。 次に、「 **[!UICONTROL プロファイルを追加]**.

   ![](assets/push_preview_1.png)

1. 上記と同じ手順を適用して、テストプロファイルを選択し、

   ![](assets/push_preview_2.png)

1. プッシュのプレビューでは、テストプロファイルデータをメッセージコンテンツに使用します。

   コンテンツをプレビューするデバイスの種類を選択します。 **[!UICONTROL iOS]** または **[!UICONTROL Android]**.

   ![](assets/push_preview_3.png)

## プッシュ通知を検証 {#push-validate}

>[!NOTE]
>
> 配信品質を高めるには、必ずプロバイダーがサポートする形式の電話番号を使用する必要があります。例えば、Twilio と Sinch は E.164 形式の電話番号のみをサポートしています。

また、エディターの上部セクションでアラートを確認します。単純な警告もありますが、メッセージの使用を妨げる可能性のある警告もあります。次の 2 種類のアラートが発生する可能性があります。

* **警告**&#x200B;は、推奨奨事項とベストプラクティスを表します。

* **エラー** は、次のように解決されていない限り、ジャーニーのテストやアクティブ化を防ぎます。

   * **[!UICONTROL メッセージのプッシュバージョンが空です]**：このエラーは、プッシュ通知の本文またはタイトルがない場合に表示されます。プッシュ通知コンテンツを定義する方法については、[この節](create-push.md)で説明します。

   * **[!UICONTROL サーフェスが存在しません]**:メッセージの作成後に選択したサーフェスを削除した場合は、メッセージを使用できません。 このエラーが発生した場合は、メッセージの&#x200B;**[!UICONTROL プロパティ]**&#x200B;で別のサーフェスを選択します。チャネルサーフェスについて詳しくは、[この節](../configuration/channel-surfaces.md)を参照してください。

   * **[!UICONTROL プッシュの iOS / Android ペイロードが 4KB の制限を超えています]**：プッシュ通知のサイズは、4KB を超えることはできません。この制限を守るために、画像や絵文字の使用を減らすようにしてください。プッシュ通知コンテンツの管理方法については、[この節](../push/create-push.md)を参照してください。

![](assets/push_alert.png)

プッシュ通知の準備が整ったら、 [ジャーニー](../building-journeys/journey-gs.md) または [campaign](../campaigns/create-campaign.md) 送信する

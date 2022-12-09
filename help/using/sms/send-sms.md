---
solution: Journey Optimizer
product: journey optimizer
title: SMS メッセージのプレビュー
description: このような場合は、旅オプティマイザーで SMS メッセージのプレビューとテストを行う方法について学習します。
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# SMS メッセージを送信します。 {#send-sms}

## SMS メッセージのプレビュー {#preview-sms}

作成したメッセージコンテンツについては、テストプロファイルを使用してプレビューとテストを行うことができます。 パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージにどのように表示されるかを確認できます。これによりテストプロファイルデータが活用されます。

1. をクリック **[!UICONTROL Simulate content]** します。

1. テストプロファイルを追加するには、をクリック **[!UICONTROL Manage test profiles]** します。

1. And **[!UICONTROL Identity value]** フィールドを使用 **[!UICONTROL Identity namespace]** してテストプロファイルを検索します。次に、をクリック **[!UICONTROL Add profile]** します。

   ![](assets/sms_preview_3.png)

1. テストプロファイルを選択したら、ウィンドウを閉じる **[!UICONTROL Add test profile]** ことができます。

   ![](assets/sms_preview_1.png)

1. 「プレビュー &amp; テスト」ウィンドウでは、メッセージコンテンツでテストプロファイルデータが活用されています。

   例えば、この SMS メッセージについては、両方のメッセージコンテンツが個人用になっています。

   ![](assets/sms_preview_2.png)

## SMS の検証{#sms-preview}

>[!NOTE]
>
> Deliverability を改善するには、プロバイダーによってサポートされている形式の電話番号を常に使用してください。 例えば、Twilio では、E.i 形式の電話番号のみがサポートされています。

また、エディターの上半分に表示されるアラートも確認する必要があります。  この中には簡単な警告が表示されているものもありますが、メッセージを使用しないようにすることもできます。 アラートは、次の2種類の方法で発生する可能性があります。

* **警告** は「推奨事項」および「ベストプラクティス」を参照してください。 例えば、SMS メッセージが空の場合は、メッセージが表示されます。

* **エラーが発生** すると、解決されていない限り、そのような旅のテストやアクティブ化はできなくなります。 例えば、件名が入力されていないことを示す警告メッセージが表示されます。

![](assets/sms-alert-button.png)

SMS メッセージの準備ができたら、移動または [ キャンペーン ](../campaigns/create-campaign.md) の ](../building-journeys/journey-gs.md) [ 設定を完了して送信します。

**関連トピック**

* [SMS チャネルの設定](sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [SMS メッセージの作成](create-sms.md)
* [メッセージの追加](../building-journeys/journeys-message.md)

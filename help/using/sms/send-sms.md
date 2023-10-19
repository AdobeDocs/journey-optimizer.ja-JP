---
solution: Journey Optimizer
product: journey optimizer
title: SMS メッセージを確認し、テストします
description: Journey Optimizerで SMS メッセージを確認して送信する方法を説明します
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: 27447578dad6bd2612989d79cd0dc8ddbe78d629
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 69%

---

# SMS メッセージを確認して送信する {#send-sms}

## SMS のプレビュー {#preview-sms}

メッセージの内容を定義したら、テストプロファイルを使用して、その内容をプレビューできます。 パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを使用して確認できます。

これをおこなうには、 **[!UICONTROL コンテンツをシミュレート]** 次に、テストプロファイルを追加し、テストプロファイルデータを使用してメッセージを確認します。

![](assets/sms_preview_2.png)

テストプロファイルの選択およびコンテンツのプレビュー方法に関する詳細な情報は、 [コンテンツ管理](../content-management/preview-test.md) 」セクションに入力します。

## SMS の検証{#sms-validate}

エディターの上部セクションでアラートを確認する必要があります。単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

* **警告**&#x200B;は、レコメンデーションとベストプラクティスを指します。例えば、SMS メッセージが空の場合は警告メッセージが表示されます。

* **エラー**&#x200B;の場合は、それが解決されない限り、ジャーニーのテストやアクティブ化またはキャンペーンの公開はできません。例えば、件名がない場合は、それを警告するエラーメッセージが表示されます。

![](assets/sms-alert-button.png)

>[!NOTE]
>
> 配信品質を高めるには、プロバイダーでサポートされている形式の電話番号を使用します。 例えば、Twilio と Sinch では E.164 形式の電話番号のみをサポートしています。

## SMS の送信{#sms-send}

SMS メッセージの準備が整ったら、[ジャーニー](../building-journeys/journey-gs.md)または[キャンペーン](../campaigns/create-campaign.md)の設定を完了して送信します。

**関連トピック**

* [SMS チャネルの設定](sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [SMS メッセージの作成](create-sms.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)

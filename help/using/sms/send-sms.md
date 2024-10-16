---
solution: Journey Optimizer
product: journey optimizer
title: テキストメッセージの確認およびテスト
description: Journey Optimizer でテキストメッセージを確認および送信する方法を学ぶ
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 86%

---

# テキストメッセージ（SMS／MMS）の確認および送信{#send-sms}

## テキストメッセージのプレビュー {#preview-sms}

メッセージコンテンツを定義したら、テストプロファイルを使用してコンテンツをプレビューできます。パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを使用して確認できます。

これを行うには、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルを追加し、テストプロファイルデータを使用してメッセージを確認します。

![](assets/sms_preview_2.png)

テストプロファイルの選択およびコンテンツのプレビュー方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

## コンテンツの検証 {#sms-validate}

エディターの上部セクションでアラートを確認する必要があります。単純な警告もありますが、メッセージの送信を妨げる可能性のある警告もあります。発生する可能性のあるアラートには、警告とエラーの 2 種類があります。

![](assets/sms-alert-button.png)

* **警告**&#x200B;は、レコメンデーションとベストプラクティスを指します。例えば、テキストメッセージが空の場合は警告メッセージが表示されます。

* **エラー**&#x200B;の場合は、それが解決されない限り、ジャーニーのテストやアクティブ化またはキャンペーンの公開はできません。例えば、件名がない場合は、それを警告するエラーメッセージが表示されます。


>[!NOTE]
>
> 配信品質を高めるには、プロバイダーでサポートされている形式の電話番号を使用します。 例えば、Twilio と Sinch では E.164 形式の電話番号のみをサポートしています。

## テキストメッセージの送信 {#sms-send}

>[!IMPORTANT]
>
>9 月のリリース以降、新しいキャンペーンとジャーニーのアクティブ化エクスペリエンスを使用すると、承認プロセス全体を管理し、キャンペーンとジャーニーが運用開始前に適切な関係者によって徹底的にレビューおよび承認されるようになります。 この機能は、限定提供（LA）で利用できます。 [詳細情報](../test-approve/gs-approval.md)

テキストメッセージの準備が整ったら、[ジャーニー](../building-journeys/journey-gs.md)または[キャンペーン](../campaigns/create-campaign.md)の設定を完了して送信します。

**関連トピック**

* [SMS チャネルの設定](sms-configuration.md)
* [SMS／MMS レポート](../reports/journey-global-report-cja-sms.md)
* [テキストメッセージの作成](create-sms.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)

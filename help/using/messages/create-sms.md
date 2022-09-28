---
title: SMS メッセージの作成
description: Journey Optimizer で SMS メッセージを作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 711fdf1dce0688d2e21d405a4e3e8777612b2f3b
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 100%

---

# SMS メッセージの作成 {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS の作成"
>abstract="テキストメッセージを追加し、式エディターを使用してパーソナライズを開始します。"

[!DNL Journey Optimizer] を使用すると、顧客のモバイルデバイスにテキストメッセージを送信できます。SMS エディターで、テキスト形式のメッセージの作成、パーソナライズおよびプレビューを行うことができます。

SMS 配信を作成するには、次の手順を実行します。

* **ジャーニーの場合**：ジャーニーに SMS アクティビティを追加し、基本設定を定義したら、右側の&#x200B;**[!UICONTROL アクション : SMS]** パネルを使用して SMS メッセージのコンテンツを作成します。

   ジャーニーの設定方法について詳しくは、この[ページ](../building-journeys/journey-gs.md)を参照してください。

* **キャンペーンの場合**：キャンペーンを作成したら、アクションとして SMS を選択し、基本設定を定義します。

   キャンペーンの設定方法について詳しくは、この[ページ](../campaigns/create-campaign.md#configure)を参照してください。

SMS メッセージを初めて作成する場合は、SMS チャネルが設定されていることを確認してください。[詳細情報](../configuration/sms-configuration.md)。

## SMS コンテンツの定義{#sms-content}

SMS メッセージのパーソナライズを開始するには、次の手順に従います。

1. 「**[!UICONTROL メッセージ]**」フィールドをクリックして、式エディターを開きます。

   ![](assets/sms-content.png)

1. 式エディターを使用してコンテンツを定義します。任意の属性を使用して、プロファイル名や市区町村など、コンテンツをパーソナライズできます。式エディターでのパーソナライゼーションについて詳しくは、[この節](../personalization/personalize.md)を参照してください。

1. 「**[!UICONTROL 保存]**」をクリックして、プレビューでメッセージを確認します。

   ![](assets/sms-content-preview.png)

## SMS を検証{#sms-preview}

>[!NOTE]
>
> 配信品質を高めるには、必ずプロバイダーがサポートする形式の電話番号を使用する必要があります。例えば、Twilio と Sinch は E.164 形式の電話番号のみをサポートしています。

メッセージのコンテンツを定義したら、テストプロファイルを使用してコンテンツのプレビューとテストを行います。[パーソナライズされたコンテンツ](../personalization/personalize.md)を挿入してある場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを利用して確認できます。

モバイルデバイスでの SMS メッセージの表示を視覚化するには、「**[!UICONTROL コンテンツをシミュレート]**」タブをクリックします。コンテンツのシミュレーションについて詳しくは、[この節](../design/preview.md)を参照してください。

また、エディターの上部セクションでアラートを確認します。単純な警告もありますが、メッセージの使用を妨げる可能性のある警告もあります。詳しくは、[この節](alerts.md)を参照してください。

![](assets/sms-alert-button.png)


## オプトインとオプトアウト{#sms-opt-in-out}

すべてのマーケティングメッセージに対して、受信者が簡単に購読解除できる方法を SMS に含める必要があります。購読を解除すると、プロファイルは、今後のマーケティングメッセージのオーディエンスから自動的に削除されます。トランザクションメッセージに対しては、購読解除リンクの追加は必須ではありません。

SMS 受信者は、オプトインおよびオプトアウトのキーワードを使用して返信できます。Adobe Journey Optimizer は、業界標準および規制に従って、受信メッセージで START、STOP、および UNSTOP のキーワードを自動的に処理します。これらのキーワードトリガーは、SMS プロバイダーからの自動標準返信です。

SMS に対するネイティブ受信キーワードのサポート（開始、停止、停止解除）の仕組みについて詳しくは、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)

<!--
## How-to video

Learn how to configure, author, and include SMS messaging into your customer journeys.

>[!VIDEO](https://video.tv.adobe.com/v/344460?quality=12)
-->
**関連トピック**

* [SMS チャネルの設定](../configuration/sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [新規メッセージの作成](get-started-content.md)
* [ジャーニーへのメッセージの追加](../building-journeys/journeys-message.md)

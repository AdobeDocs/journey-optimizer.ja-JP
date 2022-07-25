---
title: SMS メッセージの作成
description: Journey Optimizer で SMS メッセージを作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 62%

---

# SMS メッセージの作成 {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS の作成"
>abstract="テキストメッセージを追加し、式エディターを使用してパーソナライズを開始します。"

用途 [!DNL Journey Optimizer] を使用して、モバイルデバイスで顧客にテキストメッセージを送信します。 SMS エディターで、テキスト形式のメッセージの作成、パーソナライズ、プレビューをおこなうことができます。

一度 [SMS を追加しました](get-started-content.md) ジャーニーのアクティビティと定義された基本設定を使用するには、 **[!UICONTROL アクション：SMS]** SMS メッセージのコンテンツを作成する右側のウィンドウ

>[!AVAILABILITY]
>
>SMS チャネルは現在、一連の組織でのみ使用できます（使用制限があります）。 詳しくは、アドビ担当者にお問い合わせください。

![](assets/sms-edit-content.png)

SMS メッセージを初めて作成する場合は、SMS チャネルが設定されていることを確認してください。[詳細情報](../configuration/sms-configuration.md)。

## SMS コンテンツの定義{#sms-content}

SMS メッセージのパーソナライズを開始するには、次の手順に従います。

1. 次をクリック： **[!UICONTROL メッセージ]** 「 」フィールドをクリックして、式エディターを開きます。

   ![](assets/sms-content.png)

1. 式エディターを使用して、コンテンツを定義します。 任意の属性を使用して、プロファイル名や市区町村など、コンテンツをパーソナライズできます。パーソナライゼーションについて詳しくは、 [この節](../personalization/personalize.md).

1. クリック **[!UICONTROL 保存]** メッセージをプレビューで確認します。

   ![](assets/sms-content-preview.png)


## SMS を検証{#sms-preview}

メッセージのコンテンツを定義したら、テストプロファイルを使用してコンテンツのプレビューとテストを行います。[パーソナライズされたコンテンツ](../personalization/personalize.md)を挿入してある場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを利用して確認できます。

モバイルデバイスでの SMS メッセージの表示を視覚化するには、 **[!UICONTROL コンテンツをシミュレート]** タブをクリックします。 コンテンツシミュレーションの詳細については、 [この節](../design/preview.md).

また、エディターの上部セクションでアラートを確認する必要があります。  単純な警告もありますが、メッセージの使用を妨げる可能性もあります。 詳しくは、[この節](alerts.md)を参照してください。

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

---
title: SMS メッセージの作成
description: Journey Optimizer で SMS メッセージを作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 630b8ef5a140709161b24256083b2104be5b6121
workflow-type: ht
source-wordcount: '427'
ht-degree: 100%

---

# SMS メッセージの作成 {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS の作成"
>abstract="テキストメッセージを追加し、式エディターを使用してパーソナライズを開始します。"

[メッセージを作成](get-started-content.md)したら、「**[!UICONTROL SMS]**」タブを使用して、SMS メッセージの設定とコンテンツを定義します。


>[!AVAILABILITY]
>
>SMS チャネルは現在、一連の組織でのみ使用できます（使用制限があります）。 詳しくは、アドビ担当者にお問い合わせください。

![](assets/sms_1.png)

SMS メッセージを初めて作成する場合は、SMS チャネルが設定されていることを確認してください。[詳細情報](../configuration/sms-configuration.md)。

## SMS コンテンツの定義{#sms-content}

SMS メッセージのパーソナライズを開始するには、次の手順に従います。

1. 「**[!UICONTROL テキストメッセージの追加]**」フィールドをクリックして、式エディターを開きます。

   ![](assets/sms_3.png)

1. 式エディターを使用してコンテンツを定義します。任意の属性を使用して、プロファイル名や市区町村など、コンテンツをパーソナライズできます。[この節](../personalization/personalize.md)で、式エディターでのパーソナライゼーションについて詳しく説明します

   >[!NOTE]
   >
   > SMS メッセージには、スペースや改行を含めて、最大 160 文字まで指定できます。

   ![](assets/sms_2.png)

1. メッセージの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。

## SMS を検証{#sms-preview}

メッセージのコンテンツを定義したら、テストプロファイルを使用してコンテンツのプレビューとテストを行います。[パーソナライズされたコンテンツ](../personalization/personalize.md)を挿入してある場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを利用して確認できます。

モバイルデバイスでの SMS メッセージの表示を視覚化するには、「**[!UICONTROL プレビュー]**」タブをクリックします。

詳しくは、[この節](../design/preview.md)を参照してください。

## SMS を公開する {#sms-publish}

メッセージの準備が整ったら、「**[!UICONTROL 公開]**」ボタンを使用してメッセージを公開し、実行できる状態にできます。このアクションにより、ジャーニーの次回の実行に使用される新しいバージョンのメッセージが公開されます。

ジャーニーで SMS メッセージを使用できるようになりました。[ジャーニーの作成方法を説明します](../building-journeys/journey-gs.md)。

## オプトインとオプトアウト{#sms-opt-in-out}

すべてのマーケティングメッセージに対して、受信者が簡単に購読解除できる方法を SMS に含める必要があります。購読を解除すると、プロファイルは、今後のマーケティングメッセージのオーディエンスから自動的に削除されます。トランザクションメッセージに対しては、購読解除リンクの追加は必須ではありません。

SMS 受信者は、オプトインおよびオプトアウトのキーワードを使用して返信できます。Adobe Journey Optimizer は、業界標準および規制に従って、受信メッセージで START、STOP、および UNSTOP のキーワードを自動的に処理します。これらのキーワードトリガーは、SMS プロバイダーからの自動標準返信です。

SMS に対するネイティブ受信キーワードのサポート（開始、停止、停止解除）の仕組みについて詳しくは、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)

## ハウツービデオ

SMS メッセージを設定、作成、およびカスタマージャーニーに含める方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/344460?quality=12)

**関連トピック**

* [SMS チャネルの設定](../configuration/sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [新規メッセージの作成](get-started-content.md)
* [ジャーニーへのメッセージの追加](../building-journeys/journeys-message.md)

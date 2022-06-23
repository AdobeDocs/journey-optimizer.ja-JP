---
title: SMS メッセージの作成
description: Journey Optimizer で SMS メッセージを作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 47b1c2832f82a5c168cd03f1d1b43a9223c945b3
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 36%

---

# SMS メッセージの作成 {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS の作成"
>abstract="テキストメッセージを追加し、式エディターを使用してパーソナライズを開始します。"

一度 [メッセージを作成しました](get-started-content.md)、 **[!UICONTROL SMS]** タブを使用して、SMS メッセージの設定とコンテンツを定義します。


>[!AVAILABILITY]
>
>SMS チャネルは現在、一連の組織でのみ使用できます（使用が制限されています）。 詳しくは、Adobe担当者にお問い合わせください。

![](assets/sms_1.png)

SMS メッセージを初めて作成する場合は、SMS チャネルが設定されていることを確認してください。 [詳細情報](../configuration/sms-configuration.md)。

## SMS コンテンツを定義{#sms-content}

SMS メッセージのパーソナライズを開始するには、次の手順に従います。

1. 「**[!UICONTROL テキストメッセージの追加]**」フィールドをクリックして、式エディターを開きます。

   ![](assets/sms_3.png)

1. 式エディターを使用してコンテンツを定義します。 任意の属性を使用して、プロファイル名や市区町村など、コンテンツをパーソナライズできます。 [この節で、](../personalization/personalize.md)式エディターでのパーソナライゼーションについて詳しく説明します

   >[!NOTE]
   >
   > SMS メッセージには、スペースや改行を含めて、最大 160 文字まで指定できます。

   ![](assets/sms_2.png)

1. クリック **[!UICONTROL 保存]** メッセージの準備が整ったら、

## SMS を検証{#sms-preview}

メッセージのコンテンツを定義したら、テストプロファイルを使用してコンテンツのプレビューとテストを行います。以下を [パーソナライズされたコンテンツ](../personalization/personalize.md)では、テストプロファイルデータを活用して、このコンテンツがメッセージにどのように表示されるかを確認できます。

モバイルデバイスでの SMS メッセージの表示を視覚化するには、 **[!UICONTROL プレビュー]** タブをクリックします。

詳しくは、[この節](../design/preview.md)を参照してください。

## SMS を公開する {#sms-publish}

メッセージの準備が整ったら、「**[!UICONTROL 公開]**」ボタンを使用してメッセージを公開し、実行可能な状態にできます。このアクションは、ジャーニーでの次回の実行に使用されるメッセージの新しいバージョンをパブリッシュします。

ジャーニーで SMS メッセージを使用できるようになりました。[ジャーニーの作成方法を説明します](../building-journeys/journey-gs.md)。

## オプトインとオプトアウト{#sms-opt-in-out}

すべてのマーケティングメッセージで、受信者が簡単に購読解除できる方法を SMS に含める必要があります。 購読を解除すると、プロファイルは、今後のマーケティングメッセージのオーディエンスから自動的に削除されます。 トランザクションメッセージに対しては、購読解除リンクの追加は必須ではありません。

SMS 受信者は、オプトインおよびオプトアウトのキーワードを使用して返信できます。 Adobe Journey Optimizerは、業界標準および規制に従って、受信メッセージで次のキーワードを自動的に処理します。START、STOP、および UNSTOP。 これらのキーワードトリガーは、SMS プロバイダーからの自動標準返信です。

**関連トピック**

* [SMS チャネルの設定](../configuration/sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [新規メッセージの作成](get-started-content.md)
* [ジャーニーへのメッセージの追加](../building-journeys/journeys-message.md)

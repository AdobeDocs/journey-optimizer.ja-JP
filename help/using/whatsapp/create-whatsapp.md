---
solution: Journey Optimizer
product: journey optimizer
title: WhatsApp メッセージの作成
description: Journey Optimizer で WhatsApp メッセージを作成する方法について説明します
feature: Whatsapp
topic: Content Management
role: User
level: Beginner
exl-id: cac6f675-59e0-431d-8c20-f24ef16d7bf2
source-git-commit: 03699215020770d0636c77e9d197990ab5da0975
workflow-type: ht
source-wordcount: '842'
ht-degree: 100%

---


# WhatsApp メッセージの作成 {#create-whatsapp}

Adobe Journey Optimizer を使用すると、WhatsApp で魅力的なメッセージをデザインして送信できます。ジャーニーまたはキャンペーンに WhatsApp アクションを追加し、以下に説明するようにメッセージコンテンツを作成するだけです。また、Adobe Journey Optimizer を使用すると、WhatsApp メッセージを送信する前にテストして、完全なレンダリング、正確なパーソナライゼーション、すべての設定の適切な設定を確保することもできます。

Journey Optimizer では、アウトバウンドメッセージ要素のみがサポートされています。

+++ 詳しくは、サポートされているメッセージ要素とコールトゥアクションを参照してください

WhatsApp では、次のメッセージタイプがサポートされています。

| メッセージ機能 | 説明 |
|-|-|
| ヘッダー | メッセージの本文の上に表示されるオプションのテキスト。 |
| テキスト | パラメーターを通じて動的コンテンツをサポートします。 |
| 画像（JPEG、PNG） | 8 ビット RGB または RGBA 形式で、サイズが 5 MB 未満である必要があります。 |
| ビデオ | 3GPP または MP4、16 MB 未満、URL 経由でホストされている必要があります。 |
| オーディオ | 応答メッセージにのみ使用できます。AAC、AMR、MP3、MP4 オーディオまたは OGG 形式で、URL でホストされ、16 MB 未満である必要があります。 |
| ドキュメント | 100 MB 未満で、URL でホストされ、.txt、.xls／.xlsx、.doc／.docx、.ppt／.pptx または .pdf のいずれかの形式である必要があります。 |
| 本文 | パラメーターを通じて動的コンテンツをサポートします。 |
| フッターテキスト | パラメーターを通じて動的コンテンツをサポートします。 |

WhatsApp メッセージでは、次のコールトゥアクションオプションを使用できます。

| コールトゥアクション | 説明 |
|-|-|
| Web サイトに訪問 | 変数パラメーターを含むボタンは、1 つのみ許可されます。 |
| WhatsApp で通話 | メッセージから直接、指定された電話番号との WhatsApp チャットを開くボタンを提供します。 |
| 電話番号に通話 | ユーザーがタップすると、指定された番号への通話を開始するボタンを提供します。 |

+++

## WhatsApp メッセージを追加 {#create-whatsapp-journey-campaign}

キャンペーンまたはジャーニーに WhatsApp メッセージを追加する方法については、以下のタブを参照してください。

>[!BEGINTABS]

>[!TAB ジャーニーへの WhatsApp メッセージの追加]

1. ジャーニーを開き、パレットの「**アクション**」セクションから **WhatsApp アクティビティ**&#x200B;をドラッグ＆ドロップします。

   ![](assets/whatsapp-create-jo.png)

1. メッセージに関する基本情報（ラベル、説明、カテゴリ）を入力したあと、使用するメッセージ設定を選択します。

   ジャーニーの設定方法について詳しくは、[このページ](../building-journeys/journey-gs.md)を参照してください。

   **[!UICONTROL 設定]**&#x200B;フィールドはデフォルトで、ユーザーがチャネルで最後に使用した設定で事前入力されます。

これで、以下に説明するように、「**[!UICONTROL コンテンツを編集]**」ボタンから WhatsApp メッセージのコンテンツのデザインを開始できます。

>[!TAB キャンペーンへの WhatsApp メッセージの追加]

1. **[!UICONTROL キャンペーン]**&#x200B;メニューにアクセスし、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

1. キャンペーンのタイプとして&#x200B;**スケジュール済み - マーケティング**&#x200B;を選択します。

1. 「**[!UICONTROL プロパティ]**」セクションで、キャンペーンの「**[!UICONTROL タイトル]**」と「**[!UICONTROL 説明]**」を編集します。

1. 「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform オーディエンスのリストからターゲットオーディエンスを定義します。[詳細情報](../audience/about-audiences.md)

1. 「**[!UICONTROL ID 名前空間]**」フィールドで、選択したオーディエンスから個人を識別するために使用する名前空間を選択します。[詳細情報](../event/about-creating.md#select-the-namespace)

1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL WhatsApp]**」を選択し、新しい設定を選択または作成します。

   WhatsApp 設定について詳しくは、[このページ](whatsapp-configuration.md)を参照してください。

   ![](assets/whatsapp-campaign-1.png)

1. 「**[!UICONTROL 実験を作成]**」をクリックしてコンテンツ実験の設定を開始し、パフォーマンスを測定してターゲットオーディエンスに最適なオプションを特定するための処理を作成します。[詳細情報](../content-management/content-experiment.md)

1. 「**[!UICONTROL アクションのトラッキング]**」セクションで、WhatsApp メッセージ内のリンクのクリック数を追跡するかどうかを指定します。

1. キャンペーンは、特定の日付に実行するか、繰り返し頻度で実行するように設計されています。キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/create-campaign.md#schedule)を参照してください。

1. **[!UICONTROL アクショントリガー]**&#x200B;メニューから、WhatsApp メッセージの「**[!UICONTROL 頻度]**」を選択します。

   * 1 回
   * 毎日
   * 毎週
   * 月

これで、以下に説明するように、「**[!UICONTROL コンテンツを編集]**」ボタンから WhatsApp メッセージのコンテンツのデザインを開始できます。

>[!ENDTABS]

## WhatsApp コンテンツの定義{#whatsapp-content}

>[!BEGINSHADEBOX]

Journey Optimizer で WhatsApp メッセージをデザインする前に、まず Meta でテンプレートを作成およびデザインする必要があります。[詳細情報](https://www.facebook.com/business/help/2055875911147364?id=2129163877102343)

WhatsApp テンプレートは、Journey Optimizer で使用する前に、まず Meta で承認される必要があります。この処理には通常数時間かかりますが、最大 24 時間かかる場合があります。[詳細情報](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#approval-process)

>[!ENDSHADEBOX]

1. ジャーニーまたはキャンペーンの設定画面で、「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、WhatsApp メッセージのコンテンツを設定します。

<!--
1. Select **[!UICONTROL Template message]**.
-->

1. 「**テンプレートカテゴリ**」を選択します。

   * マーケティング
   * ユーティリティ
   * 認証

   [テンプレートカテゴリの詳細情報](https://developers.facebook.com/docs/whatsapp/updates-to-pricing/new-template-guidelines/#template-category-guidelines)

   ![](assets/whatsapp-design-1.png)

1. **WhatsApp テンプレート**&#x200B;ドロップダウンから、Meta でデザインした、作成済みのテンプレートを選択します。

   [WhatsApp テンプレート作成方法の詳細情報](https://www.facebook.com/business/help/2055875911147364?id=2129163877102343)

   ![](assets/whatsapp-design-2.png)

1. 「**[!UICONTROL 画像 URL]**」フィールドに、テンプレート内のプレースホルダーを置き換えるメディア URL を追加します。Meta のテンプレートメディアは、プレースホルダーのみです。画像、オーディオ、ビデオを正しく表示するには、Adobe Experience Manager またはその他のソースからの外部 URL を使用する必要があります。

   ![](assets/whatsapp-design-3.png)

1. パーソナライゼーションエディターを使用して、テンプレートにパーソナライゼーションを追加します。プロファイル名や市区町村など、任意の属性を使用できます。

   [パーソナライゼーション](../personalization/personalize.md)について詳しくは、次のページを参照してください。

   ![](assets/whatsapp-design-4.png)

1. 「**[!UICONTROL コンテンツをシミュレート]**」ボタンを使用して、WhatsApp メッセージコンテンツ、短縮 URL、パーソナライズされたコンテンツをプレビューします。[詳細情報](send-whatsapp.md)

テストを実行してコンテンツを検証したら、オーディエンスに [WhatsApp メッセージを送信](send-whatsapp.md)し、[レポート](../reports/campaign-global-report-cja.md)を通じてパフォーマンスを監視できます。

<!--
* **[!UICONTROL Template message]**: Predefined message imported from Meta into Journey Optimizer. These are intended for sending notifications, alerts, or updates to your customers.

* **[!UICONTROL Response message]**: Message created in Journey Optimizer and sent in reply to customer queries or interactions.

>[!BEGINTABS]

>[!TAB Template message]

1. From the journey or campaign configuration screen, click the **[!UICONTROL Edit content]** button to configure the WhatsApp message content.

1. Select **[!UICONTROL Template message]**.

1. Choose your Template category. [Learn more](https://developers.facebook.com/docs/WhatsApp/updates-to-pricing/new-template-guidelines/)

1. From the **WhatsApp template** drop-down, select your previously created template designed in Meta.

1. Use the personalization editor to define content, add personalization and dynamic content. You can use any attribute, such as the profile name or city for example. You can also define conditional rules. Browse to the following pages to learn more about [personalization](../personalization/personalize.md) and [dynamic content](../personalization/get-started-dynamic-content.md) in the personalization editor.

1. Use the **[!UICONTROL Simulate content]** button to preview your WhatsApp message content, shortened URLs, and personalized content. [Learn more](send-whatsapp.md)

Once you have performed your tests and validated the content, you can send your WhatsApp message to your audience. These steps are detailed on [this page](send-whatsapp.md)

>[!TAB Response message]

1. From the journey or campaign configuration screen, click the **[!UICONTROL Edit content]** button to configure the WhatsApp message content.

1. Select **[!UICONTROL Response message]**.

1. Enter your text in the **[!UICONTROL Body]** field.

1. Use the personalization editor to define content, add personalization and dynamic content. You can use any attribute, such as the profile name or city for example. You can also define conditional rules. Browse to the following pages to learn more about [personalization](../personalization/personalize.md) and [dynamic content](../personalization/get-started-dynamic-content.md) in the personalization editor.

1. Use the **[!UICONTROL Simulate content]** button to preview your WhatsApp message content, shortened URLs, and personalized content. [Learn more](send-whatsapp.md)

Once you have performed your tests and validated the content, you can send your WhatsApp message to your audience. These steps are detailed on [this page](send-whatsapp.md)

>[!ENDTABS]
-->


## チュートリアルビデオ {#video}

次のビデオでは、Adobe Journey Optimizer を使用して複数ステップの WhatsApp ジャーニーを作成する方法について説明します。

+++ こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3470283/?learn=on&captions=jpn")

+++

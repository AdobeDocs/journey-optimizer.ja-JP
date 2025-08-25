---
solution: Journey Optimizer
product: journey optimizer
title: Dynamic Media
description: Journey Optimizer での Dynamic Media の使用
topic: Content Management
role: User
level: Beginner
exl-id: 3e777cc5-a935-4e68-9de7-60b241e78f63
source-git-commit: 1b4ab451ed9e2315ffe4850c6ab4b8ad20223ac3
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 99%

---

# Dynamic Media の操作 {#aem-dynamic}

## Dynamic Media の基本を学ぶ {#gs-aem-dynamic}

アセットセレクターで Dynamic Media がサポートされるようになり、承認済み Dynamic Media レンディションを Journey Optimizer 内でシームレスに選択して使用できるようになりました。Adobe Experience Manager のアセットに行った変更は Journey Optimizer コンテンツに即座に反映されるので、手動での更新が必要なく、常に最新バージョンが使用されます。

この統合は、Dynamic Media Manager as a Cloud Service を使用している顧客のみが使用できます。

Adobe Experience Manager as a Cloud Service の Dynamic Media について詳しくは、[Experience Manager ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media){target="_blank"}を参照してください。

>[!AVAILABILITY]
>
>ヘルスケアのお客様の場合、統合は Journey Optimizer Healthcare Shield および Adobe Experience Manager Enhanced Security アドオン製品のライセンスを取得した場合にのみ有効になります。


## Dynamic Media の追加と管理 {#dynamic-media}


Adobe Experience Manager as a Cloud Service の Dynamic Media を Journey Optimizer コンテンツに直接挿入すると、任意の画面やブラウザー向けにコンテンツを強化および最適化できます。その後、必要に応じてサイズ変更、切り抜き、拡大などの調整を行うことができます。


>[!IMPORTANT]
>
>OpenAPI 搭載 Dynamic Media が Adobe Experience Manager as a Cloud Service で有効になっていることを確認します。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media-open-apis/dynamic-media-open-apis-overview#enable-dynamic-media-open-apis){target="_blank"}

Dynamic Media と Adobe Journey Optimizer の統合は、Dynamic Media [Scene7 モード](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/dynamic/config-dms7){target="_blank"}と [OpenAPI 搭載](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media-open-apis/dynamic-media-open-apis-overview){target="_blank"}の両方で使用できます。

>[!AVAILABILITY]
>
>古いバージョンの Outlook（2016 を含む）では、Dynamic Media を使用したコンテンツのレンダリングはサポートされていません。アドビでは、互換性を向上させるよう、永続的な修正に積極的に取り組んでいます。その間、次のガイドラインを適用します。
>
>* Dynamic Media Scene7 URL の場合：画像 URL に `?bfc=on` を追加します。これにより、自動形式ネゴシエーションが可能になり、クライアントの機能に基づいて最も互換性のある画像形式が配信されます。
>
>* Open API 搭載 Dynamic Media の場合：`.avif` 形式を使用します。この形式には、必要に応じて互換性のある形式を配信するビルトインのフォールバックメカニズムが含まれます。
>

HTML コンテンツに Adobe Experience Manager アセットを追加するには、次の手順に従います。

1. **[!UICONTROL HTML コンポーネント]**&#x200B;をコンテンツにドラッグ＆ドロップします。

1. 「**[!UICONTROL ソースコードを表示]**」を選択します。

   ![](assets/dynamic-media-1.png)

1. **[!UICONTROL HTML を編集]**&#x200B;メニューで、「**[!UICONTROL アセット]**」に移動し、「**[!UICONTROL アセットセレクターを開く]**」をクリックします。

   または、アセットの URL をコピー＆ペーストすることもできます。

   ![](assets/dynamic-media-2.png)

1. AEM アセットを参照し、コンテンツに追加するアセットを選択します。

1. アセットの要件に合わせて、必要に応じて画像パラメーター（高さ、幅、回転、反転、明るさ、色相など）を調整します。

   URL に追加できる画像パラメーターの包括的なリストについて詳しくは、[Experience Manager ドキュメント](https://experienceleague.adobe.com/ja/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/c-command-reference){target="_blank"}を参照してください。

   ![](assets/dynamic-media-3.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

これで、コンテンツに Dynamic Media が含まれるようになりました。Experience Manager で行った更新は、Journey Optimizer に自動的に表示されます。

## テキストオーバーレイのパーソナライズ {#text-overlay}

既存のテキストオーバーレイを選択した新しいテキストに置き換えることで、Dynamic Media を簡単にカスタマイズし、シームレスな更新とパーソナライゼーションが可能になります。

例えば、実験機能を使用すると、既存のテキストオーバーレイを処理ごとに異なるテキストに置き換えて更新し、メッセージを開いた際に各プロファイルに合わせてカスタマイズできます。

![](assets/dynamic-media-layout-1.png)

>[!AVAILABILITY]
>
>**テキストオーバーレイのパーソナライゼーション**&#x200B;は、Dynamic Media [Scene7 モード](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/dynamic/config-dms7){target="_blank"}でのみ使用できます。ヘルスケアのお客様は Scene7 モードにアクセスできないので、コンテンツは画像の Journey Optimizer バイナリコピーを使用してレンダリングされます。例外については、Adobeの担当者にお問い合わせください。

テキストオーバーレイをパーソナライズするには、次の手順に従います。

1. **[!UICONTROL HTML コンポーネント]**&#x200B;をコンテンツにドラッグ＆ドロップします。

1. 「**[!UICONTROL ソースコードを表示]**」を選択します。

1. **[!UICONTROL HTML を編集]**&#x200B;メニューで、「**[!UICONTROL アセット]**」、「**[!UICONTROL アセットセレクターを開く]**」の順にアクセスします。

   または、アセットの URL をコピー＆ペーストすることもできます。

1. AEM アセットを参照して、コンテンツに追加するアセットを選択します。

1. オーバーレイを目的のテキストに置き換えます。

   ![](assets/do-not-localize/dynamic_media_layout.gif)

1. 画像パラメーターを更新します。

   * **レイヤー**：テキストを配置するベース要素を入力します。
   * **サイズ**：テキストブロックのサイズを更新します。
   * **テキスト属性**：テキストフォントのサイズを調整します。
   * **位置**：画像内のテキストの位置を設定します。

   >[!WARNING]
   >
   >Dynamic Media を更新するには、レイヤーパラメーターが必要です。

   ![](assets/dynamic-media-layout-2.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

これで、コンテンツに更新したテキストオーバーレイが含まれるようになりました。

![](assets/dynamic-media-layout-3.png)

## Dynamic Media テンプレートの追加と管理 {#dynamic-media-template}

Journey Optimizer で Dynamic Media テンプレートを簡単に追加し、必要に応じてメディアコンテンツを更新できます。これで、メディアにパーソナライゼーションフィールドを組み込むことができるようになり、Journey Optimizer 内でよりカスタマイズされた魅力的なコンテンツを作成できるようになりました。

詳しくは、[Dynamic Media テンプレート](https://experienceleague.adobe.com/ja/docs/dynamic-media-classic/using/template-basics/quick-start-template-basics){target="_blank"}を参照してください。


>[!AVAILABILITY]
>
>**Dynamic Media テンプレート**&#x200B;は、Dynamic Media [Scene7 モード](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/dynamic/config-dms7)でのみ使用できます。ヘルスケアのお客様は Scene7 モードにアクセスできないので、コンテンツはレンダリングされません。例外について詳しくは、Experience Manager サポートにお問い合わせください。


### 画像コンポーネントの使用 {#image-component}

画像コンポーネントを使用して、動的テンプレートをコンテンツに直接挿入できます。

1. キャンペーンまたはジャーニーを開き、コンテンツにアクセスします。

1. **画像コンポーネント**&#x200B;をレイアウトにドラッグ＆ドロップします。

   画像コンポーネントについて詳しくは、[このページ](../email/content-components.md)を参照してください。

   ![](assets/dynamic-media-template-1.png)

1. AEM アセットを参照して、コンテンツに追加する Dynamic Media テンプレートを選択します。

   ![](assets/dynamic-media-template-2.png)

1. **画像設定**&#x200B;で、Dynamic Media テンプレートのパラメーターにアクセスします。

   使用可能なフィールドは、Adobe Experience Manager での[テンプレート作成](https://experienceleague.adobe.com/ja/docs/dynamic-media-classic/using/template-basics/creating-template-parameters#creating_template_parameters){target="_blank"}時に追加したパラメーターによって異なります。

   ![](assets/dynamic-media-template-3.png)

1. 様々なフィールドに入力し、パーソナライゼーションエディターを使用して、パーソナライズされたコンテンツを追加します。プロファイル名、市区町村、その他の関連する詳細などの属性を使用して、よりカスタマイズされたエクスペリエンスを作成できます。

   パーソナライゼーションについて詳しくは、[このページ](../personalization/personalize.md)を参照してください。

   ![](assets/do-not-localize/dynamic_media_template.gif)

1. 条件付きコンテンツを Dynamic Media コンポーネントに適用して、コンテンツの様々なバリアントを生成できます。[詳細情報](../personalization/dynamic-content.md)

1. 「**[!UICONTROL 保存]**」をクリックします。

テストを実行してコンテンツを検証したら、メッセージをオーディエンスに送信できます。

### HTML コンポーネントの使用 {#html-component}

HTML コンポーネントを使用して、動的テンプレートをコンテンツに直接挿入できます。

1. キャンペーンまたはジャーニーを開き、コンテンツにアクセスします。

1. **HTML コンポーネント**&#x200B;をレイアウトにドラッグ＆ドロップします。

   ![](assets/dynamic-media-template-4.png)

1. 「**[!UICONTROL ソースコードを表示]**」を選択します。

   ![](assets/dynamic-media-template-5.png)

1. **[!UICONTROL HTML を編集]**&#x200B;メニューで、「**[!UICONTROL アセット]**」、「**[!UICONTROL アセットセレクターを開く]**」の順にアクセスします。

   または、アセットの URL をコピー＆ペーストすることもできます。

1. アセットの要件に合わせて、必要に応じて画像テキストパラメーターを調整します。

   ![](assets/do-not-localize/dynamic_media_template_html.gif)

1. 「**[!UICONTROL 保存]**」をクリックします。

テストを実行してコンテンツを検証したら、メッセージをオーディエンスに送信できます。

<!--
## Personalization with Text Overlay

Easily customize any dynamic media by replacing the existing text overlay with new text of your choice, allowing for seamless updates and personalization.

In this example, our goal is to update the existing text overlay by replacing it with a new validity date and adding a personalization block, ensuring it is customized for each profile when they open their messages.

1. Drag and drop an **[!UICONTROL HTML component]** into your content.

1. Select **[!UICONTROL Show the source code]**.

1. From the **[!UICONTROL Edit HTML]** menu, access **[!UICONTROL Assets]** then **[!UICONTROL Open asset selector]**.

    You can also simply copy and paste your assets URL.

1. Browse through your AEM assets and select the one you want to add to your content.

1. Replace the overlay with the desired text.

    Here we change the validity date from 31st December 2024 to the 1st July 2025.

1. Add the required personalization fields to your image.

1. Click **[!UICONTROL Save]**.

Your content now includes your updated text overlay and personalization.

## Add Dynamic media conditional content

Enable conditional content in your dynamic media to better target your audience and deliver a more personalized experience.

1. Drag and drop an **[!UICONTROL HTML component]** into your content.

1. Select **[!UICONTROL Show the source code]**.

1. From the **[!UICONTROL Edit HTML]** menu, access **[!UICONTROL Assets]** then **[!UICONTROL Open asset selector]**.

    You can also simply copy and paste your assets URL.

1. Browse through your AEM assets and select the one you want to add to your content.

1. Once your dynamic media is inserted to your content, select **[!UICONTROL Enable conditional]** content from your HTML component toolbar to create your different user experiences. 

1. From the Variant - 1, click **[!UICONTROL Select condition]** to fine tune your audience.

1. Choose your condition or create a new one if needed and click **[!UICONTROL Select]**.

    [Learn more about conditions](../personalization/create-conditions.md)

1. Select your **[!UICONTROL Component]** and access the **[!UICONTROL Settings]** menu.

1. In the **[!UICONTROL Custom Attributes]** menu, populate the Dynamic Media text and personalization fields to customize the content for your audience.

-->

## チュートリアルビデオ {#video}

Adobe Experience Manager Dynamic Media を Adobe Journey Optimizer と統合して、コンテンツのリアルタイムの更新とパーソナライゼーションを可能にする方法について説明します。

このチュートリアルでは、AJO 内で画像を直接変更する方法、HTML モードを使用してテキストオーバーレイを追加する方法、AEM で高度なパーソナライゼーション用の Dynamic Media テンプレートを作成する方法、様々なオーディエンスセグメントに合わせてコンテンツを調整してキャンペーンをパーソナライズする方法について説明します。この統合により、マーケターは、アプリケーションを切り替えずに、パーソナライズされた魅力的なキャンペーンを効率的に作成できます。

>[!VIDEO](https://video.tv.adobe.com/v/3457695/?learn=on&enablevpops=&autoplay=true)


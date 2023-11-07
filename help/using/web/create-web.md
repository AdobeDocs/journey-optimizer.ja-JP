---
title: Web エクスペリエンスの作成
description: Journey Optimizer で web ページを作成し、そのコンテンツを編集する方法を学ぶ
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: e28c038b-49ed-4685-bfe6-514116eb0711
source-git-commit: 27447578dad6bd2612989d79cd0dc8ddbe78d629
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 100%

---

# Web エクスペリエンスの作成 {#create-web}

[!DNL Journey Optimizer] では、インバウンド web キャンペーンを通じて、顧客に提供する web エクスペリエンスをパーソナライズできます。

>[!CAUTION]
>
>現在、[!DNL Journey Optimizer] では、**キャンペーン**&#x200B;を使用してのみ web エクスペリエンスを作成できます。

[こちらのビデオで web キャンペーンの作成方法を学習](#video)

## Web キャンペーンの作成 {#create-web-campaign}

>[!CONTEXTUALHELP]
>id="ajo_web_surface"
>title="Web サーフェスの定義"
>abstract="Web サーフェスは、単一のページ URL または複数のページを一致させることができるので、1 つまたは複数の web ページにわたってコンテンツの変更を配信できます。"

>[!CONTEXTUALHELP]
>id="ajo_web_surface_rule"
>title="ルールに一致するページの作成"
>abstract="ルールに一致するページを使用すると、同じルールに一致する複数の URL をターゲットにすることができます。例えば、変更を web サイト全体のヒーローバナーに適用したり、web サイトのすべての製品ページに表示されるトップ画像を追加したりする場合です。"

キャンペーンを通じて web エクスペリエンスの作成を開始するには、次の手順に従います。

>[!NOTE]
>
>Web エクスペリエンスを初めて作成する場合は、[こちらのセクション](web-prerequisites.md)に記載されている前提条件を必ず満たすようにしてください。

1. キャンペーンの作成. [詳細情報](../campaigns/create-campaign.md)

1. **[!UICONTROL Web]**&#x200B;アクションを選択します。

1. Web サーフェスを定義します。

   >[!NOTE]
   >
   >Web サーフェスは、コンテンツが配信される URL で識別される web プロパティです。単一ページの URL または複数のページを一致させることができるので、1 つまたは複数の web ページをまたいで変更を配信できます。

   単一ページのみに変更を適用する場合は、**[!UICONTROL ページ URL]** を入力します。

   ![](assets/web-campaign-surface.png)

1. または、**[!UICONTROL ルールに一致するページ]**&#x200B;を作成して、同じルールに一致する複数の URL をターゲットにすることもできます。例えば、変更を web サイト全体のヒーローバナーに適用したり、web サイトのすべての製品ページに表示されるトップ画像を追加したりする場合です。

   これを行うには、「**[!UICONTROL ルールに一致するページ]**」を選択し、「**[!UICONTROL ルールを作成]**」をクリックします。

   ![](assets/web-campaign-matching-rule.png)

1. 「**[!UICONTROL ドメイン]**」フィールドと「**[!UICONTROL ページ]**」フィールドの条件を定義します。

   例えば、Luma web サイトのすべての女性向け製品ページに表示される要素を編集する場合は、**[!UICONTROL ドメイン]**／**[!UICONTROL 次で始まる]**／`luma` および&#x200B;**[!UICONTROL ページ]**／**[!UICONTROL 次を含む]**／`women` を選択します。

   ![](assets/web-pages-matching-rule.png)

1. 変更を保存します。ルールは、**[!UICONTROL キャンペーンを作成]**&#x200B;画面に表示されます。

   ![](assets/web-pages-matching-rule-example.png)

1. Web サーフェスを定義したら、「**[!UICONTROL 作成]**」を選択します。

1. キャンペーンのプロパティ、[オーディエンス](../audience/about-audiences.md)、[スケジュール](../campaigns/create-campaign.md#schedule)など、web キャンペーンを作成する手順を完了します。

   ![](assets/web-campaign-steps.png)

キャンペーンの設定方法について詳しくは、[このページ](../campaigns/get-started-with-campaigns.md)を参照してください。

## Web キャンペーンのテスト {#test-web-campaign}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_preview"
>title="Web エクスペリエンスのプレビュー"
>abstract="Web エクスペリエンスがどのように表示されるかをシミュレーションで確認します。"

Web デザイナーを使用して [web エクスペリエンスを作成](edit-web-content.md)したら、テストプロファイルを使用して、変更した web ページをプレビューできます。パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがどのように表示されるかを、テストプロファイルデータを使用して確認できます。

これを行うには、web キャンペーンのコンテンツ編集画面または web デザイナーから「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルを追加し、テストプロファイルデータを使用して web ページを確認します。

![](assets/web-designer-preview.png)

また、デフォルトのブラウザーで開くことも、テスト URL をコピーして任意のブラウザーに貼り付けることもできます。これにより、キャンペーンの実施前に任意のブラウザーで新しい web エクスペリエンスをプレビューできるチームや関係者とリンクを共有できます。

>[!NOTE]
>
>テスト URL をコピーする際に表示されるコンテンツは、コンテンツのシミュレーションが [!DNL Journey Optimizer] で生成されるときにテストプロファイル用にパーソナライズされます。

テストプロファイルの選択およびコンテンツのプレビュー方法について詳しくは、「[コンテンツ管理](../content-management/preview-test.md)」の節を参照してください。

## Web キャンペーンのアクティブ化 {#activate-web-campaign}

[Web キャンペーンの設定](#configure-web-campaign)を定義し、[web デザイナー](edit-web-content.md#work-with-web-designer)を使用して必要に応じてコンテンツを編集したら、web キャンペーンをレビューおよびアクティブ化できます。次の手順に従います。

<!--
>[!NOTE]
>
>You can also preview your web campaign content before activating it. [Learn more](#test-web-campaign)-->

1. Web キャンペーンから、「**[!UICONTROL アクティブ化するレビュー]**」を選択します。

1. コンテンツ、プロパティ、サーフェス、オーディエンス、スケジュールを必要に応じて確認および編集します。

1. 「**[!UICONTROL アクティブ化]**」を選択します。

   ![](assets/web-campaign-activate.png)

   >[!NOTE]
   >
   >「**[!UICONTROL アクティブ化]**」をクリックした後、web キャンペーンの変更が web サイトでライブになるまでに最大 15 分かかる場合があります。

Web キャンペーンは&#x200B;**[!UICONTROL ライブ]**&#x200B;ステータスになり、選択したオーディエンスに対して表示されるようになりました。キャンペーンの各受信者は、[!DNL Journey Optimizer] の web デザイナーを使用して web サイトに追加した変更を表示できます。

>[!NOTE]
>
>Web キャンペーンのスケジュールを定義した場合、開始日時に達するまで、**[!UICONTROL スケジュール済み]**&#x200B;ステータスになります。
>
>既に実行中の別のキャンペーンと同じページに影響を与える web キャンペーンをアクティブ化すると、すべての変更が web ページに適用されます。

キャンペーンのアクティブ化について詳しくは、[この節](../campaigns/review-activate-campaign.md)を参照してください。

## Web キャンペーンの停止 {#stop-web-campaign}

Web キャンペーンがライブの場合、停止して、オーディエンスに変更が表示されないようにすることができます。次の手順に従います。

1. リストからライブキャンペーンを選択します。

1. 上部のメニューから、「**[!UICONTROL キャンペーンを停止]**」を選択します。

   ![](assets/web-campaign-stop.png)

1. 追加した変更は、定義したオーディエンスには表示されなくなります。

>[!NOTE]
>
>Web キャンペーンが停止した後は、再び編集またはアクティブ化することはできません。キャンペーンを複製し、複製したものをアクティブ化することのみ可能です。

## チュートリアルビデオ{#video}

以下のビデオでは、web キャンペーンの作成、プロパティの設定、レビュー、公開の方法を確認できます。

>[!VIDEO](https://video.tv.adobe.com/v/3418800/?quality=12&learn=on)
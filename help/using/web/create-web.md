---
title: Web エクスペリエンスの作成
description: Journey Optimizer で web ページを作成し、そのコンテンツを編集する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: e28c038b-49ed-4685-bfe6-514116eb0711
source-git-commit: 0f69a47dccad20f3e978613b349a29f9daab94bd
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 97%

---

# Web エクスペリエンスの作成 {#create-web}

>[!AVAILABILITY]
>
>現在、web チャネル機能は、一部のユーザーのみが利用できるベータ版として使用できます。

[!DNL Journey Optimizer] では、インバウンド web キャンペーンを通じて、顧客に提供する web エクスペリエンスをパーソナライズできます。

>[!CAUTION]
>
>現在、[!DNL Journey Optimizer] では、**キャンペーン**&#x200B;を使用してのみ web エクスペリエンスを作成できます。

## 前提条件 {#prerequesites}

[!DNL Journey Optimizer] ユーザーインターフェイスで web ページにアクセスして作成できるようにするには、次の前提条件に従ってください。

* Web サイトに変更を追加するには、web サイトに [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target=&quot;_blank&quot;} を実装する必要があります。

* [!DNL Journey Optimizer] の web デザイナーにアクセスするには、Chrome で [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=&quot;_blank&quot;} ブラウザー拡張機能をダウンロードする必要があります。[詳細情報](visual-editing-helper.md)

>[!CAUTION]
>
>Google Chrome は現在、[!DNL Journey Optimizer] で web ページの作成をサポートしている唯一のブラウザーです。

Web エクスペリエンスが正しく配信されるようにするには、次の設定を定義する必要があります。

* [Adobe Experience Platform データ収集](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target=&quot;_blank&quot;} で、**[!UICONTROL Adobe Experience Platform]** サービスの下で「**[!UICONTROL Edge セグメント化]**」オプションと「**[!UICONTROL Adobe Journey Optimizer]**」オプションの両方を有効にするなど、データストリームが定義されていることを確認します。

   これにより、Journey Optimizer インバウンドイベントが Adobe Experience Platform Edge で正しく処理されます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja){target=&quot;_blank&quot;}

   ![](assets/web-aep-datastream-ajo.png)

   >[!NOTE]
   >
   >「**[!UICONTROL Adobe Journey Optimizer]**」オプションは、「**[!UICONTROL Edge セグメント化]**」オプションが既に有効になっている場合にのみ有効にできます。

* [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target=&quot;_blank&quot;} で、「**[!UICONTROL Active-On-Edge 結合ポリシー]**」オプションが有効になっている結合ポリシーが 1 つあることを確認します。これを行うには、**[!UICONTROL 顧客r]**／**[!UICONTROL プロファイル]**／**[!UICONTROL 結合ポリシー]** Experience Platform メニューでポリシーを選択します。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target=&quot;_blank&quot;}

   この結合ポリシーは、[!DNL Journey Optimizer] インバウンドチャネルで使用すると、エッジでインバウンドキャンペーンを正しくアクティブ化して公開できます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja){target=&quot;_blank&quot;}

   ![](assets/web-aep-merge-policy.png)

## Web キャンペーンの作成 {#create-web-campaign}

>[!CONTEXTUALHELP]
>id="ajo_web_surface"
>title="Web サーフェスを定義する"
>abstract="Web サーフェスは、1 つのページ URL または複数のページと一致させることができ、1 つまたは複数の Web ページにコンテンツの変更を配信できます。"

キャンペーンを通じて web エクスペリエンスの作成を開始するには、次の手順に従います。

1. キャンペーンの作成. [詳細情報](../campaigns/create-campaign.md)

1. **[!UICONTROL Web]**&#x200B;アクションを選択します。

   ![](assets/web-create-campaign.png)

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

1. Web サーフェスを定義したら、「**[!UICONTROL 作成]**」を選択します。これで、キャンペーンのプロパティと設定を設定できます。

## Web キャンペーンの設定 {#configure-web-campaign}

1. 「**[!UICONTROL プロパティ]**」タブでは、キャンペーン名を編集し、必要に応じて説明を追加できます。

   ![](assets/web-campaign-properties.png)

1. カスタムまたはコアのデータ使用ラベルを web キャンペーンに割り当てるには、画面上部の「**[!UICONTROL アクセスを管理]**」ボタンを選択します。[オブジェクトレベルのアクセス制御（OLAC）について詳しくはこちらから](../administration/object-based-access.md)

1. 「**[!UICONTROL コンテンツ実験]**」を選択して、特定の指標に関してどの処理が最も効果的かを判断するために、オーディエンスの一部でコンテンツ処理をテストできます。[詳細情報](../campaigns/content-experiment.md)

   >[!AVAILABILITY]
   >
   >**コンテンツ実験**&#x200B;機能は現在、一連の組織でのみ使用できます（使用制限あり）。詳しくは、アドビ担当者にお問い合わせください。

1. キャンペーンの「**[!UICONTROL アクション]**」タブから、「**[!UICONTROL コンテンツを編集]**」を選択して web キャンペーンの作成を開始します。[詳細情報](author-web.md)

   ![](assets/web-edit-content.png)

1. 「**[!UICONTROL オーディエンス]**」タブで、web キャンペーンを表示できるユーザーを定義します。デフォルトでは、web キャンペーンはすべての訪問者に表示されます。

   ![](assets/web-campaign-audience.png)

   また、特定のオーディエンスを選択することもできます。「**[!UICONTROL オーディエンスを選択]**」ボタンを使用して、使用可能な Adobe Experience Platform セグメントのリストを表示します。[セグメントについて詳しくはこちらを参照](../segment/about-segments.md)

   >[!NOTE]
   >
   >API トリガーキャンペーンの場合、オーディエンスは API 呼び出しを使用して設定する必要があります。[詳細情報](../campaigns/api-triggered-campaigns.md)

   ![](assets/web-campaign-select-audience.png)

1. 「**[!UICONTROL ID 名前空間]**」フィールドで、選択したセグメントから個人を識別するために使用する名前空間を選択します。[名前空間について詳しくはこちらを参照](../event/about-creating.md#select-the-namespace)

1. Web キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を定義します。[詳細情報](../campaigns/create-campaign.md#schedule)

   ![](assets/web-campaign-schedule.png)

   デフォルトでは、手動でアクティブ化したときに開始し、手動で停止したときに終了しますが、変更を表示する特定の日付と時間を定義することもできます。

   ![](assets/web-campaign-schedule-start.png)

## Web キャンペーンのアクティブ化 {#activate-web-campaign}

[Web キャンペーンの設定](#configure-web-campaign)を定義し、[web デザイナー](author-web.md)を使用して必要に応じてコンテンツを編集したら、web キャンペーンをレビューおよびアクティブ化できます。次の手順に従います。

>[!NOTE]
>
>アクティブ化する前に web キャンペーンのコンテンツをプレビューすることもできます。[詳細情報](author-web.md#test-web-campaign)

1. Web キャンペーンから、「**[!UICONTROL アクティブ化するレビュー]**」を選択します。

   ![](assets/web-campaign-review.png)

1. コンテンツ、プロパティ、サーフェス、オーディエンス、スケジュールを必要に応じてレビューおよび編集します。

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

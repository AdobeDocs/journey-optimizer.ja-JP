---
solution: Journey Optimizer
product: journey optimizer
title: フラグメントの作成
description: フラグメントを作成して、Journey Optimizer のキャンペーンとジャーニーでコンテンツを再利用する方法について説明します
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: da3ffe9c-a244-4246-b4b5-a3a1d0508676
source-git-commit: abd5f388a41cc85c710cdb8c8e51c7fe381714ad
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 100%

---

# フラグメントの作成 {#create-fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_visual_fragment"
>title="ビジュアルタイプを選択"
>abstract="スタンドアロンのビジュアルフラグメントを作成して、ジャーニーまたはキャンペーン内のメールや、コンテンツテンプレートでコンテンツを再利用できるようにします。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/email/design-email/add-content/use-visual-fragments" text="メールへのビジュアルフラグメントの追加"

>[!CONTEXTUALHELP]
>id="ajo_create_expression_fragment"
>title="式タイプの選択"
>abstract="スタンドアロン式のフラグメントを作成して、複数のジャーニーやキャンペーンでコンテンツを再利用できるようにします。パーソナライゼーションエディターを使用すると、現在のサンドボックスで作成されたすべての式フラグメントを活用できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/content-management/personalization/personalization-build-expressions" text="パーソナライゼーションエディターの操作"

フラグメントは、左側のメニューの&#x200B;**[!UICONTROL フラグメント]**&#x200B;からゼロから作成できます。さらに、コンテンツをデザインする際に、既存のコンテンツの一部をフラグメントとして保存することもできます。[方法についてはこちらを参照](#save-as-fragment)

保存すると、フラグメントをジャーニー、キャンペーンまたはテンプレートで使用できるようになります。このフラグメントは、ジャーニーとキャンペーン内でコンテンツを作成する際に使用できます。[ビジュアルフラグメントの追加](../email/use-visual-fragments.md)および[式フラグメントの活用](../personalization/use-expression-fragments.md)を参照してください。

フラグメントを作成するには、次の手順に従います。

## フラグメントのプロパティの定義 {#properties}

1. **[!UICONTROL コンテンツ管理]**／**[!UICONTROL フラグメント]**&#x200B;の左のメニューから、フラグメントリストにアクセスします。

1. 「**[!UICONTROL フラグメントを作成]**」を選択し、フラグメント名と説明を（必要に応じて）入力します。

   ![](assets/fragment-details.png)

1. 「**[!UICONTROL タグ]**」フィールドから Adobe Experience Platform タグを選択または作成してフラグメントを分類し、検索の向上を図ります。[詳しくは、統合タグの操作方法を参照してください](../start/search-filter-categorize.md#tags)

1. フラグメントタイプ（**ビジュアルフラグメント**&#x200B;または&#x200B;**式フラグメント**）を選択します。[詳細情報](../content-management/fragments.md#visual-expression)

   >[!NOTE]
   >
   >現時点では、ビジュアルフラグメントは、**メール**&#x200B;チャネルでのみ使用できます。

1. 式フラグメントを作成する場合は、使用するコードのタイプを **[!UICONTROL HTML]**、**[!UICONTROL JSON]** または&#x200B;**[!UICONTROL テキスト]**&#x200B;から選択します。

   ![](assets/fragment-expression-type.png)

1. カスタムまたはコアのデータ使用ラベルをフラグメントに割り当てるには、画面の上部セクションで「**[!UICONTROL アクセスを管理]**」ボタンをクリックします。[オブジェクトレベルのアクセス制御（OLAC）についての詳細を参照してください](../administration/object-based-access.md)。

1. 「**[!UICONTROL 作成]**」をクリックして、フラグメントのコンテンツをデザインします。

## フラグメントコンテンツのデザイン {#content}

フラグメントのプロパティを設定すると、作成するフラグメントのタイプに応じて、E メールデザイナーまたはパーソナライゼーションエディターが開きます。

>[!NOTE]
>
>[コンテキスト属性](../personalization/personalization-build-expressions.md)は、フラグメント内ではサポートされていません。
>
>ジャーニーまたはキャンペーンでトラッキングが有効になっている場合、フラグメントにリンクを追加し、このフラグメントがメッセージで使用されていると、メッセージに含まれる他のすべてのリンクと同様に、これらのリンクが追跡されます。[リンクとトラッキングの詳細情報](../email/message-tracking.md)

* ビジュアルフラグメントの場合は、ジャーニーやキャンペーン内のメールと同じ方法で、必要に応じてコンテンツを編集します。[詳細情報](../email/get-started-email-design.md)

  ![](assets/fragment-designer.png)

  ブランドやデザインに合った特定のスタイル設定をすばやく適用するには、フラグメントに[テーマ](../email/apply-email-themes.md)を適用します。

  ![](assets/fragment-themes.png)

  >[!CAUTION]
  >
  >フラグメントには、テーマを使用モードと手動スタイルモード間で相互互換性がありません。テーマを適用するコンテンツでフラグメントを使用できるようにするには、このフラグメントをテーマを使用モードで作成する必要があります。[テーマの詳細情報](../email/apply-email-themes.md)

* 式フラグメントの場合は、[!DNL Journey Optimizer] パーソナライゼーションエディターのすべてのパーソナライズ機能およびオーサリング機能を活用して、フラグメントコンテンツを構築します。[詳細情報](../personalization/personalization-build-expressions.md)

  ![](assets/fragment-expression-editor.png)

コンテンツの準備が整ったら、「**[!UICONTROL 保存]**」ボタンをクリックします。

>[!NOTE]
>
>ビジュアルフラグメントは、100 KB を超えることはできません。式フラグメントは、200 KB を超えることはできません。

フラグメントが作成され、**[!UICONTROL ドラフト]**&#x200B;ステータスでフラグメントリストに追加されます。追加されたフラグメントをプレビューして公開し、ジャーニーとキャンペーンで使用できます。

## フラグメントのプレビューと公開 {#publish}

>[!NOTE]
>
>フラグメントを公開するには、[フラグメントを公開](../administration/ootb-product-profiles.md#content-library-manager)するユーザー権限が必要です。

フラグメントを公開する準備が整ったら、プレビューして公開し、ジャーニーやキャンペーンで使用できます。これを行うには、以下の手順に従います。

1. コンテンツをデザインした後にフラグメントの作成画面に戻るか、フラグメントのリストから開きます。

1. フラグメントのプレビューは、「**[!UICONTROL タグ]**」フィールドで利用でき、レンダリングを確認できます。変更を行う必要がある場合は、画面の上部セクションで「**[!UICONTROL 編集]**」ボタンをクリックして、フラグメントのタイプに応じて E メールデザイナーまたはパーソナライゼーションエディターを開きます。[詳細情報](manage-fragments.md#edit-fragments)

   ![](assets/fragment-preview.png)

1. 右上隅の「**[!UICONTROL 公開]**」ボタンをクリックして、フラグメントを公開します。

1. フラグメントがライブジャーニーまたはキャンペーンで使用されている場合は、通知するメッセージが開きます。「**[!UICONTROL さらに表示]**」リンクをクリックすると、参照先のジャーニーやキャンペーンのリストにアクセスできます。[詳しくは、フラグメントの参照の探索方法を参照してください](../content-management/manage-fragments.md#explore-references)

   ![](assets/fragment-publish.png){width="70%" align="center"}

   「**[!UICONTROL 確認]**」をクリックしてフラグメントを公開し、使用しているライブジャーニー／キャンペーンで更新します。

フラグメントは&#x200B;**[!UICONTROL ライブ]**&#x200B;に変わり、[!DNL Journey Optimizer] E メールデザイナーまたはパーソナライゼーションエディター内でコンテンツを作成する際に使用できるようになります。

* [ビジュアルフラグメントの使用方法を学ぶ](../email/use-visual-fragments.md)
* [式フラグメントの使用方法を学ぶ](../personalization/use-expression-fragments.md)

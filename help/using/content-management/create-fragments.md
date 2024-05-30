---
solution: Journey Optimizer
product: journey optimizer
title: フラグメントの作成
description: フラグメントを作成して、Journey Optimizer のキャンペーンとジャーニーでコンテンツを再利用する方法を学ぶ
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 83997271d16e15fb0d7ccdd21aa8ac8b8221a0d5
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 55%

---


# フラグメントを最初から作成する {#create-fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_visual_fragment"
>title="ビジュアルタイプを選択"
>abstract="スタンドアロンのビジュアルフラグメントを作成して、ジャーニーまたはキャンペーン内のメールや、コンテンツテンプレートでコンテンツを再利用できるようにします。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/email/design-email/add-content/use-visual-fragments.html?lang=ja" text="メールへのビジュアルフラグメントの追加"

>[!CONTEXTUALHELP]
>id="ajo_create_expression_fragment"
>title="式タイプの選択"
>abstract="スタンドアロン式のフラグメントを作成して、複数のジャーニーやキャンペーンでコンテンツを再利用できるようにします。パーソナライゼーションエディターを使用する場合、現在のサンドボックスで作成されたすべての式フラグメントを活用できます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/content-management/personalization/expression-editor/use-expression-fragments.html?lang=ja" text="式フラグメントを活用"

フラグメントはから作成されます **[!UICONTROL フラグメント]** 左メニュー。 また、コンテンツをデザインする際に、既存のコンテンツの一部をフラグメントとして保存することもできます。 [方法についてはこちらを参照](#save-as-fragment)

保存すると、フラグメントをジャーニー、キャンペーンまたはテンプレートで使用できるようになります。このフラグメントは、内でコンテンツを作成する際に使用できるようになりました [!DNL Journey Optimizer]. [ビジュアルフラグメントの追加](../email/use-visual-fragments.md)および[式フラグメントの活用](../personalization/use-expression-fragments.md)を参照してください

フラグメントをゼロから作成するには、次の手順に従います。

1. [](#access-manage-fragments)**[!UICONTROL コンテンツ管理]**／**[!UICONTROL フラグメント]**&#x200B;の左のメニューから、フラグメントリストにアクセスします。

1. 「**[!UICONTROL フラグメントを作成]**」を選択します。

1. フラグメントの詳細、名前や説明などを（必要に応じて）入力します。

   ![](assets/fragment-details.png)

1. 「**[!UICONTROL タグ]**」フィールドから Adobe Experience Platform タグを選択または作成してフラグメントを分類し、検索の向上を図ります。[詳細情報](../start/search-filter-categorize.md#tags)

1. フラグメントのタイプ（[ビジュアルフラグメント](#create-visual-fragment)または[式フラグメント](#create-expression-fragment)）を選択します。

   >[!NOTE]
   >
   >現在、ビジュアルフラグメントについては、**メール**&#x200B;チャネルのみがサポートされています。

1. 式フラグメントを作成する場合は、使用するコードのタイプを選択します。 **[!UICONTROL HTML]**, **[!UICONTROL JSON]** または **[!UICONTROL テキスト]**.

   ![](assets/fragment-expression-type.png)

1. カスタムまたはコアのデータ使用ラベルをフラグメントに割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。[オブジェクトレベルのアクセス制御（OLAC）についての詳細はこちらを参照してください](../administration/object-based-access.md)。

1. 「**[!UICONTROL 作成]**」をクリックします。

1. この [電子メールデザイナー](../email/get-started-email-design.md) 作成しているフラグメントのタイプに応じて、パーソナライゼーションエディターが開きます。

   * ビジュアルフラグメントの場合は、ジャーニーやキャンペーン内のメールと同じ方法で、必要に応じてコンテンツを編集します。

     >[!NOTE]
     >
     >パーソナライゼーションフィールドと動的コンテンツを追加できますが、コンテキスト属性はフラグメントではサポートされていません。

     ![](assets/fragment-designer.png)

   * 式フラグメントの場合は、を利用します [!DNL Journey Optimizer] フラグメントコンテンツを作成するためのすべてのパーソナライゼーション機能とオーサリング機能が備わったパーソナライゼーションエディター。 [詳細情報](../personalization/personalization-build-expressions.md)

     ![](assets/fragment-expression-editor.png)

1. フラグメントの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。

フラグメントがに追加されます。 [フラグメントリスト](#access-manage-fragments). これで、内でコンテンツを作成する際に使用できるようになりました [!DNL Journey Optimizer] 電子メールデザイナーまたはパーソナライゼーションエディター。

* [ビジュアルフラグメントの使用方法について](../email/use-visual-fragments.md)
* [式フラグメントの使用方法について](../personalization/use-expression-fragments.md)

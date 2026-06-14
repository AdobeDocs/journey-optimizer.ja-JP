---
solution: Journey Optimizer
product: journey optimizer
title: フラグメントを作成
description: フラグメントを作成して、Journey Optimizer のキャンペーンとジャーニーでコンテンツを再利用する方法について説明します
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: da3ffe9c-a244-4246-b4b5-a3a1d0508676
TQID: https://experienceleague.adobe.com/NlC-JLidAL9r-1-8rX4hX-WxCkr-Nv1e6YKSisx1n28
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: c6e980f5-2d4f-494f-beef-186b9ecf1513
  - id: ee5bb250-0884-4d71-86eb-d8489e8bcadd
  - id: f8d2e9f0-69c9-40cd-890f-71336c8dfff7
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: dc3ac795cd3cbfbd3dd3adfe6f220641d331081f
workflow-type: tm+mt
source-wordcount: 1008
ht-degree: 78%

---

# フラグメントを作成 {#create-fragments}

>[!BEGINSHADEBOX]

**このページ：** ビジュアルフラグメントとエクスプレッションフラグメントを作成、デザイン、ロック、プレビュー、公開して、Adobe Journey Optimizer キャンペーンとジャーニー全体でコンテンツを再利用する方法を説明します。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_create_visual_fragment"
>title="ビジュアルタイプを選択"
>abstract="スタンドアロンのビジュアルフラグメントを作成して、ジャーニーまたはキャンペーン内のメールや、コンテンツテンプレートでコンテンツを再利用できるようにします。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/email/design-email/add-content/use-visual-fragments" text="メールへのビジュアルフラグメントの追加"

>[!CONTEXTUALHELP]
>id="ajo_create_expression_fragment"
>title="式タイプの選択"
>abstract="スタンドアロン式のフラグメントを作成して、複数のジャーニーやキャンペーンでコンテンツを再利用できるようにします。 パーソナライゼーションエディターを使用すると、現在のサンドボックスで作成されたすべての式フラグメントを活用できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/content-management/personalization/personalization-build-expressions" text="パーソナライゼーションエディターの操作"

フラグメントは、左側のメニューの&#x200B;**[!UICONTROL フラグメント]**&#x200B;からゼロから作成できます。 さらに、コンテンツをデザインする際に、既存のコンテンツの一部をフラグメントとして保存することもできます。 [方法についてはこちらを参照](save-fragments.md#)

保存すると、フラグメントをジャーニー、キャンペーンまたはテンプレートで使用できるようになります。 このフラグメントは、ジャーニーとキャンペーン内でコンテンツを作成する際に使用できます。 [ビジュアルフラグメントの追加](../email/use-visual-fragments.md)および[式フラグメントの活用](../personalization/use-expression-fragments.md)を参照してください。

フラグメントを作成するには、次の手順に従います。

## フラグメントのプロパティの定義 {#properties}

1. **[!UICONTROL コンテンツ管理]**／**[!UICONTROL フラグメント]**&#x200B;の左のメニューから、フラグメントリストにアクセスします。

1. 「**[!UICONTROL フラグメントを作成]**」を選択し、フラグメント名と説明を（必要に応じて）入力します。

   ![](assets/fragment-details.png)

1. 「**[!UICONTROL タグ]**」フィールドから Adobe Experience Platform タグを選択または作成してフラグメントを分類し、検索の向上を図ります。 [詳しくは、統合タグの操作方法を参照してください](../start/search-filter-categorize.md#tags)

1. フラグメントタイプ（**ビジュアルフラグメント**&#x200B;または&#x200B;**式フラグメント**）を選択します。 [詳細情報](../content-management/fragments.md#visual-expression)

   >[!NOTE]
   >
   >現時点では、ビジュアルフラグメントは、**メール**&#x200B;チャネルでのみ使用できます。

1. 式フラグメントを作成する場合は、使用するコードのタイプを **[!UICONTROL HTML]**、**[!UICONTROL JSON]** または&#x200B;**[!UICONTROL テキスト]**&#x200B;から選択します。

   ![](assets/fragment-expression-type.png)

1. カスタムまたはコアのデータ使用ラベルをフラグメントに割り当てるには、画面の上部セクションで「**[!UICONTROL アクセスを管理]**」ボタンをクリックします。 [詳しくは、オブジェクトレベルのアクセス制御（OLAC）を参照してください](../administration/object-based-access.md)。

1. 「**[!UICONTROL 作成]**」をクリックして、フラグメントのコンテンツをデザインします。

## フラグメントコンテンツのデザイン {#content}

フラグメントのプロパティを設定すると、作成するフラグメントのタイプに応じて、E メールデザイナーまたはパーソナライゼーションエディターが開きます。

>[!NOTE]
>
>[コンテキスト属性](../personalization/personalization-build-expressions.md)は、フラグメント内ではサポートされていません。
>
>ジャーニーまたはキャンペーンでトラッキングが有効になっている場合、フラグメントにリンクを追加し、このフラグメントがメッセージで使用されていると、メッセージに含まれる他のすべてのリンクなど、これらのリンクを追跡します。 [リンクとトラッキングの詳細情報](../email/message-tracking.md)

* ビジュアルフラグメントの場合は、ジャーニーやキャンペーン内のメールと同じ方法で、必要に応じてコンテンツを編集します。 [詳細情報](../email/get-started-email-design.md)

  ![](assets/fragment-designer.png)

  ブランドやデザインに合った特定のスタイル設定をすばやく適用するには、フラグメントに[テーマ](../email/apply-email-themes.md)を適用します。

  ![](assets/fragment-themes.png)

  >[!CAUTION]
  >
  >フラグメントには、テーマを使用モードと手動スタイルモード間で相互互換性がありません。 メールコンテンツでフラグメントを使用する際は、このフラグメント用に定義したテーマを適用してください。 [詳細情報](../email/apply-email-themes.md#leverage-themes-fragment)

* 式フラグメントの場合は、[!DNL Journey Optimizer] パーソナライゼーションエディターのすべてのパーソナライズ機能およびオーサリング機能を活用して、フラグメントコンテンツを構築します。 [詳細情報](../personalization/personalization-build-expressions.md)

  ![](assets/fragment-expression-editor.png)

  >[!NOTE]
  >
  >JSON タイプの式フラグメントは、保存時に構文で検証され、エラーはすべて警告アラートとして表示されます。

コンテンツの準備が整ったら、「**[!UICONTROL 保存]**」ボタンをクリックします。

>[!NOTE]
>
>ビジュアルフラグメントは、100 KB を超えることはできません。 式フラグメントは、200 KB を超えることはできません。

フラグメントが作成され、**[!UICONTROL ドラフト]**&#x200B;ステータスでフラグメントリストに追加されます。 追加されたフラグメントをプレビューして公開し、ジャーニーとキャンペーンで使用できます。

### ビジュアルフラグメントのロック {#lock-visual-fragment}

ビジュアルフラグメントを作成または編集する場合は、ビジュアルフラグメントをロックして、電子メールで使用するときに編集者がビジュアルフラグメントを変更または削除できないようにすることができます。

このオプションを選択すると、フラグメントが使用される場所で同期が維持され、ブランドの適用、一貫性の維持、法的要件の遵守に役立ちます。

ビジュアルフラグメントをロックするには、次の手順に従います。

1. フラグメントコンテンツ編集画面で、「**[!UICONTROL 設定]**」タブに移動します。

1. デフォルトでは、フラグメントのロックは解除されます。 「**[!UICONTROL 継承が破損するのを防ぐ]**」を選択して、フラグメントをロックします。

1. 「**[!UICONTROL 確認]**」をクリックします。

   >[!NOTE]
   >
   >この設定はいつでも更新できます。 ただし、変更は将来の使用にのみ適用されます。 このフラグメントを使用する既存のメールは変更されません。

![](assets/fragment-lock.png){width="70%" align="center"}

このフラグメントをメールで使用する場合、そのフラグメントはロックされ、元のフラグメントから切り離せなくなりました。 [詳細情報](../email/use-visual-fragments.md#locked-fragments)

元のロックされたフラグメントに対する新しい更新は、それを使用するすべての電子メールに自動的に反映されます。

## フラグメントのプレビューと公開 {#publish}

>[!NOTE]
>
>フラグメントを公開するには、[フラグメントを公開](../administration/ootb-product-profiles.md#content-library-manager)するユーザー権限が必要です。

フラグメントを公開する準備が整ったら、プレビューして公開し、ジャーニーやキャンペーンで使用できます。 これを行うには、以下の手順に従います。

1. コンテンツをデザインした後にフラグメントの作成画面に戻るか、フラグメントのリストから開きます。

1. フラグメントのプレビューは、「**[!UICONTROL タグ]**」フィールドで利用でき、レンダリングを確認できます。 変更を行う必要がある場合は、画面の上部セクションで「**[!UICONTROL 編集]**」ボタンをクリックして、フラグメントのタイプに応じて E メールデザイナーまたはパーソナライゼーションエディターを開きます。 [詳細情報](manage-fragments.md#edit-fragments)

   ![](assets/fragment-preview.png)

1. 右上隅の「**[!UICONTROL 公開]**」ボタンをクリックして、フラグメントを公開します。

1. フラグメントがライブジャーニーまたはキャンペーンで使用されている場合は、通知するメッセージが開きます。 「**[!UICONTROL さらに表示]**」リンクをクリックすると、参照先のジャーニーやキャンペーンのリストにアクセスできます。 [詳しくは、フラグメントの参照の探索方法を参照してください](../content-management/manage-fragments.md#explore-references)

   ![](assets/fragment-publish.png){width="70%" align="center"}

   「**[!UICONTROL 確認]**」をクリックしてフラグメントを公開し、使用しているライブジャーニー／キャンペーンで更新します。

フラグメントは&#x200B;**[!UICONTROL ライブ]**&#x200B;に変わり、[!DNL Journey Optimizer] E メールデザイナーまたはパーソナライゼーションエディター内でコンテンツを作成する際に使用できるようになります。

* [ビジュアルフラグメントの使用方法を学ぶ](../email/use-visual-fragments.md)
* [式フラグメントの使用方法を学ぶ](../personalization/use-expression-fragments.md)

>[!CAUTION]
>
>公開すると、ライブフラグメントに新しいパーソナライズされた属性を追加することはできません。 パーソナライゼーション属性を追加するには、フラグメントを複製する必要があります。 [詳細情報](manage-fragments.md#adding-new-attributes)


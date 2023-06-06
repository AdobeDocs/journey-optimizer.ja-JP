---
solution: Journey Optimizer
product: journey optimizer
title: フラグメントの作成
description: フラグメントを作成して、Journey Optimizer のキャンペーンとジャーニーでコンテンツを再利用する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 05f74838-6766-47ea-aaed-a67c174a51a9
source-git-commit: a2b2398280624c4f344ff2530a6054b68f082eab
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 98%

---

# フラグメントの操作 {#fragments}

フラグメントは、[!DNL Journey Optimizer] キャンペーンおよびジャーニー全体で 1 つ以上のメールで参照できる再利用可能なコンポーネントです。

この機能を使用すると、技術者以外のマーケティングユーザーが改善されたデザインプロセスでメールコンテンツを迅速に組み立てるために使用できる複数のカスタムコンテンツブロックを事前に構築できます。

➡️ [フラグメントの管理、作成、使用方法については、このビデオを参照してください](#video-fragments)

>[!CAUTION]
>
>フラグメントを作成、編集、アーカイブするには、**[!DNL Content Library Manager]** 製品プロファイルに含まれる **[!DNL Manage Library Items]** 権限を付与されている必要があります。[詳細情報](../administration/ootb-product-profiles.md#content-library-manager)

フラグメントを最大限に活用するには：

* 独自のフラグメントを作成します。詳しくは、[フラグメントの作成](#create-fragments)を参照してください
* 作成したフラグメントを、必要な回数だけメールで使用します。詳しくは、[フラグメントの使用](#use-fragments)を参照してください

>[!NOTE]
>
>現在、この機能はメールでのみ使用できます。

## フラグメントへのアクセスと管理 {#access-manage-fragments}

フラグメントリストにアクセスするには、左のメニューで&#x200B;**[!UICONTROL コンテンツ管理]**／**[!UICONTROL フラグメント]**&#x200B;を選択します。

![](assets/fragment-list.png)

現在のサンドボックスで作成されたすべてのフラグメント（**[!UICONTROL フラグメント]**&#x200B;メニューからか、「[フラグメントとして保存](#save-as-fragment)」オプションを使用して）が表示されます。

作成日または変更日にフラグメントをフィルタリングできます。すべてのフラグメントを表示するか、現在のユーザーが作成または変更した項目のみを表示するかを選択できます。また、**[!UICONTROL アーカイブ済み]**&#x200B;フラグメントを表示することもできます。[詳細情報](#archive-fragments)

![](assets/fragment-list-filters.png)

各フラグメントの横にある&#x200B;**[!UICONTROL その他のアクション]**&#x200B;アイコンから、次の操作を実行できます。

* フラグメントを複製します。

* 「**[!UICONTROL 参照を探索]**」オプションを使用して、使用されているジャーニー、キャンペーン、テンプレートを確認します。[詳細情報](#explore-references)

* フラグメントをアーカイブします。[詳細情報](#archive-fragments)

![](assets/fragment-list-more-actions.png)

### フラグメントの編集 {#edit-fragments}

フラグメントを編集するには、次の手順に従います。

1. **[!UICONTROL フラグメント]**&#x200B;リストから目的の項目をクリックします。
1. フラグメントのプロパティから、[参照を探索](#explore-references)し、[そのアクセス権を管理](../administration/object-based-access.md)して、フラグメントの詳細を更新することができます。

   ![](assets/fragment-edit-content.png)

1. フラグメントをゼロから作成する場合と同様に、対応するボタンを選択してコンテンツを編集します。[詳細情報](#create-from-scratch)


>[!NOTE]
>
>フラグメントを編集すると、**[!UICONTROL ライブ]**&#x200B;ジャーニーまたはキャンペーンで使用するメールを除く、そのフラグメントを含むすべてのメールまたはテンプレートに変更が自動的に反映されます。また、元のフラグメントからの継承を解除することもできます。[詳細情報](#break-inheritance)

<!--Changes made to a fragment are not propagated to live journeys or campaigns where it is used.-->

<!--When added to an email, if you want to modify a fragment for a specific email, you can break the synchronization with the original fragment. The fragment becomes part of the email content and the changes will not be synchronized anymore. [Learn more](#break-inheritance)-->

### 参照の探索 {#explore-references}

フラグメントを現在使用しているジャーニー、キャンペーン、コンテンツテンプレートのリストを表示できます。

これを行うには、フラグメントリストの&#x200B;**[!UICONTROL その他のアクション]**&#x200B;メニューまたはフラグメントのプロパティ画面から「**[!UICONTROL 参照を探索]**」を選択します。

![](assets/fragment-explore-references.png)

タブを選択して、ジャーニー、キャンペーン、テンプレートを切り替えます。ステータスを確認し、名前をクリックすると、フラグメントが参照されている対応する項目にリダイレクトされます。

![](assets/fragment-usage-screen.png)

>[!NOTE]
>
>アクセスを妨げるラベルが付いているジャーニー、キャンペーン、テンプレートでフラグメントが使用されている場合、選択したタブの上部にアラートメッセージが表示されます。[オブジェクトレベルのアクセス制御（OLAC）について詳しくはこちらを参照してください](../administration/object-based-access.md)

### フラグメントのアーカイブ {#archive-fragments}

ブランドと関係がなくなった項目からフラグメントリストを削除できます。

これを行うには、目的のフラグメントの横にある「**[!UICONTROL その他のアクション]**」アイコンをクリックし、「**[!UICONTROL アーカイブ]**」を選択します。フラグメントリストから表示されなくなるので、今後のメールやテンプレートでユーザーはフラグメントを使用できなくなります。

![](assets/fragment-list-archive.png)

>[!NOTE]
>
>メールまたはコンテンツテンプレートで使用しているフラグメントをアーカイブしても、<!--it will remain in the email or template, but you won't be able to select it from the fragment list to edit it-->メールまたはテンプレートは影響を受けません。

フラグメントをアーカイブ解除するには、**[!UICONTROL アーカイブ済み]**&#x200B;項目をフィルタリングし、**[!UICONTROL その他のアクション]**&#x200B;メニューから「**[!UICONTROL アーカイブ解除]**」を選択します。これで、フラグメントリストから再びアクセスし、任意のメールまたはテンプレートで使用できるようになりました。

![](assets/fragment-list-unarchive.png)

## フラグメントの作成 {#create-fragments}

フラグメントの作成方法は 2 つあります。

* **[!UICONTROL フラグメント]**&#x200B;専用のメニューを使用して、フラグメントを最初から作成します。[方法についてはこちらを参照](#create-template-from-scratch)

* メールまたはコンテンツテンプレートをデザインする際は、コンテンツの一部をフラグメントとして保存します。[方法についてはこちらを参照](#save-as-template)

保存すると、フラグメントをジャーニー、キャンペーンまたはテンプレートで使用できるようになります。最初から作成した場合も、既存のコンテンツから作成した場合でも、このフラグメントを使用して、[!DNL Journey Optimizer] 内で[メール](get-started-email-design.md)または[コンテンツテンプレート](content-templates.md)を構築できるようになりました。[詳細情報](#use-fragments)

### ゼロから作成 {#create-from-scratch}

>[!CONTEXTUALHELP]
>id="ajo_create_fragment"
>title="独自のフラグメントの定義"
>abstract="スタンドアロンのフラグメントをゼロから作成して、複数のジャーニーやキャンペーンでコンテンツを再利用できるようにします。"

フラグメントをゼロから作成するには、次の手順に従います。

1. **[!UICONTROL コンテンツ管理]**／**[!UICONTROL フラグメント]**&#x200B;の左のメニューから、フラグメントリストにアクセスします。

1. 「**[!UICONTROL フラグメントを作成]**」を選択します。

1. フラグメントの詳細、名前や説明などを（必要に応じて）入力します。

   ![](assets/fragment-details.png)

   >[!NOTE]
   >
   >現在、**[!UICONTROL ビジュアルフラグメント]**&#x200B;タイプと&#x200B;**メール**&#x200B;チャネルのみがサポートされています。

1. カスタムまたはコアのデータ使用ラベルをフラグメントに割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。[オブジェクトレベルのアクセス制御（OLAC）についての詳細はこちらを参照してください](../administration/object-based-access.md)。

1. 「**[!UICONTROL 作成]**」をクリックします。

1. [メールデザイナー](get-started-email-design.md)が表示されます。ジャーニーやキャンペーン内のメールと同じ方法で、必要に応じてコンテンツを編集します。

   >[!NOTE]
   >
   >パーソナライゼーションフィールドと動的コンテンツを追加できますが、コンテキスト属性はフラグメントではサポートされていません。

   ![](assets/fragment-designer.png)

1. フラグメントの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。

1. 必要に応じて、フラグメント名の横にある矢印をクリックして&#x200B;**[!UICONTROL 詳細]**&#x200B;画面に戻り、フラグメントを編集します。

   ![](assets/fragment-designer-back.png)

このフラグメントは、[!DNL Journey Optimizer] 内で[メール](get-started-email-design.md)または[コンテンツテンプレート](content-templates.md)を作成する際に使用できるようになりました。[方法についてはこちらを参照](#use-fragments)

### フラグメントとして保存 {#save-as-fragment}

キャンペーンやジャーニーで[コンテンツテンプレート](content-templates.md)または[メール](get-started-email-design.md)をデザインする際、コンテンツの一部をフラグメントとして保存しておくと、後で再利用できます。それには、次の手順に従います。

1. [メールデザイナー](get-started-email-design.md)で、画面の右上にある「...」をクリックします。

1. ドロップダウンメニューから「**[!UICONTROL フラグメントとして保存]**」を選択します。

   ![](assets/fragment-save-as.png)

1. **[!UICONTROL フラグメントとして保存]**&#x200B;画面が表示されます。パーソナライゼーションフィールドや動的コンテンツなど、フラグメントに含める要素を選択します。コンテキスト属性は、フラグメントではサポートされていません。

   >[!CAUTION]
   >
   >互いに隣接するセクションのみを選択できます。空の構造や別のフラグメントは選択できません。

   ![](assets/fragment-save-as-screen.png)

1. 「**[!UICONTROL 作成]**」をクリックします。フラグメントの詳細、名前や説明などを（必要に応じて）入力します。

   ![](assets/fragment-details.png)

   >[!NOTE]
   >
   >現在、**[!UICONTROL ビジュアルフラグメント]**&#x200B;タイプと&#x200B;**メール**&#x200B;チャネルのみがサポートされています。

1. カスタムまたはコアのデータ使用ラベルをフラグメントに割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。[オブジェクトレベルのアクセス制御（OLAC）についての詳細はこちらを参照してください](../administration/object-based-access.md)。

1. 「**[!UICONTROL 作成]**」をもう一度クリックします。フラグメントは&#x200B;**[!UICONTROL フラグメント]**&#x200B;リストに保存され、[!DNL Journey Optimizer] 専用メニューからアクセスできます。

   このフラグメントは、そのリストの他の項目と同様に、[アクセス](#access-manage-fragments)、[編集](#edit-fragments)、[アーカイブ](#archive-fragments)できるスタンドアロンのフラグメントになります。

このフラグメントは、[!DNL Journey Optimizer] 内で[メール](get-started-email-design.md)または[コンテンツテンプレート](content-templates.md)を作成する際に使用できるようになりました。[方法についてはこちらを参照](#use-fragments)

>[!NOTE]
>
>その新しいフラグメントに対する変更は、送信元のメールまたはテンプレートには生成されません。同様に、そのメールまたはテンプレート内で元のコンテンツを編集しても、新しいフラグメントは変更されません。

## フラグメントの使用 {#use-fragments}

フラグメントは、ジャーニーまたはキャンペーン内の[メール](get-started-email-design.md)や、[コンテンツテンプレート](content-templates.md)で使用できます。

1. [メールデザイナー](get-started-email-design.md)を使用して、メールまたはテンプレートのコンテンツを開きます。

1. 左パネルから「**[!UICONTROL フラグメント]**」アイコンを選択します。

   ![](assets/fragments-in-designer.png)

1. 現在のサンドボックスで作成されたすべてのフラグメントのリストが表示されます。次のことができます。

   * ラベルの入力を開始して、特定のフラグメントを検索します。
   * フラグメントを昇順または降順に並べ替えます。
   * フラグメントの表示方法（カード表示またはリスト表示）を変更します。

1. また、リストを更新することもできます。

   >[!NOTE]
   >
   >コンテンツの編集中に一部のフラグメントが変更または追加された場合、リストは最新の変更内容で更新されます。

1. リストからフラグメントを挿入する領域にドラッグ＆ドロップします。

   ![](assets/fragment-insert.png)

1. 他のコンポーネントと同様に、コンテンツ内でフラグメントを移動できます。

1. フラグメントを選択すると、右側に対応するパネルが表示されます。ここから、コンテンツからフラグメントを削除したり、複製したりできます。また、これらのアクションは、フラグメントの上部に表示されるコンテキストメニューから直接実行することもできます。

   ![](assets/fragment-right-pane.png)

1. 「**[!UICONTROL 設定]**」タブから、次の操作を実行できます。

   * フラグメントを表示するデバイスを選択します。
   * 必要に応じて、新しいタブでフラグメントを開いて編集します。[詳細情報](#edit-fragments)
   * 参照を探索します。[詳細情報](#explore-references)

1. 「**[!UICONTROL スタイル]**」タブを使用して、フラグメントをさらにカスタマイズできます。

1. 必要に応じて、元のフラグメントの継承を解除できます。[詳細情報](#break-inheritance)

1. 必要な数のフラグメントを追加し、変更内容を&#x200B;**[!UICONTROL 保存]**&#x200B;します。

### 継承を解除 {#break-inheritance}

フラグメントを編集すると、変更内容が同期されます。これらは、そのフラグメントを含むすべての&#x200B;**[!UICONTROL ドラフト]**&#x200B;ジャーニー／キャンペーンおよびコンテンツテンプレートに自動的に生成されます。

>[!NOTE]
>
>変更内容は、**[!UICONTROL ライブ]**&#x200B;ジャーニーやキャンペーンで使用されるメールには生成されません。

メールまたはコンテンツテンプレートに追加すると、フラグメントはデフォルトで同期されます。

ただし、元のフラグメントからの継承を解除することはできます。フラグメントのコンテンツは現在のデザインにコピーされ、変更内容は同期されなくなります。

継承を解除するには、次の手順に従います。

1. フラグメントを選択します。

1. コンテキストツールバーのロック解除アイコンをクリックします。

   ![](assets/fragment-break-inheritance.png)

1. そのフラグメントは、元のフラグメントにリンクされなくなったスタンドアロン要素になります。コンテンツ内の他のコンテンツコンポーネントと同様に編集します。[詳細情報](content-components.md)

## チュートリアルビデオ {#video-fragments}

でフラグメントを管理、オーサリング、使用する方法について説明します。 [!DNL Journey Optimizer].

>[!VIDEO](https://video.tv.adobe.com/v/3419932/?quality=12)


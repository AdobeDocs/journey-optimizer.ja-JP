---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer でのコンテンツのゼロからのデザイン
description: メールコンテンツをゼロからデザインする方法を学ぶ
feature: Email Design
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: コンテンツ, エディター, メール, 開始
exl-id: 151594f2-85e4-4c79-9c15-334fbd3768c4
source-git-commit: 50491d039f2baf8c30a6af0c1b59fe9041244ac7
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---

# メールDesignerを使用したコンテンツのゼロからのデザイン {#content-from-scratch}

>[!CONTEXTUALHELP]
>id="ac_structure_components_email"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはメールのレイアウトを定義します。ドラッグ＆ドロップ&#x200B;**構造**&#x200B;コンポーネントをキャンバスに追加して、メールコンテンツのデザインを開始します。"

>[!CONTEXTUALHELP]
>id="ac_structure_components_landing_page"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはランディングページのレイアウトを定義します。**構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップして、ランディングページのコンテンツのデザインを開始します。"

>[!CONTEXTUALHELP]
>id="ac_structure_components_fragment"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはフラグメントのレイアウトを定義します。**構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップして、フラグメントのコンテンツのデザインを開始します。"

>[!CONTEXTUALHELP]
>id="ac_structure_components_template"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはテンプレートのレイアウトを定義します。**構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップして、テンプレートのコンテンツのデザインを開始します。"


>[!CONTEXTUALHELP]
>id="ac_edition_columns_email"
>title="メール列の定義"
>abstract="E メールデザイナーを使用すると、列構造を選択することで、メールのレイアウトを簡単に定義できます。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns_landing_page"
>title="ランディングページ列の定義"
>abstract="メールデザイナーでは、列構造を選択することで、ランディングページのレイアウトを簡単に定義できます。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns_fragment"
>title="フラグメント列の定義"
>abstract="メールデザイナーでは、列構造を選択義することで、フラグメントのレイアウトを簡単に定義できます。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns_template"
>title="テンプレート列の定義"
>abstract="メールデザイナーでは、列構造を選択することで、テンプレートのレイアウトを簡単に定義できます。"


Adobe Journey Optimizer Designer を使用して、コンテンツの構造を簡単に定義できます。単純なドラッグ＆ドロップ操作で構造要素を追加したり移動したりして、コンテンツの形を数秒でデザインすることができます。

コンテンツの作成を開始するには、次の手順に従います。

1. デザイナーのホームページで、「**[!UICONTROL ゼロからデザイン]**」オプションを選択します。

   ![](assets/email_designer.png)

1. **[!UICONTROL 構造]**&#x200B;をキャンバスにドラッグ＆ドロップしてコンテンツのデザインを開始し、メールのレイアウトを定義します。

   >[!NOTE]
   >
   >列の積み重ねは、すべてのメールプログラムと互換性があるわけではありません。サポートされていない場合、列は積み重ねられません。

   <!--Once placed in the email, you cannot move nor remove your components unless there is already a content component or a fragment placed inside. This is not true in AJO - TBC?-->

1. 必要に応じて&#x200B;**[!UICONTROL 構造]**&#x200B;を追加し、右側の専用パネルで設定を編集します。

   ![](assets/email_designer_structure_components.png)

   「**[!UICONTROL n:n 列]**」コンポーネントを選択して、列数（3～10）を任意に定義します。各列の下部にある矢印を動かして、各列の幅を定義することもできます。

   >[!NOTE]
   >
   >各列のサイズを構造コンポーネントの全幅の 10％未満にすることはできません。空でない列は削除できません。

1. 「**[!UICONTROL コンテンツ]**」セクションを展開し、必要な数の要素を 1 つ以上の構造コンポーネントに追加します。[詳しくは、コンテンツコンポーネントを参照してください](content-components.md)

1. 各コンポーネントは、右側のメニューの「**[!UICONTROL 設定]**」タブまたは「**[!UICONTROL スタイル]**」タブを使用してさらにカスタマイズできます。例えば、コンポーネントのテキストスタイル、パディングまたは余白を変更できます。[詳しくは、整列とパディングを参照してください](alignment-and-padding.md)

   ![](assets/email_designer_structure_component.png)

1. **[!UICONTROL アセットピッカー]**&#x200B;から、**[!UICONTROL Assets ライブラリ]**&#x200B;に保存されたアセットを直接選択できます。[詳しくは、アセット管理を参照してください](../integrations/assets.md)

   アセットを含むフォルダーをダブルクリックします。それらを構造コンポーネントにドラッグ＆ドロップします。

   ![](assets/email_designer_asset_picker.png)

1. パーソナライゼーションフィールドを挿入して、プロファイル属性、オーディエンスメンバーシップ、コンテキスト属性などからコンテンツをカスタマイズします。[詳しくは、コンテンツのパーソナライゼーションを参照してください](../personalization/personalize.md)

   ![](assets/email_designer_personalization.png)

1. 「**[!UICONTROL 条件付きコンテンツを有効にする]**」をクリックし、動的コンテンツを追加して、条件付きルールに基づいてコンテンツをターゲットプロファイルに適応させます。[動的コンテンツの基本を学ぶ](../personalization/get-started-dynamic-content.md)

   ![](assets/email_designer_dynamic-content.png)

1. 左側のペインから「**[!UICONTROL リンク]**」タブをクリックし、トラッキングするコンテンツのすべての URL を表示します。必要に応じて、**[!UICONTROL トラッキングタイプ]**、**[!UICONTROL ラベル]**&#x200B;を変更して、**[!UICONTROL タグ]**&#x200B;を追加できます。[詳しくは、リンクとトラッキングを参照してください](message-tracking.md)

   ![](assets/email_designer_links.png)

1. 必要に応じて、詳細メニューの「**[!UICONTROL コードエディターに切り替え]**」をクリックしてコードエディターに切り替え、メールをさらにパーソナライズできます。これにより、例えばトラッキングタグやカスタム HTML タグを追加するために、メールソースコードを編集できます。[詳しくは、コードエディターを参照してください](code-content.md)

   >[!CAUTION]
   >
   >コードエディターに切り替えた後で、このメールのビジュアルデザイナーに戻すことはできません。

1. コンテンツの準備が整ったら、「**[!UICONTROL コンテンツをシミュレート]**」ボタンをクリックしてレンダリングを確認します。デスクトップまたはモバイル表示を選択できます。テストプロファイルの選択およびコンテンツのプレビュー方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

   ![](assets/email_designer_simulate_content.png)

1. コンテンツの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。

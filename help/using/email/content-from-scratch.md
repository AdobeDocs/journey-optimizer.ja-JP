---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer でのメールのデザイン
description: メールコンテンツのデザイン方法について学ぶゼロから
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 151594f2-85e4-4c79-9c15-334fbd3768c4
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 50%

---

# ゼロから開始 {#content-from-scratch}

>[!CONTEXTUALHELP]
>id="ac_structure_components_email"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントはメールのレイアウトを定義します。"

>[!CONTEXTUALHELP]
>id="ac_structure_components_landing_page"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントはランディングページのレイアウトを定義します。"

>[!CONTEXTUALHELP]
>id="ac_structure_components_fragment"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントはフラグメントのレイアウトを定義します。"

>[!CONTEXTUALHELP]
>id="ac_structure_components_template"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントはテンプレートのレイアウトを定義します。"


>[!CONTEXTUALHELP]
>id="ac_edition_columns_email"
>title="メール列の定義"
>abstract="E メールデザイナーを使用すると、列構造を定義することで、メールのレイアウトを簡単に定義できます。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns_landing_page"
>title="ランディングページ列の定義"
>abstract="電子メールデザイナーを使用すると、列構造を定義することで、ランディングページのレイアウトを簡単に定義できます。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns_fragment"
>title="フラグメント列の定義"
>abstract="電子メールデザイナーを使用すると、列構造を定義することで、フラグメントのレイアウトを簡単に定義できます。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns_template"
>title="テンプレート列の定義"
>abstract="電子メールデザイナーを使用すると、列構造を定義することで、テンプレートのレイアウトを簡単に定義できます。"


E メールデザイナーを使用すると、メールの構造を簡単に定義できます。単純なドラッグ＆ドロップ操作で構造要素を追加したり移動したりして、メールの形を数秒でデザインすることができます。

E メールコンテンツの作成を開始するには、次の手順に従います。

1. 電子メールデザイナーのホームページで、「**[!UICONTROL ゼロからデザイン]**」オプションを選択します。

   ![](assets/email_designer.png)

1. ドラッグ&amp;ドロップで E メールコンテンツのデザインを開始 **[!UICONTROL 構造コンポーネント]** をキャンバスにドラッグして、e メールのレイアウトを定義します。

   >[!NOTE]
   >
   >列の積み重ねは、すべてのメールプログラムと互換性があるわけではありません。 サポートされていない場合、列は積み重ねられません。

   <!--Once placed in the email, you cannot move nor remove your components unless there is already a content component or a fragment placed inside. This is not true in AJO - TBC?-->

1. 追加する数 **[!UICONTROL 構造コンポーネント]** 必要に応じて、右側の専用パネルで設定を編集します。

   ![](assets/email_designer_structure_components.png)

   「**[!UICONTROL n:n 列]**」コンポーネントを選択して、選択する列数（3～10）を定義します。各列の下部にある矢印を動かして、各列の幅を定義することもできます。

   ![](assets/email_designer_structure_n-n-colum.png)

   >[!NOTE]
   >
   >各列のサイズを構造コンポーネントの全幅の 10％未満にすることはできません。空でない列は削除できません。

1. を展開します。 **[!UICONTROL コンテンツコンポーネント]** セクションを開き、必要な数の要素を 1 つ以上の構造コンポーネントに追加します。 [コンテンツコンポーネントの詳細を説明します](content-components.md)

1. 各コンポーネントは、 **[!UICONTROL コンポーネント設定]** 右側のパネル 例えば、各コンポーネントのテキストスタイル、パディングまたはマージンを変更できます。 [整列とパディングの詳細を表示](alignment-and-padding.md)

   ![](assets/email_designer_structure_component.png)

1. 次の **[!UICONTROL アセットピッカー]**&#x200B;を使用すると、 **[!UICONTROL アセットライブラリ]**. [アセット管理の詳細](assets-essentials.md)

   アセットを含むフォルダーをダブルクリックします。 構造コンポーネントにドラッグ&amp;ドロップします。

   ![](assets/email_designer_asset_picker.png)

1. パーソナライゼーションフィールドを挿入して、プロファイルデータからの E メールコンテンツをカスタマイズします。 [コンテンツのパーソナライゼーションの詳細](../personalization/personalize.md)

   ![](assets/email_designer_personalization.png)

1. 動的コンテンツを追加して、条件付きルールに基づいてコンテンツをターゲットプロファイルに適応させます。[動的コンテンツの基本を学ぶ](../personalization/get-started-dynamic-content.md)

   ![](assets/email_designer_dynamic-content.png)

1. 次をクリック： **[!UICONTROL リンク]** タブをクリックして、追跡するコンテンツのすべての URL を表示します。 これらの **[!UICONTROL トラッキングタイプ]** または **[!UICONTROL ラベル]** とを追加します。 **[!UICONTROL タグ]** 必要に応じて。 [リンクとメッセージトラッキングの詳細を説明します](message-tracking.md)

   ![](assets/email_designer_links.png)

1. 必要に応じて、「 」をクリックして E メールをさらにパーソナライズできます。 **[!UICONTROL コードエディターに切り替え]** を選択します。 [コードエディターの詳細を説明します](code-content.md)

   ![](assets/email_designer_switch-to-code.png)

   >[!CAUTION]
   >
   >コードエディターに切り替えた後で、この電子メールのビジュアルデザイナーに戻すことはできません。

1. コンテンツの準備が整ったら、「 **[!UICONTROL コンテンツをシミュレート]** 電子メールのレンダリングを確認する場合。 デスクトップまたはモバイル表示を選択できます。[メールのプレビューの詳細](preview.md)

   ![](assets/email_designer_simulate_content.png)

1. E メールの準備が整ったら、 **[!UICONTROL 保存]**.


---
solution: Journey Optimizer
product: journey optimizer
title: メールオーサリングエクスペリエンスの強化
description: 再利用可能なテーマとモジュールを使用してメールの作成を効率化し、キャンペーンのデザインの一貫性と効率性を確保する方法について説明します。
badge: label="ベータ版" type="Informative"
feature: Email Design
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: メールテーマ, モジュール, 再利用性, ブランドの一貫性, メールデザイン, カスタム CSS, モバイルの最適化
exl-id: e81d9634-bbff-44d0-8cd7-e86f85075c06
source-git-commit: abd5f388a41cc85c710cdb8c8e51c7fe381714ad
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 100%

---

# メールコンテンツへのテーマの追加 {#apply-email-themes}

>[!CONTEXTUALHELP]
>id="ajo_use_theme"
>title="メールへのテーマの適用"
>abstract="メールのテーマを選択して、ブランドやデザインに合った特定のスタイル設定をすばやく適用します。"

<!--This documentation provides a comprehensive guide to using themes to streamline your email creation process. With the ability to define reusable themes and leverage pre-designed modules, marketers can create professional, brand-aligned emails faster and with less effort.-->

>[!AVAILABILITY]
>
>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。

テーマを使用すると、技術ユーザー以外でも、標準テンプレートの上にカスタムスタイルを追加することで、特定のブランドやデザイン言語に適合する再利用可能なコンテンツを作成できます<!-- to achieve brand specific results-->。

この機能により、マーケターは、一意のデザインニーズに合わせた高度なカスタマイズオプションを提供しながら、視覚的に魅力的でブランドの一貫性のあるメールをより迅速かつ少ない労力で活用できます。

<!--What is the Enhanced Email Authoring Experience?

This feature introduces two key components to simplify and enhance email creation:

* **Theme Management System**: A centralized system for creating, customizing, and applying reusable themes to emails. Themes ensure consistent styling across campaigns and eliminate the need for repetitive manual styling.

* **Modules**: Pre-designed, reusable content blocks that abstract common email elements (e.g., titles, descriptions, images, and links). Modules are built using customizable low-level components, offering flexibility while maintaining design standards.

Key Benefits:

- **Consistency**: Ensure all emails align with your brand's design guidelines.
- **Efficiency**: Save time by reusing themes and modules across campaigns.
- **Customization**: Add custom CSS and mobile-specific styles for advanced designs.
- **Scalability**: Eliminate repetitive styling tasks, enabling faster email creation.-->

## ガードレールと制限 {#themes-guardrails}

* メールをゼロから作成する際に、ブランドやデザインに合った特定のスタイルをすばやく適用するには、テーマを使用してコンテンツの作成の開始を選択します。

  手動スタイルモードを選択した場合は、メールをリセットしない限り、テーマを適用できません。

* [フラグメント](../content-management/fragments.md)には、テーマを使用モードと手動スタイルモード間で相互互換性がありません。

  テーマが適用されるコンテンツでフラグメントを使用できるようにするには、このフラグメントをテーマを使用モードで作成する必要があります。

* HTML で作成されたコンテンツを使用する場合は、[互換性モード](existing-content.md)になり、このコンテンツにテーマを適用できません。

  テーマを含む E メールデザイナーのすべての機能を最大限に活用するには、テーマを使用モードで新しいコンテンツを作成するか、読み込んだ HTML コンテンツを変換する必要があります。[詳細情報](existing-content.md)

<!--If using a content created in Manual Styling mode or HTML, you cannot apply themes to this content. You must create a new content in Use Themes mode.

If you apply a theme to a content using a [fragment](../content-management/fragments.md) created in Manual Styling mode, the rendering may not be optimal.-->

## テーマの作成 {#create-and-edit-themes}

今後のメールコンテンツで活用できるテーマを定義するには、次の手順に従います。

1. まず、新しい[コンテンツテンプレート](../content-management/create-content-templates.md)を作成します。

1. 「**[!UICONTROL テーマを作成または編集]**」オプションを選択します。

   ![](assets/theme-create.png)

1. デフォルトのテーマを選択するか、アドビのテンプレートまたはカスタムテンプレートを使用できます。この例では、デフォルトのテーマを選択し、「**[!UICONTROL 作成]**」をクリックします。

   ![](assets/theme-select.png)

1. 「**[!UICONTROL 一般設定]**」タブで、ブランドに特定の名前を付けてテーマの定義を開始します。デフォルトのメールの幅を調整したり、現在のテーマを書き出して[サンドボックス間で共有](../configuration/copy-objects-to-sandbox.md)したりすることもできます。

   <!--![](assets/theme-general-settings.png)-->

1. 右側のパネルを使用して、様々なタブを移動し、デザイン設定を更新します。

   ![](assets/theme-right-pane.png)

1. 「**[!UICONTROL カラー]**」タブから、次の操作を行います。

   * 「**[!UICONTROL 編集]**」ボタンを使用して、ブランドのデフォルトカラーを含む&#x200B;**[!UICONTROL カラーパレット]**&#x200B;を設定します。**[!UICONTROL プリセット]**&#x200B;を選択して、カラースキームをすばやく作成するか、テーマの各カラーを個別に調整します。また、両方の組み合わせを使用することもできます。

     ![](assets/theme-colors.gif)

   * 「**[!UICONTROL バリアントを追加]**」をクリックして、ライトモードやダークモードなど、複数のカラーバリアントを作成します。各バリアントには、独自のカラーパレットとニュアンスコントロールがあります。

     ![](assets/theme-colors-variant.png)

   * 各バリアントに対して、編集アイコンをクリックして、個々の要素を編集します。作成したデフォルトのパレットや、任意のカスタムカラーを使用できます。

     ![](assets/theme-colors-edit-variant.gif)

1. **[!UICONTROL テキスト設定]**&#x200B;では、テーマ全体に使用するグローバルフォントを設定できます。より精度の高い制御を行うには、各見出しと段落のタイプを編集して、フォント、サイズ、スタイルなどを調整することもできます。

   ![](assets/theme-text.png)

1. 「**[!UICONTROL 間隔]**」タブで、リストから個々の要素を選択し、様々なコンポーネント間の間隔を適切に調整します。

   <!--![](assets/theme-spacing.png)-->

1. 右側の他のタブを使用すると、このテーマの各ボタン要素、ディバイダー、追加の画像書式設定、グリッドレイアウト間隔を個別に管理できます。

   <!--![](assets/theme-buttons.png)-->

1. 「**[!UICONTROL 保存]**」をクリックして、今後の使用のためにこのテーマを保存します。

## メールへのテーマの適用 {#apply-themes}

メールにデフォルトまたはカスタムのスタイルテーマを適用するには、次の手順に従います。

1. [!DNL Journey Optimizer] で、ジャーニーまたはキャンペーンに[メールアクションを追加](create-email.md)し、[メール本文を編集](get-started-email-design.md#key-steps)します。

1. 次のいずれかのアクションを選択できます。

   * ビルトインの[メールテンプレート](use-email-templates.md)を選択して、E メールデザイナーを開きます。各テンプレートに固有のデフォルトのテーマが自動的に適用されます。

   * [新しいコンテンツをゼロから](content-from-scratch.md)デザインし、「**[!UICONTROL テーマを使用]**」を選択して、定義済みのスタイルテーマから開始します。

     ![](assets/theme-from-scratch.png)

     >[!CAUTION]
     >
     >手動スタイルモードを選択した場合は、メールをリセットしない限り、テーマを適用できません。
     >
     >テーマを使用モードで[フラグメント](../content-management/fragments.md)を使用するには、このフラグメント自体がテーマを使用モードを使用して作成されている必要があります。

1. E メールデザイナーに移動したら、右側のパネルにある「**[!UICONTROL テーマ]**」ボタンをクリックします。デフォルトのテーマまたはテンプレートのテーマが表示されます。このテーマでは、2 つのカラーバリアントを切り替えることができます。

   ![](assets/theme-default-hero.png)

1. 現在使用しているテーマの横にある矢印をクリックします。使用可能なカスタムテーマとアドビテーマのリストが表示されます。

   ![](assets/theme-hero-change.png)

1. 「**[!UICONTROL カスタムテーマ]**」をクリックし、作成したテーマを選択します。

   ![](assets/theme-select-custom.png)

1. ドロップダウンリストの外側をクリックします。新しく選択したカスタムテーマのスタイルは、すべてのメールコンポーネントに自動的に適用されます。2 つのカラーバリアントを切り替えることができます。

1. コンポーネントを選択した場合でも、専用のアイコンを使用してこのスタイルをロック解除できます。

   ![](assets/theme-unlock-style.png)

テーマはいつでも切り替えることができます。メールコンテンツは変更されませんが、スタイルは新しいテーマを反映して更新されます。

<!--
>[!NOTE]
> - Themes apply styles globally. Ensure your theme is finalized before applying it to multiple emails.
> - Switching themes may override custom styles applied to individual components.

>[!CAUTION]
> - When using fragments, the email's theme will override the fragment's styles. A warning will be displayed in the editor if there is a conflict.

## Example Use Cases {#example-use-cases}

### 1. Creating a New Theme
- A marketer creates a theme with their brand's colors, fonts, and button styles.
- The theme is saved and reused across multiple email campaigns.

### 2. Switching Themes
- A marketer applies a holiday-themed design to an existing email by switching to a pre-designed holiday theme.-->

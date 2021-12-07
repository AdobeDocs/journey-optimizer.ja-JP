---
title: ランディングページのデザイン
description: Journey Optimizerでランディングページのコンテンツをデザインする方法を説明します
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
exl-id: c61b8d80-17e1-4fdd-a739-efcee032dc23
source-git-commit: 88b037e079a46e10f7ee4715e78e5edc5a34a6ce
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 3%

---

# ランディングページコンテンツのデザイン {#design-lp-content}

ランディング用のコンテンツの作成を開始するには [プライマリページ](create-lp.md#configure-primary-page) または [サブページ](create-lp.md#configure-subpages)をクリックし、プライマリページコンテンツにマウスポインターを置いて、 **[!UICONTROL Designer を開く]**. 右側のパレットで、対応するボタンをクリックすることもできます。

![](../assets/lp_open-designer.png)

ここから、次のことができます。

* **ランディングページをゼロからデザインする** コンテンツデザイナーのインターフェイスを通じて、 [Adobe Experience Manager Assets Essentials](../assets-essentials.md). コンテンツをデザインする方法、または組み込みテンプレートを使用する方法を説明します [この節](../create-email-content.md).

* **コードまたは生のHTMLを貼り付け** を直接コンテンツデザイナーに追加します。 独自のコンテンツの作成方法については、[iこの節](../existing-content.md#import-raw-html-code)を参照してください。

* ファイルまたは .zip フォルダーから&#x200B;**既存の HTML コンテンツを読み込み**&#x200B;ます。コンテンツのインポート方法を説明します [この節](../existing-content.md#import-html-content-from-file).

>[!NOTE]
>
>ランディングページのコンテンツデザイナーは、主に E メールのデザイナーと似ています。 詳細情報： [コンテンツのデザイン [!DNL Journey Optimizer]](../design-emails.md).

## ランディングページ固有のコンテンツを定義する {#define-lp-specific-content}

ユーザーが選択してランディングページから送信できるようにする特定のコンテンツを定義するには、次の手順に従います。

1. ランディングページ固有のをドラッグ&amp;ドロップします **[!UICONTROL フォーム]** 左側のパレットからメインのワークスペースにコンポーネントを追加します。

   ![](../assets/lp_designer-form-component.png)

   >[!NOTE]
   >
   >この **[!UICONTROL フォーム]** コンポーネントは、同じページで 1 回だけ使用できます。

1. 選択します。この **[!UICONTROL フォームコンテンツ]** タブが右側のパレットに表示され、フォームの様々なフィールドを編集できます。

   ![](../assets/lp_designer-form-content-options.png)

   >[!NOTE]
   >
   >次に切り替え： **[!UICONTROL フォームスタイル]** タブを使用して、フォームコンポーネントコンテンツのスタイルをいつでも編集できます。 [詳細情報](#define-lp-styles)

1. 次の **[!UICONTROL チェックボックス 1]** 「 」セクションでは、このチェックボックスに対応するラベルを編集できます。

1. このチェックボックスでユーザーのオプトイン/オプトアウトを行うかどうかを定義します。通信の受信に同意するか、それ以上連絡を希望しないか。

   ![](../assets/lp_designer-form-update.png)

1. 次の 3 つのオプションの間で、更新する項目を選択します。

   ![](../assets/lp_designer-form-update-options.png)

   * **[!UICONTROL 購読リスト]**:プロファイルがこのチェックボックスを選択した場合に更新される購読リストを選択する必要があります。 詳細情報： [購読リスト](subscription-list.md).

      ![](../assets/lp_designer-form-subs-list.png)

   * **[!UICONTROL チャネル（E メール）]**:オプトインまたはオプトアウトは、チャネル全体に適用されます。 例えば、オプトアウトするプロファイルに 2 つの E メールアドレスがある場合、両方のアドレスはすべてのコミュニケーションから除外されます。

   * **[!UICONTROL 電子メール ID]**:オプトインまたはオプトアウトは、ランディングページへのアクセスに使用した電子メールアドレスにのみ適用されます。 例えば、プロファイルに 2 つの E メールアドレスがある場合、オプトインに使用された電子メールアドレスのみがブランドからのコミュニケーションを受け取ります。

1. クリック **[!UICONTROL フィールドを追加]** > **[!UICONTROL チェックボックス]** 別のチェックボックスを追加する場合。 上記の手順を繰り返して、プロパティを定義します。

   ![](../assets/lp_designer-form-checkbox-2.png)

1. 必要なチェックボックスをすべて追加したら、 **[!UICONTROL コールトゥアクション]** をクリックして、対応するセクションを展開します。 これにより、 **[!UICONTROL フォーム]** コンポーネント。

   ![](../assets/lp_designer-form-call-to-action.png)

1. 「 」ボタンをクリックした場合の動作を定義します。

   * **[!UICONTROL リダイレクト URL]**:ユーザーのリダイレクト先となるページの URL を入力します。
   * **[!UICONTROL 確認テキスト]**:表示する確認テキストを入力します。
   * **[!UICONTROL サブページへのリンク]**:の設定 [サブページ](create-lp.md#configure-subpages) を選択し、表示されるドロップダウンリストから選択します。

   ![](../assets/lp_designer-form-confirmation-action.png)

1. エラーが発生した場合にボタンをクリックしたときの動作を定義します。

   * **[!UICONTROL リダイレクト URL]**:ユーザーのリダイレクト先となるページの URL を入力します。
   * **[!UICONTROL エラーテキスト]**:表示するエラーテキストを入力します。 エラーテキストは、 [フォームスタイル](#define-lp-styles).

   * **[!UICONTROL サブページへのリンク]**:の設定 [サブページ](create-lp.md#configure-subpages) を選択し、表示されるドロップダウンリストから選択します。

   ![](../assets/lp_designer-form-error.png)

1. フォームの送信時に追加の更新を行う場合は、 **[!UICONTROL オプトイン]** または **[!UICONTROL オプトアウト]**&#x200B;をクリックし、使用する E メールアドレスのみ、またはチャネルのサブスクリプションリストを更新するかを定義します。

   ![](../assets/lp_designer-form-additionnal-update.png)

1. コンテンツを保存し、ページ名の横の矢印をクリックして、 [ランディングページのプロパティ](create-lp.md#configure-primary-page).

   ![](../assets/lp_designer-form-save.png)

<!--Will the name Email Designer be kept if you can also design LP with the same tool? > To modify in Messages section > content designer or Designer-->

## ランディングページのフォームスタイルを定義 {#define-lp-styles}

1. フォームコンポーネントコンテンツのスタイルを変更するには、いつでも **[!UICONTROL フォームスタイル]** タブをクリックします。

   ![](../assets/lp_designer-form-style.png)

1. を展開します。 **[!UICONTROL チェックボックス]** 「 」セクションに追加し、チェックボックスと対応するテキストの外観を定義します。 例えば、フォントファミリーやサイズ、チェックボックスの境界線の色を調整できます。

   ![](../assets/lp_designer-form-style-checkboxes.png)

1. を展開します。 **[!UICONTROL ボタン]** 「 」セクションを使用して、コンポーネントフォーム内のボタンの外観を変更します。 例えば、ボーダーの追加、マウスポインターを置いたときのラベルの色の編集、ボタンの配置の調整を行うことができます。

   ![](../assets/lp_designer-form-style-buttons.png)

   ボタンのラベルの色など、設定の一部をプレビューするには、 **[!UICONTROL プレビュー]** 」ボタンをクリックします。 ランディングページのテストの詳細を説明します [ここ](create-lp.md#test).

   ![](../assets/lp_designer-form-style-buttons-preview.png)

1. を展開します。 **[!UICONTROL フォームレイアウト]** 「 」セクションを使用して、背景色、パディング、余白などのレイアウト設定を編集します。

   ![](../assets/lp_designer-form-style-layout.png)

1. を展開します。 **[!UICONTROL フォームエラー]** 「 」セクションを使用して、問題が発生した場合に表示されるエラーメッセージの表示を調整します。 フォーム上のエラーテキストをプレビューするには、対応するオプションをオンにします。

   ![](../assets/lp_designer-form-error-preview.png)


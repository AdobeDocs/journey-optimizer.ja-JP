---
title: ランディングページ固有のコンテンツの定義
description: Journey Optimizer でランディングページ固有のコンテンツをデザインする方法を説明します
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
exl-id: 5bf023b4-4218-4110-b171-3e70e0507fca
source-git-commit: f5e3b7cee816be420a09abd8aa9404faaccfec87
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 100%

---

# ランディングページ固有のコンテンツの定義 {#lp-content}

ユーザーがランディングページからオプションを選択および送信できる特定のコンテンツを定義するには、**[!UICONTROL フォーム]**&#x200B;コンポーネントを使用します。これを行うには、以下の手順に従います。

>[!NOTE]
>
>また、**[!UICONTROL フォーム]**&#x200B;コンポーネントを使用せずにクリックスルーのランディングページを作成することもできます。この場合、ランディングページはユーザーに表示されますが、フォームの送信には必要ありません。これは、オプトインやオプトアウトなど、受信者からのアクションを必要とせずにランディングページの表示のみを行う場合や、ユーザーによる入力が不要な情報を提供する場合に役立ちます。

## フォームコンポーネントの使用 {#use-form-component}

1. ランディングページ固有の&#x200B;**[!UICONTROL フォーム]**&#x200B;コンポーネントを左側のパレットからメインのワークスペースにドラッグ＆ドロップします。

   ![](assets/lp_designer-form-component.png)

   >[!NOTE]
   >
   >**[!UICONTROL フォーム]**&#x200B;コンポーネントは、同じページで 1 回だけ使用できます。

1. 選択します。「**[!UICONTROL フォームコンテンツ]**」タブが右側のパレットに表示され、フォームの様々なフィールドを編集できます。

   ![](assets/lp_designer-form-content-options.png)

   >[!NOTE]
   >
   >「**[!UICONTROL フォームスタイル]**」タブに切り替えると、フォームコンポーネントコンテンツのスタイルをいつでも編集できます。[詳細情報](#define-lp-styles)

1. 「**[!UICONTROL チェックボックス 1]**」セクションでは、このチェックボックスに対応するラベルを編集できます。

1. このチェックボックスでユーザーのオプトイン／オプトアウトを行うかどうかを定義します（お知らせの受信に同意する、または以降の連絡を望まない）。

   ![](assets/lp_designer-form-update.png)

   次の 3 つのオプションの中から選択します。

   * **[!UICONTROL オプトイン（オンにした場合）]**：ユーザーが同意するには、チェックボックスをオンにする必要があります（オプトイン）。
   * **[!UICONTROL オプトアウト（オンにした場合）]**：ユーザーが同意を削除するには、このチェックボックスをオンにする必要があります（オプトアウト）。
   * **[!UICONTROL オンにした場合はオプトインし、オフにした場合はオプトアウトします]**：このオプションを使用すると、オプトイン／オプトアウト用の 1 つのチェックボックスを挿入できます。ユーザーは、同意（オプトイン）するにはチェックボックスをオンにし、同意を削除（オプトアウト）するにはオフにする必要があります。

1. 次の 3 つのオプションの間で、更新する項目を選択します。

   ![](assets/lp_designer-form-update-options.png)

   * **[!UICONTROL 購読リスト]**：プロファイルがこのチェックボックスを選択した場合に更新される購読リストを選択する必要があります。詳しくは、[購読リスト](subscription-list.md)を参照してください。

      ![](assets/lp_designer-form-subs-list.png)

   * **[!UICONTROL チャネル（メール）]**：オプトインまたはオプトアウトは、チャネル全体に適用されます。例えば、オプトアウトするプロファイルに 2 つのメールアドレスがある場合、両方のアドレスはすべてのコミュニケーションから除外されます。

   * **[!UICONTROL メール ID]**：オプトインまたはオプトアウトは、ランディングページへのアクセスに使用したメールアドレスにのみ適用されます。例えば、プロファイルに 2 つのメールアドレスがある場合、ブランドからのお知らせはオプトインに使用されたメールアドレスにのみ届きます。

1. **[!UICONTROL フィールドを追加]**／**[!UICONTROL チェックボックス]**&#x200B;をクリックし、別のチェックボックスを追加します。上記の手順を繰り返して、プロパティを定義します。

   ![](assets/lp_designer-form-checkbox-2.png)

1. 必要なチェックボックスをすべて追加したら、「**[!UICONTROL コールトゥアクション]**」をクリックして、対応するセクションを展開します。これにより、**[!UICONTROL フォーム]**&#x200B;コンポーネントでボタンの動作を定義できるようになります。

   ![](assets/lp_designer-form-call-to-action.png)

1. ボタンをクリックしたときの動作を定義します。

   * **[!UICONTROL リダイレクト URL]**：ユーザーのリダイレクト先となるページの URL を入力します。
   * **[!UICONTROL 確認テキスト]**：表示する確認テキストを入力します。
   * **[!UICONTROL サブページへのリンク]**：[サブページ](create-lp.md#configure-subpages)を設定し、表示されるドロップダウンリストから選択します。

   ![](assets/lp_designer-form-confirmation-action.png)

1. エラーが発生した場合にボタンをクリックしたときの動作を定義します。

   * **[!UICONTROL リダイレクト URL]**：ユーザーのリダイレクト先となるページの URL を入力します。
   * **[!UICONTROL エラーテキスト]**：表示するエラーテキストを入力します。エラーテキストは、[フォームスタイル](#define-lp-styles)を定義する際にプレビューできます。

   * **[!UICONTROL サブページへのリンク]**：[サブページ](create-lp.md#configure-subpages)を設定し、表示されるドロップダウンリストから選択します。

   ![](assets/lp_designer-form-error.png)

1. フォームの送信時に追加の更新を行う場合は、「**[!UICONTROL オプトイン]**」または「**[!UICONTROL オプトアウト]**」を選択し、購読リスト、チャネル、または使用するメールアドレスのみを更新するかどうかを定義します。

   ![](assets/lp_designer-form-additionnal-update.png)

1. コンテンツを保存し、ページ名の横の矢印をクリックして、[ランディングページのプロパティ](create-lp.md#configure-primary-page)に戻ります。

   ![](assets/lp_designer-form-save.png)

<!--Will the name Email Designer be kept if you can also design LP with the same tool? > To modify in Messages section > content designer or Designer-->

## ランディングページのフォームスタイルを定義 {#lp-form-styles}

1. フォームコンポーネントコンテンツのスタイルを変更するには、いつでも「**[!UICONTROL フォームスタイル]**」タブに切り替えます。

   ![](assets/lp_designer-form-style.png)

1. 「**[!UICONTROL チェックボックス]**」セクションを展開し、チェックボックスと対応するテキストの外観を定義します。例えば、フォントファミリーやサイズ、チェックボックスの境界線の色を調整できます。

   ![](assets/lp_designer-form-style-checkboxes.png)

1. 「**[!UICONTROL ボタン]**」セクションを展開し、コンポーネントフォーム内のボタンの外観を変更します。例えば、境界線を追加したり、マウスポインターを置いたときのラベルの色を編集したり、ボタンの配置を調整したりできます。

   ![](assets/lp_designer-form-style-buttons.png)

   マウスポインターを置いたときにボタンのラベルの色などの設定の一部をプレビューするには、「**[!UICONTROL プレビュー]**」ボタンを使用します。ランディングページのテストについては、[こちら](create-lp.md#test-landing-page)を参照してください。

   ![](assets/lp_designer-form-style-buttons-preview.png)

1. 「**[!UICONTROL フォームレイアウト]**」セクションを展開し、背景色、パディング、余白などのレイアウト設定を編集します。

   ![](assets/lp_designer-form-style-layout.png)

1. 「**[!UICONTROL フォームエラー]**」セクションを展開し、問題が発生した場合に表示されるエラーメッセージの表示を調整します。フォーム上のエラーテキストをプレビューするには、対応するオプションをオンにします。

   ![](assets/lp_designer-form-error-preview.png)

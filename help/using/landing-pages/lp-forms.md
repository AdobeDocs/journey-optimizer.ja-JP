---
solution: Journey Optimizer
product: journey optimizer
title: ランディングページ用のフォームの作成と使用
description: Journey Optimizerでランディングページ用のフォームを作成して使用する方法を説明します
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
keywords: ランディング，ランディングページ，作成，ページ，フォーム
badge: label="限定提供" type="Informative"
hidefromtoc: true
hide: true
source-git-commit: 67283fe92282ce23c97c29fa2c0ad78132cc184a
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 4%

---

# ランディングページでのフォームの使用 {#lp-forms}

>[!AVAILABILITY]
>
>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。

[!DNL Journey Optimizer] ランディングページでプロファイルデータを取得し、[!DNL Experience Platform] データセットを強化するには、ランディングページでフォームを活用します。

## フォームプリセットの作成 {#create-form-preset}

>[!CONTEXTUALHELP]
>id="ajo_lp_form_connection"
>title="使用するエンドポイントを選択"
>abstract="フォーム送信時にデータが送信されるストリーミングエンドポイントを定義する。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="HTTP API ストリーミング接続の作成"

>[!CONTEXTUALHELP]
>id="ajo_lp_form_dataset"
>title="データセットの選択"
>abstract="フォームの応答を保存および反映するデータセットを定義します。 入力して特定のデータセットを検索するか、リストから選択できます。"

フォームを作成する前に、フォーム送信データを送信する接続エンドポイントと、フォームを通じて取り込まれたデータを保存するデータセットを選択する専用のプリセットを作成する必要があります。

ストリーミングエンドポイントにデータが到着すると、データセット情報とリンクされます。 生成されたソース/ターゲット接続とソースフローを使用して、データがデータセットにプッシュされます。

プリセットの作成時：

* データセットとストリーミング接続の異なる組み合わせを使用して、複数のプリセットを設定できます。
* 同じデータセットまたはストリーミング接続は、複数のプリセットで再利用できます。
* 各ストリーミング接続は、次のようなリソースを自動的に生成します。
   * **Source接続** - データの発信元。
   * **ターゲット接続** - データが格納または使用される場所です。
   * **Source フロー** - ソース接続から [!DNL Experience Platform] にデータを移動し、マッピング、変換および検証を処理するパイプラインです。

>[!NOTE]
>
> フォームプリセットにアクセスして編集するには、実稼動サンドボックスにおける **[!UICONTROL フォームプリセットの管理]** 権限が必要です。 権限について詳しくは、[ この節 ](../administration/high-low-permissions.md#administration-permissions).<!--TBC--> を参照してください

1. **[!UICONTROL フォームプリセット]** インベントリにアクセスするには、左のメニューから **[!UICONTROL 管理]**/**[!UICONTROL チャネル]**/**[!UICONTROL フォーム設定]** を選択します。

1. **[!UICONTROL フォームプリセットを作成]** をクリックします。

1. 名前を更新して取得しやすくし、必要に応じて説明を追加します。

   ![](assets/lp_create-form-preset.png){width=80%}

1. そのフォームに使用する **[!UICONTROL ストリーミング接続]** を選択します。 これは、フォームの送信時にデータが送信されるストリーミングエンドポイントです。

   >[!NOTE]
   >
   >ストリーミングソース接続の作成について詳しくは、[Experience Platform ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/streaming/http){target="_blank"} を参照してください。

1. フォームにリンクする **[!UICONTROL データセット]** を選択します。 ここで、フォームの応答が保存され、反映されます。 入力して特定のデータセットを検索するか、リストから選択できます。

   >[!NOTE]
   >
   >現在、[!DNL Adobe Experience Platform] 個のデータセットのみを選択できます。 一度に 1 つのデータセットのみを選択できます。

1. 「**[!UICONTROL 公開]**」をクリックします。これで、プリセットをフォームで使用できるようになります。

## フォームへのアクセスと管理 {#access-forms}

フォームリストにアクセスするには、左のメニューで **[!UICONTROL コンテンツ管理]**/**[!UICONTROL Forms]** を選択します。

既存のフォームがすべて表示されます。 ステータス、作成日、変更日に基づいてフォームをフィルタリングできます。

## フォームの作成とデザイン {#create-form}

>[!CONTEXTUALHELP]
>id="ajo_lp_form_preset"
>title="プリセットを選択"
>abstract="使用する接続を含む事前定義済みプリセットと、フォームの事前定義済みデータセットを選択します。"
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/landing-pages/lp-forms#create-form-preset" text="フォームプリセットの作成"

フォームを作成するには、次の手順に従います。

1. **[!UICONTROL Forms]** リストで、「**[!UICONTROL フォームを作成]**」をクリックします。

1. 名前を追加します。 必要に応じて、説明を追加できます。

   ![](assets/lp_create-form.png)

1. 使用する接続と、フォーム用に事前定義されたデータセットを含む **[!UICONTROL プリセット]** を選択します。 [ フォームプリセットの作成方法を学ぶ ](#create-form-preset)

1. 「**[!UICONTROL 作成]**」をクリックします。

   <!--![](assets/lp_create-form-filled.png){width=50%}-->

1. フォームデザイナーが開きます。 [ コンポーネント ](../email/content-components.md#add-content-components) を追加して、フォームコンテンツを作成します。 [ テキスト ](../email/content-components.md#text) コンポーネントと **[!UICONTROL フィールド]** コンポーネントを使用できます。

1. **[!UICONTROL フィールド]** コンポーネントを使用すると、選択したデータセットスキーマに基づいて属性を選択できます。

   >[!NOTE]
   >
   >収集したデータをプロファイルにマッピングするには、プロファイル ID フィールドを選択します。 属性リストから ID フィールドを識別するには、**[!UICONTROL 必須]**.<!--Explain--> とマークされたフィールドを探します

   例えば、メールとユーザー ID を設定できます。 ユーザーがこれらのフィールドに入力すると、入力した情報は選択したデータセットに保存されます。

   ![](assets/lp_create-form-fields.png)

1. 説明、デフォルト値、検証メッセージ、最大長など **[!UICONTROL 各]** フィールドの詳細」を指定できます。

   ![](assets/lp_create-form-field-details.png)

1. **[!UICONTROL スタイル]** パネルを使用して、必要に応じてフォームのレイアウト、スタイル設定および寸法を調整できます。 [ 詳しくは、スタイル設定を参照してください ](../email/get-started-email-style.md)

1. **[!UICONTROL 保存して閉じる]** をクリックします。

1. 「ありがとうございます」ページを設定します。 [詳細情報](#thank-you-page)

1. **[!UICONTROL 公開]** ランディングページで選択できるフォームです。

### 「ありがとうございます」ページの設定 {#thank-you-page}

>[!CONTEXTUALHELP]
>id="ajo_lp_forms_thankyou_page"
>title="「ありがとうございました」ページ"
>abstract="ユーザーがフォームに入力または転送したときの動作を設定します。"

「**[!UICONTROL ありがとうページ]**」セクションでは、ユーザーがフォームに入力したときの動作を設定します。

![](assets/lp_create-form-thank-you.png){width=70%}

次のいずれかのアクションを設定します。

* **[!UICONTROL ページを維持]** – このオプションを選択すると、フォームの送信時に訪問者が同じページに留まります。
* **[!UICONTROL ランディングページ]** - フォームの送信後にユーザーがリダイレクトされる公開済みの [ ランディングページ ](create-lp.md) を選択します。
* **[!UICONTROL 外部 URL]** - フォローアップページとして使用する完全な URL を入力します。 ユーザーがフォームを送信すると、指定した URL に移動します。
* **[!UICONTROL 条件付きリダイレクト]** - フォームの応答に基づいて異なるフォローアップアクションを動的に表示するルールを設定します。

  特定のオーディエンスごとにルールを定義できます。 例えば、米国居住者向けの特定のランディングページや、カナダ居住者向けの別のページなどを表示できます。 最後に、定義したルールに該当しないユーザーに対してデフォルトのアクションを設定します。

  >[!NOTE]
  >
  >ルール内で定義された条件が順番に読み取られます。

  ![](assets/lp_create-form-thank-you-conditional.png){width=40%}

## ランディングページでのフォームの活用 {#leverage-form-in-lp}

これで、このフォームをランディングページに埋め込み、フォームで定義した属性に対応するデータを取得し、選択したデータセットに保存できるようになりました。 次の手順に従います。

1. ランディングページを作成します。 [詳細情報](create-lp.md#create-landing-page)

1. ランディングページのタイプとして **[!UICONTROL データキャプチャ]** を選択し、**[!UICONTROL 作成]** をクリックします。

   ![](assets/lp_create-lp-data-capture.png){width=65%}

1. プライマリページを設定します。 [詳細情報](create-lp.md#configure-primary-page)

1. [ ランディングページデザイナー ](design-lp.md) を開きます。

1. **[!UICONTROL 構造コンポーネント]** をコンテンツにドラッグ&amp;ドロップします。 **[!UICONTROL フォーム]** コンポーネントをその構造にドラッグ&amp;ドロップします。

   >[!NOTE]
   >
   >ランディングページでは、公開済みのフォームのみを選択できます。

1. 「**[!UICONTROL 埋め込みフォーム]**」セクションで、作成したフォームを選択します。

   ![](assets/lp_embed-form.png)

   >[!NOTE]
   >
   >「**[!UICONTROL フォームを編集]** ボタンを使用して、選択したフォームを更新できます。 フォームが新しいタブで開きます。 フォームコンテンツの編集手順は、[ この節 ](#create-form) で説明する手順と同じです。

1. 「**[!UICONTROL フォローアップタイプ]**」セクションでは、ユーザーがフォームに入力したときの動作を設定します。

   * 「**[!UICONTROL フォーム定義]**」を選択して、埋め込みフォームで定義されたアクションを選択します。 [詳細情報](#thank-you-page)

   * フォームの送信後にユーザーがリダイレクトされる公開済みの [ ランディングページ ](create-lp.md) を選択することもできます。

   * または、ユーザーがフォームを送信したときに表示されるフォローアップページとして **[!UICONTROL 外部 URL]** を定義します。

1. ランディングページを保存してテストします。 [詳細情報](create-lp.md#test-landing-page)

ランディングページが [ 公開 ](create-lp.md#publish-landing-page) され、ジャーニーで使用されると、ユーザーがフォームに入力したときに、入力された情報は選択したデータセットに取り込まれます。

>[!NOTE]
>
>ランディングページで使用されているフォームを非公開にし、このフォームを編集して再度公開した場合、ランディングページでは常に、最新の公開済みバージョンのフォームが使用されます。

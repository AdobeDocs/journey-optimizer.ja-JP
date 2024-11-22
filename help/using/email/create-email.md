---
solution: Journey Optimizer
product: journey optimizer
title: メールの作成
description: Journey Optimizer でメールを作成する方法を学ぶ
feature: Email
topic: Content Management
role: User
level: Beginner
keywords: 作成, メール, 開始, ジャーニー, キャンペーン
exl-id: c77dc420-a375-4376-ad86-ac740e214c3c
source-git-commit: 03cb3298c905766bc059e82c58969a2111379345
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 95%

---

# メールの作成 {#create-email}

>[!CONTEXTUALHELP]
>id="ajo_message_email"
>title="メールの作成"
>abstract="メールの件名を定義し、メールデザイナーを開いてメールのコンテンツを作成します。"

## メールアクションの追加 {#email-action}

[!DNL Journey Optimizer] でメールを作成するには、**[!UICONTROL メール]**&#x200B;アクションをジャーニーまたはキャンペーンに追加します。次に、ケースに応じて、次の手順に従います。

>[!BEGINTABS]

>[!TAB ジャーニーへのメールの追加]

1. ジャーニーを開き、パレットの「**[!UICONTROL アクション]**」セクションから&#x200B;**[!UICONTROL メール]**&#x200B;アクティビティをドラッグ＆ドロップします。

1. メッセージに関する基本情報（ラベル、説明、カテゴリ）を入力します。

1. [メール設定](email-settings.md)を選択または作成します。

   ![](assets/email_journey.png)

   フィールドには、ユーザーがチャネルで使用した最後の設定がデフォルトで事前入力されます。

>[!NOTE]
>
>「送信時間の最適化」オプションを使用すると、メッセージの送信に最適な時間を予測し、過去の開封率とクリック率に基づいてエンゲージメントを最大化できます。詳しくは、[送信時間の最適化](../building-journeys/journeys-message.md#send-time-optimization)を参照してください。

ジャーニーの設定方法について詳しくは、[このページ](../building-journeys/journey-gs.md)を参照してください。

>[!TAB キャンペーンへのメールの追加]

1. スケジュール済みキャンペーンまたは API トリガーキャンペーンを新規作成し、アクションとして「**[!UICONTROL メール]**」を選択します。

1. キャンペーンプロパティ、[オーディエンス](../audience/about-audiences.md)、[スケジュール](../campaigns/create-campaign.md#schedule)など、メールキャンペーンを作成する手順を完了します。

   ![](assets/email_campaign_steps.png)

1. **[!UICONTROL メール]**&#x200B;アクションを選択します。

1. メール設定を選択または作成します。[詳細情報](email-settings.md)

   ![](assets/email_campaign.png)

<!--
From the **[!UICONTROL Action]** section, specify if you want to track how your recipients react to your delivery: you can track email opens, and/or clicks on links and buttons in your email.

![](assets/email_campaign_tracking.png)
-->

キャンペーンの設定方法について詳しくは、[このページ](../campaigns/get-started-with-campaigns.md)を参照してください。

>[!ENDTABS]

## メールコンテンツの定義 {#define-email-content}

<!-- update the quarry component with right ID value-->

>[!CONTEXTUALHELP]
>id="test_id"
>title="メールコンテンツの設定"
>abstract="メールのコンテンツを作成します。件名を定義してから、E メールデザイナーを活用してメールの本文を作成およびパーソナライズします。"

1. ジャーニーまたはキャンペーンの設定画面で、「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、メールコンテンツを設定します。[詳細情報](get-started-email-design.md)

   ![](assets/email_campaign_edit_content.png)

   **[!UICONTROL コンテンツを編集]**&#x200B;画面の「**[!UICONTROL ヘッダー]**」セクションで、「**[!UICONTROL 差出人名]**」、「**[!UICONTROL 差出人メールアドレス]**」、「**[!UICONTROL BCC]**」の各フィールドは、選択したメール設定で設定されます。[詳細情報](email-settings.md) <!--check if same for journey-->

   ![](assets/email_designer_edit_content_header.png)

1. メッセージの件名を追加します。パーソナライゼーションエディターを使用して件名を設定およびパーソナライズするには、「**[!UICONTROL パーソナライゼーションダイアログを開く]**」アイコンをクリックします。[詳細情報](../personalization/personalization-build-expressions.md)

1. 「**[!UICONTROL メール本文を編集]**」ボタンをクリックしてメールデザイナーにアクセスし、コンテンツの作成を開始します。[詳細情報](get-started-email-design.md)

   ![](assets/email_designer_edit_email_body.png)

1. キャンペーンで作業している場合は、「**[!UICONTROL コードエディター]**」ボタンをクリックし、表示されるポップアップウィンドウを使用してプレーン HTML で独自のコンテンツをコーディングすることもできます。

   ![](assets/email_designer_edit_code_editor.png)

   >[!NOTE]
   >
   >E メールデザイナーで既にコンテンツを作成または読み込んでいる場合は、そのコンテンツが HTML で表示されます。

## アラートの確認 {#check-email-alerts}

メッセージをデザインする際、重要な設定が見つからない場合は、インターフェイス（画面の右上）にアラートが表示されます。

![](assets/email_journey_alerts_details.png)

>[!NOTE]
>
>このボタンが表示されない場合、アラートは検出されていません。

システムでチェックされる設定と要素は以下のとおりです。また、設定を調整して対応する問題を解決する方法に関する情報もあります。

次の 2 種類のアラートが発生する可能性があります。

* **警告**&#x200B;は、次のようなレコメンデーションやベストプラクティスを示しています。

   * **[!UICONTROL メール本文にオプトアウトンクがありません]**：購読解除リンクをメール本文に追加するのがベストプラクティスです。設定方法について詳しくは、[この節](../privacy/opt-out.md#opt-out-management)を参照してください。

     >[!NOTE]
     >
     >マーケティングタイプのメールメッセージには、オプトアウトリンクを含める必要があります。これはトランザクションメッセージには必要ありません。メッセージカテゴリ（**[!UICONTROL マーケティング]**&#x200B;または&#x200B;**[!UICONTROL トランザクション]**）は、[チャネル設定](email-settings.md#email-type)レベルで、ジャーニーまたはキャンペーンから[メッセージの作成](#create-email-journey-campaign)時に定義されます。

   * **[!UICONTROL HTML のテキストバージョンが空です]**：メール本文のテキストバージョンを必ず定義してください。このバージョンは、HTML コンテンツを表示できない場合に使用されます。テキストバージョンの作成方法については、[この節](text-version-email.md)を参照してください。

   * **[!UICONTROL メールの本文に空のリンクが存在します]**：メール内のすべてのリンクが正しいことを確認します。コンテンツとリンクの管理方法については、[この節](content-from-scratch.md)を参照してください。

   * **[!UICONTROL メールのサイズが 100KB の制限を超えています]**：配信を最適化するには、メールのサイズが 100KB を超えないようにしてください。メールコンテンツの編集方法については、[この節](content-from-scratch.md)を参照してください。

* **エラー**（例えば次のようなもの）が解決されない限り、ジャーニー／キャンペーンのテストやアクティブ化はできません。

   * **[!UICONTROL 件名行がありません]**：電子メールの件名は必須です。定義およびパーソナライズの方法については、[この節](create-email.md)で説明します。

  <!--HTML is empty when Amp HTML is present-->

   * **[!UICONTROL メッセージの電子メールバージョンが空です]**：このエラーは、電子メールのコンテンツが設定されていない場合に表示されます。メールコンテンツの設計方法については、[この節](get-started-email-design.md)を参照してください。

   * **[!UICONTROL 設定が存在しません]**：選択した設定がメッセージの作成後に削除された場合は、メッセージを使用できません。このエラーが発生した場合は、メッセージ&#x200B;**[!UICONTROL プロパティ]**&#x200B;で別の設定を選択します。チャネル設定について詳しくは、[この節](../configuration/channel-surfaces.md)を参照してください。

>[!CAUTION]
>
>メールを使用してジャーニー／キャンペーンをテストまたはアクティブ化できるようにするには、すべての&#x200B;**エラー**&#x200B;アラートを解決する必要があります。

## メールの確認および送信

メッセージコンテンツを定義したら、テストプロファイルを使用してメッセージをプレビューし、配達確認を送信し、一般的なデスクトップ、モバイルおよび web ベースのクライアントでのレンダリングを制御できます。パーソナライズされたコンテンツを挿入した場合は、そのコンテンツがメッセージにどのように表示されるかを、テストプロファイルデータを使用して確認できます。

>[!NOTE]
>
>テストプロファイルに加えて、[!DNL Journey optimizer] では、コンテンツの様々なバリアントをプレビューし、CSV/JSON ファイルからアップロードされたサンプル入力データを使用して配達確認を送信するか、手動で追加することで、テストすることもできます。 [ サンプル入力データを使用してコンテンツをテストする方法を説明します ](../test-approve/simulate-sample-input.md)

これを行うには、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルを追加し、テストプロファイルデータを使用してメッセージを確認します。

![](assets/email_designer_edit_simulate.png)

テストプロファイルの選択およびコンテンツのプレビュー方法について詳しくは、[コンテンツ管理](../content-management/preview-test.md)の節を参照してください。

メールの準備ができたら、[ジャーニー](../building-journeys/journey-gs.md)または[キャンペーン](../campaigns/create-campaign.md)を設定し、アクティブ化して、メッセージが送信されるようにします。

>[!NOTE]
>
>メールの開封やインタラクションを通じて受信者の行動を追跡するには、ジャーニーの[メールアクティビティ](../building-journeys/journeys-message.md)またはメール[キャンペーン](../campaigns/create-campaign.md)で「**[!UICONTROL トラッキング]**」セクションの専用オプションが有効になっていることを確認してください。<!--to move?-->

<!--

## Define your email content {#email-content}

Use [!DNL Journey Optimizer] Email Designer to [design your email from scratch](../email/content-from-scratch.md). If you have an existing content, you can [import it in the Email Designer](../email/existing-content.md), or [code your own content](../email/code-content.md) in [!DNL Journey Optimizer]. 

[!DNL Journey Optimizer] comes with a set of [built-in templates](email-templates.md) to help you start. Any email can also be saved as a template.

Use [!DNL Journey Optimizer] personalization editor to personalize your messages with profiles' data. For more on personalization, refer to [this section](../personalization/personalize.md).

Adapt the content of your messages to the targeted profiles by using [!DNL Journey Optimizer] dynamic content capabilities. [Get started with dynamic content](../personalization/get-started-dynamic-content.md)

## Email tracking {#email-tracking}

If you want to track the behavior of your recipients through openings and/or clicks on links, enable the following options: **[!UICONTROL Email opens]** and **[!UICONTROL Click on email]**. 

Learn more about tracking in [this section](message-tracking.md).

## Validate your email content {#email-content-validate}

Control the rendering of your email, and check personalization settings with test profiles, using the preview section on the left-hand side. For more on this, refer to [this section](preview.md).

![](assets/messages-simple-preview.png)

You must also check alerts in the upper section of the editor.  Some of them are simple warnings, but others can prevent you from using the message. 

-->


---
solution: Journey Optimizer
product: journey optimizer
title: 多言語コンテンツの概要
description: Journey Optimizerの多言語コンテンツの詳細
feature: Multilingual Content
topic: Content Management
role: User
level: Beginner
keywords: 開始, 開始, コンテンツ, 実験
hide: true
hidefromtoc: true
source-git-commit: 90aeb777276e1e72c3099272f00e3700e06c83bf
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 4%

---

# 自動翻訳を使用した多言語コンテンツの作成 {#multilingual-automated}

>[!BEGINSHADEBOX]

**目次**

* [多言語コンテンツの概要](multilingual-gs.md)
* [手動翻訳を使用した多言語コンテンツの作成](multilingual-manual.md)
* **[自動翻訳を使用した多言語コンテンツの作成](multilingual-automated.md)**
* [多言語キャンペーンレポート](multilingual-report.md)

>[!ENDSHADEBOX]

自動フローを使用して、ターゲット言語と言語プロバイダーを簡単に選択できます。 その後、コンテンツが翻訳に直接送信され、完了時に最終レビューがおこなわれます。

自動翻訳を使用して多言語コンテンツを作成するには、次の手順に従います。

1. [ロケールを作成する](#create-locale).

1. [言語プロジェクトの作成](#create-translation-project).

1. [言語設定の作成](#create-language-settings).

1. [多言語キャンペーンの作成](#create-a-multilingual-campaign).

1. [翻訳タスクをレビュー（オプション）](#review-translation-project).

## ロケールを作成 {#create-locale}

言語設定を構成する際に、 [言語設定の作成](#language-settings) セクションでは、多言語コンテンツで特定のロケールが使用できない場合、を使用して必要な数の新しいロケールを柔軟に作成できます。 **[!UICONTROL 翻訳]** メニュー。

1. 次から： **[!UICONTROL 管理]** メニュー、アクセス **[!UICONTROL チャネル]**.

   翻訳メニューを使用すると、アクティベートされたロケールのリストにアクセスできます。

1. 次から： **[!UICONTROL ロケール辞書]** タブ、クリック **[!UICONTROL ロケールを追加]**.

   ![](assets/locale_1.png)

1. ロケールコードを **[!UICONTROL 言語]** リストおよび関連する **[!UICONTROL 地域]**.

1. クリック **[!UICONTROL 保存]** をクリックしてロケールを作成します。

   ![](assets/locale_2.png)

## 翻訳プロジェクトの作成 {#translation-project}

Target ロケールを指定し、コンテンツの特定の言語または地域を示して、翻訳プロジェクトを開始します。 その後、翻訳プロバイダーを選択できます。

1. 次から： **[!UICONTROL 翻訳プロジェクト]** 下のメニュー **[!UICONTROL コンテンツ管理]**&#x200B;をクリックし、 **[!UICONTROL プロジェクトを作成]**.

   ![](assets/translation_project_1.png)

1. Type-in a **[!UICONTROL 名前]** および **[!UICONTROL 説明]**.

1. を選択します。 **[!UICONTROL ソースのロケール]**.

   ![](assets/translation_project_2.png)

1. 承認後に翻訳を自動的に公開するかどうか、およびレビューワークフローを有効にするかどうかを選択します。

1. クリック **[!UICONTROL ロケールを追加]** をクリックしてメニューにアクセスし、翻訳プロジェクトの言語を定義します。

   次の場合、 **[!UICONTROL ロケール]** がない場合は、事前に **[!UICONTROL 翻訳]** メニューまたは API を使用します。 参照： [新しいロケールを作成](#create-locale).

   ![](assets/translation_project_3.png)

1. リストからを選択します。 **[!UICONTROL ターゲットのロケール]** を選択し、 **[!UICONTROL 翻訳プロバイダー]** 各ロケールでを使用します。

1. クリック **[!UICONTROL ロケールを追加]** Target ロケールと正しい翻訳プロバイダーのリンクを終了したとき。 次に、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/translation_project_4.png)

1. クリック **[!UICONTROL 保存]** 翻訳プロジェクトが設定されたとき。

これで、翻訳プロジェクトが作成され、多言語キャンペーンで使用できます。

## 言語設定の作成 {#language-settings}

この節では、多言語コンテンツを管理するためのプライマリ言語とそれに関連するロケールを設定できます。 また、プロファイル言語に関連する情報の検索に使用する属性を選択することもできます。

1. 次から： **[!UICONTROL 管理]** メニュー、アクセス **[!UICONTROL チャネル]**.

1. Adobe Analytics の **[!UICONTROL 言語設定]** メニュー、クリック **[!UICONTROL 言語設定の作成]**.

   ![](assets/language_settings_1.png)

1. 名前を入力 **[!UICONTROL 言語設定]**.

1. を選択します。 **[!UICONTROL 翻訳プロジェクト]** オプション。

1. 次から： **[!UICONTROL 翻訳プロジェクト]** 「 」フィールドで、「 **[!UICONTROL 編集]** を選択し、以前に作成した **[!UICONTROL 翻訳プロジェクト]**.

   以前に設定したロケールが自動的に読み込まれます。

   ![](assets/language_settings_2.png)

1. 次から： **[!UICONTROL 送信環境設定]** メニューで、検索する属性を選択して、プロファイル言語に関する情報を見つけます。

1. クリック **[!UICONTROL 編集]** 次に **[!UICONTROL ロケール]** さらにパーソナライズし、 **[!UICONTROL プロファイル環境設定]**.

   ![](assets/language_settings_3.png)

1. 次の場合、 **[!UICONTROL 翻訳プロジェクト]** が更新されました。「 **[!UICONTROL 更新]** これらの変更を **[!UICONTROL 言語設定]**.

   ![](assets/language_settings_4.png)

1. クリック **[!UICONTROL 送信]** をクリックして、 **[!UICONTROL 言語設定]**.

<!--
1. Access the **[!UICONTROL Channel surfaces]** menu and create a new channel surface or select an existing one.

1. In the **[!UICONTROL Header parameters]** section, select the **[!UICONTROL Enable multilingual]** option.

1. Select your **[!UICONTROL Locales dictionary]** and add as many as needed.
-->

## 多言語キャンペーンの作成 {#create-multilingual-campaign}

翻訳プロジェクトと言語の設定が完了したら、キャンペーンを作成し、様々なロケール用にコンテンツをカスタマイズする準備が整いました。

1. まず、要件に応じて、電子メール、SMS、またはプッシュ通知キャンペーンを作成し、設定します。 [詳細情報](../campaigns/create-campaign.md)

1. プライマリコンテンツを作成したら、「 **[!UICONTROL 保存]** キャンペーン設定画面に戻ります。

1. クリック **[!UICONTROL 言語を追加]**.  [詳細情報](#create-language-settings)

   ![](assets/multilingual-campaign-automated-1.png)

1. 以前に作成したを選択 **[!UICONTROL 言語設定]**.

   ![](assets/multilingual-campaign-automated-2.png)

1. ロケールが読み込まれたので、 **[!UICONTROL 翻訳に送信]** をクリックして、以前に選択した翻訳プロバイダーにコンテンツを転送します。

   ![](assets/multilingual-campaign-automated-3.png)

1. コンテンツを翻訳用に送信した後は、編集できなくなります。 元のコンテンツに変更を加えるには、ロックアイコンをクリックします。

   このコンテンツに変更を加える場合は、新しい翻訳プロジェクトを作成し、翻訳用に再送信する必要があります。

   ![](assets/multilingual-campaign-automated-4.png)

1. クリック **[!UICONTROL 翻訳を開く]** 翻訳プロジェクトにアクセスして確認するには、以下を実行します。

   ![](assets/multilingual-campaign-automated-5.png)

1. このページでは、翻訳プロジェクトのステータスに従います。

   * **[!UICONTROL 翻訳中]**：サービスプロバイダーが翻訳に積極的に取り組んでいます。
   * **[!UICONTROL レビューの準備完了]**：レビュープロセスを開始する準備が整い、翻訳にアクセスして拒否または承認できます。
   * **[!UICONTROL 確認済み]**：翻訳が承認され、キャンペーンに送信する準備が整いました。
   * **[!UICONTROL 公開準備完了]**：機械翻訳が完了し、キャンペーンに送信できるようになりました。
   * **[!UICONTROL 完了]**：キャンペーンで翻訳を利用できるようになりました。

   ![](assets/multilingual-campaign-automated-6.png)

1. 翻訳が完了すると、多言語コンテンツを送信する準備が整います。

   ![](assets/translation_review_9.png)

1. クリック **[!UICONTROL 有効化するレビュー]** ：キャンペーンの概要を表示します。

   概要では、必要に応じてキャンペーンを変更し、パラメーターが正しくないか、または見つからないかを確認できます。

1. 多言語コンテンツを参照して、各言語でのレンダリングを確認します。

   ![](assets/multilingual-campaign-automated-7.png)

1. キャンペーンが正しく設定されていることを確認してから、「**[!UICONTROL アクティブ化]**」をクリックします。

これで、キャンペーンがアクティブ化されました。キャンペーンに設定されたメッセージは、即座に送信されるか、指定した日付に送信されます。 キャンペーンがライブになると、すぐに変更できなくなります。 コンテンツを再利用するには、キャンペーンを複製します。

送信後は、キャンペーンレポート内でキャンペーンの影響を測定できます。

## 翻訳プロジェクトをレビュー {#review-translation-project}

次を選択した場合、 **[!UICONTROL レビューワークフローを有効にする]** の **[!UICONTROL 翻訳プロジェクト]**を使用すると、選択した翻訳プロバイダーによって、完了後にJourney Optimizerで直接翻訳をレビューできます。
このオプションが無効になっている場合、プロバイダーが翻訳を完了すると、翻訳タスクのステータスは自動的に「 」に設定されます。 **[!UICONTROL 確認済み]**&#x200B;をクリックすると、 **[!UICONTROL 製品に送信]**.

1. 翻訳がサービスプロバイダーから完了したら、翻訳にアクセスして、 **[!UICONTROL 翻訳プロジェクト]** または直接 **[!UICONTROL Campaign]**.

   ![](assets/translation_review_1.png)

1. レビューウィンドウから、翻訳済みコンテンツを参照し、各翻訳文字列を許可または却下します。

   ![](assets/translation_review_3.png)

1. クリック **[!UICONTROL 編集]** 翻訳文字列のコンテンツを変更する場合。

   ![](assets/translation_review_2.png)

1. 更新した翻訳を入力し、「 **[!UICONTROL 確認]** 終了したとき。

   ![](assets/translation_review_4.png)

1. また、 **[!UICONTROL すべて却下]** または **[!UICONTROL すべて承認]** を直接使用します。

   選択時 **[!UICONTROL すべて却下]**&#x200B;をクリックし、コメントを追加して、 **[!UICONTROL 拒否]**.

1. クリック **[!UICONTROL プレビュー]** をクリックして、各言語の翻訳済みコンテンツのレンダリングを確認します。

1. 翻訳が完了したら、「 **[!UICONTROL 最終化]**.

   ![](assets/translation_review_5.png)

1. お使いの **[!UICONTROL 翻訳プロジェクト]**」、プロジェクトの 1 つを選択して、詳細を表示します。 翻訳を拒否した場合は、翻訳に返信するように選択できます。

   ![](assets/translation_review_6.png)

1. 一度、 **[!UICONTROL 翻訳プロジェクト]** ステータスが「レビュー済み」に設定されている場合は、キャンペーンに送信できます。

   詳細設定メニューで、 **[!UICONTROL 公開]**.

   ![](assets/translation_review_7.png)

1. キャンペーンで、翻訳のステータスが **[!UICONTROL 翻訳完了]**. これで、多言語コンテンツを送信できます。手順 10 ( [この節](#create-multilingual-campaign).

   ![](assets/translation_review_9.png)

<!--
# Create a multilingual journey {#create-multilingual-journey}

1. Create your journey with a Delivery and personalize your content as needed.
1. From your delivery action, click Edit content.
1. Click Add languages.


-->

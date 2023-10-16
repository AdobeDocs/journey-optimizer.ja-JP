---
solution: Journey Optimizer
product: journey optimizer
title: 多言語コンテンツの概要
description: Journey Optimizerの多言語コンテンツの詳細
feature: Multilingual
topic: Content Management
role: User
level: Beginner
keywords: 開始, 開始, コンテンツ, 実験
hide: true
hidefromtoc: true
source-git-commit: 3b1acd7ada0637ce22e360e6e1bb35921dde2315
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 16%

---

# 多言語コンテンツの作成 {#multilingual-automated}

多言語機能を使用すると、1 つのキャンペーン内で複数の言語のコンテンツを容易に作成できます。 この機能を使用すると、キャンペーンの編集時に言語を切り替えたり、編集プロセス全体を合理化したり、多言語コンテンツを効率的に管理する機能を改善したりできます。

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

1. 次から： **[!UICONTROL 翻訳プロジェクト]** 下のメニュー **[!UICONTROL コンテンツ管理]**&#x200B;をクリックし、 **[!UICONTROL プロジェクトを作成]**.

1. Type-in a **[!UICONTROL 名前]** および **[!UICONTROL 説明]**.

1. を選択します。 **[!UICONTROL ソースのロケール]**.

1. 承認後に翻訳を自動的に公開するかどうか、およびレビューワークフローを有効にするかどうかを選択します。

1. クリック **[!UICONTROL ロケールを追加]** をクリックしてメニューにアクセスし、翻訳プロジェクトの言語を定義します。

   次の場合、 **[!UICONTROL ロケール]** がない場合は、事前に **[!UICONTROL 翻訳]** メニューまたは API を使用します。 参照： [新しいロケールを作成](#create-locale).

1. リストからを選択します。 **[!UICONTROL ターゲットのロケール]** を選択し、 **[!UICONTROL 翻訳プロバイダー]** 各ロケールでを使用します。

1. クリック **[!UICONTROL ロケールを追加]** Target ロケールと正しい翻訳プロバイダーのリンクを終了したとき。

1. クリック **[!UICONTROL 保存]** 翻訳プロジェクトが設定されたとき。

1. 翻訳プロジェクトの詳細設定メニューから、編集、非アクティブ化または削除を選択できます。

## 言語設定の作成 {#language-settings}

この節では、多言語コンテンツを管理するためのプライマリ言語とそれに関連するロケールを設定できます。 また、プロファイルの言語に関連する情報の検索に使用する属性を選択することもできます

1. 次から： **[!UICONTROL 管理]** メニュー、アクセス **[!UICONTROL チャネル]**.

1. Adobe Analytics の **[!UICONTROL 言語設定]** メニュー、クリック **[!UICONTROL 言語設定の作成]**.

1. 名前を入力 **[!UICONTROL 言語設定]**.

1. を選択します。 **[!UICONTROL 翻訳プロジェクト]** オプション。

1. 次から： **[!UICONTROL 翻訳プロジェクト]** 「 」フィールドで、「 **[!UICONTROL 編集]** を選択し、以前に作成した **[!UICONTROL 翻訳プロジェクト]**.

   以前に設定したロケールが自動的に読み込まれます。 次の場合に、 **[!UICONTROL 翻訳プロジェクト]**&#x200B;をクリックし、 **[!UICONTROL 更新]** これらの変更を **[!UICONTROL 言語設定]**.

1. 次から： **[!UICONTROL 送信環境設定]** メニューで、検索する属性を選択して、プロファイル言語に関する情報を見つけます。

1. クリック **[!UICONTROL 編集]** 次に **[!UICONTROL ロケール]** さらにパーソナライズし、 **[!UICONTROL プロファイル環境設定]**.

1. クリック **[!UICONTROL 送信]** をクリックして、 **[!UICONTROL 言語設定]**.

<!--
1. Access the **[!UICONTROL Channel surfaces]** menu and create a new channel surface or select an existing one.

1. In the **[!UICONTROL Header parameters]** section, select the **[!UICONTROL Enable multilingual]** option.

1. Select your **[!UICONTROL Locales dictionary]** and add as many as needed.
-->

## 多言語キャンペーンの作成 {#create-multilingual-campaign}

1. まず、要件に従ってキャンペーンを作成し、設定します。 [詳細情報](../campaigns/create-campaign.md)

1. 次に移動： **[!UICONTROL アクション]** メニューを開き、「 」を選択します。 **[!UICONTROL コンテンツを編集]**.

1. 元のコンテンツを作成または読み込み、必要に応じてパーソナライズします。

1. プライマリコンテンツを作成したら、「 **[!UICONTROL 保存]** キャンペーン設定画面に戻ります。

1. クリック **[!UICONTROL 言語を追加]** を選択し、以前に作成した **[!UICONTROL 言語設定]**. [詳細情報](#create-language-settings)

1. の詳細設定にアクセスする **[!UICONTROL ロケール]** メニューと選択 **[!UICONTROL プライマリをすべてのロケールにコピーする]**.

1. これで、選択した  **[!UICONTROL ロケール]**&#x200B;をクリックし、各ロケールにアクセスして、 **[!UICONTROL メール本文を編集]** コンテンツを翻訳します。

1. ロケールを無効にするか、有効にするかを選択すると、 **[!UICONTROL その他のアクション]** 選択したロケールのメニュー。

1. 多言語設定を非アクティブ化するには、 **[!UICONTROL 言語を追加]** ローカル言語として保持する言語を選択します。

1. クリック **[!UICONTROL 有効化するレビュー]** ：キャンペーンの概要を表示します。

   概要では、必要に応じてキャンペーンを変更し、パラメーターが正しくないか、または見つからないかを確認できます。

1. 多言語コンテンツを参照して、各言語でのレンダリングを確認します。

1. キャンペーンが正しく設定されていることを確認してから、「**[!UICONTROL アクティブ化]**」をクリックします。

これで、キャンペーンがアクティブ化されました。キャンペーンに設定されたメッセージは、即座に送信されるか、指定した日付に送信されます。 キャンペーンがライブになると、すぐに変更できなくなります。 コンテンツを再利用するには、キャンペーンを複製します。

送信後は、キャンペーンレポート内でキャンペーンの影響を測定できます。

## 多言語キャンペーンレポート {#multilingual-campaign-report}

「**全期間**」タブからアクセスできるグローバルレポートには、少なくとも 2 時間前に発生したイベントと、選択した期間のイベントが表示されます。キャンペーンのグローバルレポートへは、「**[!UICONTROL レポートを表示]**」ボタンを使用して、キャンペーンから直接アクセスできます。

キャンペーンレポートで使用可能なデータについて詳しくは、 [このページ](../reports/campaign-global-report.md).

+++多言語コンテンツで使用できる様々な指標およびウィジェットの詳細を説明します。

![](assets/report_multilingual.png)

The **[!UICONTROL 言語別の E メール送信統計]** ウィジェットは、 **[!UICONTROL ロケール]**:

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL バウンス]**：送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。

* **[!UICONTROL エラー]**：配信中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

The **[!UICONTROL 言語別の E メールトラッキング統計]** ウィジェットには、配信に使用できる受信者アクティビティ用のデータが含まれます。 **[!UICONTROL ロケール]**:

* **[!UICONTROL 配信停止]**：購読解除リンクのクリック数。

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

* **[!UICONTROL クリック数]**：コンテンツがクリックされた回数。
+++


<!--
# Create a multilingual journey {#create-multilingual-journey}

1. Create your journey with a Delivery and personalize your content as needed.
1. From your delivery action, click Edit content.
1. Click Add languages.


-->

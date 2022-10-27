---
title: アプリ内通知の作成
description: Journey Optimizerでアプリ内メッセージを作成する方法を説明します
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 9fc05acf695396814ecfaec7cc086b07a63d4afd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# アプリ内メッセージの作成 {#create-in-app}

## キャンペーンとアプリ内メッセージの作成{#create-in-app-in-a-campaign}

アプリ内メッセージを作成するには、次の手順に従います。

1. **[!UICONTROL キャンペーン]**&#x200B;メニューにアクセスし、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

1. 内 **[!UICONTROL プロパティ]** 「 」セクションで、いつキャンペーンを実行するかを指定します。

1. 内 **[!UICONTROL アクション]** セクションで、 **[!UICONTROL アプリ内メッセージ]** そして **[!UICONTROL アプリサーフェス]** アプリ内メッセージ用に事前設定済み。 次に、「**[!UICONTROL 作成]**」をクリックします。

   [アプリ内設定の詳細を説明します](inapp-configuration.md).

   ![](assets/in_app_create_1.png)

1. 次の **[!UICONTROL プロパティ]** セクションで、キャンペーンの **[!UICONTROL タイトル]** および **[!UICONTROL 説明]**.

1. ランディングページにカスタムデータ使用ラベルまたはコアデータ使用ラベルを割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。[詳細情報](../administration/object-based-access.md)。

1. 次をクリック： **[!UICONTROL オーディエンスを選択]** ボタンを使用して、使用可能なAdobe Experience Platformセグメントのリストからターゲットにするオーディエンスを定義します。 [詳細情報](../segment/about-segments.md)。

   ![](assets/in_app_create_2.png)

1. 「**[!UICONTROL ID 名前空間]**」フィールドで、選択したセグメントから個人を識別するために使用する名前空間を選択します。[詳細情報](../event/about-creating.md#select-the-namespace)。

1. アプリ内メッセージがアクティブな場合のトリガーの頻度を選択します。

   * **[!UICONTROL 毎回表示]**:イベントが **[!UICONTROL モバイルアプリトリガー]** ドロップダウンが発生します。
   * **[!UICONTROL 1 回表示]**:このメッセージは、 **[!UICONTROL モバイルアプリトリガー]** ドロップダウンが発生します。
   * **[!UICONTROL クリックスルーまで表示]**:このメッセージを、 **[!UICONTROL モバイルアプリトリガー]** ドロップダウンは、SDK が「クリック済み」のアクションと共にインタラクションイベントを送信するまで発生します。

1. 次の **[!UICONTROL モバイルアプリトリガー]** ドロップダウンで、メッセージをトリガーするイベントと条件を選択します。

   1. 左側のドロップダウンから、メッセージのトリガーに必要なイベントを選択します。
   1. 右側のドロップダウンから、選択したイベントに必要な検証を選択します。
   1. 次をクリック： **[!UICONTROL 追加]** ボタンを使用します。 次に、上記の手順を繰り返します。
   1. イベントのリンク方法を選択します ( 例： **[!UICONTROL および]** 望むなら **両方** トリガーを表示または選択するために true に設定する **[!UICONTROL または]** 次の場合にメッセージを表示する **どちらか** のトリガーが真です。

   ![](assets/in_app_create_3.png)

1. メッセージをトリガーするイベントを **[!UICONTROL モバイルアプリトリガー]**
」ドロップダウンリストから選択できます。

   トリガーを選択すると、アプリ内メッセージを表示するユーザーアクションを選択できます。

   ![](assets/in_app_create_3.png)

1. キャンペーンは、特定の日付に実行するか、定期的な頻度で実行するように設計されています。 設定方法を学ぶ **[!UICONTROL スケジュール]** の [この節](../campaigns/create-campaign.md#schedule).

   ![](assets/in-app-schedule.png)

1. これで、 **[!UICONTROL コンテンツを編集]** 」ボタンをクリックします。

   ![](assets/in_app_create_4.png)

## アプリ内メッセージの送信{#in-app-send}

### デバイスでプレビュー {#preview-device}

特定のデバイスでアプリ内通知をプレビューできます。

1. クリック **[!UICONTROL デバイスでプレビュー]**.

   ![](assets/in_app_create_6.png)

1. 次の **[!UICONTROL デバイスに接続]** ウィンドウ、クリック **[!UICONTROL 開始]**.

1. を **[!UICONTROL ベース URL]** 」と入力します。 **[!UICONTROL 次へ]**.

   ![](assets/in_app_create_7.png)

1. デバイスで QR コードをスキャンし、表示された PIN コードを入力します。

アプリ内メッセージをデバイスで直接トリガーできるようになり、実際のデバイスでメッセージをプレビューし、確認できます。

### アプリ内通知の確認とアクティブ化{#in-app-review}

アプリ内メッセージを作成し、そのコンテンツを定義してパーソナライズしたら、そのメッセージを確認してアクティブ化できます。

手順は次のとおりです。

1. 以下を使用： **[!UICONTROL 有効化するレビュー]** ボタンをクリックして、メッセージの概要を表示します。

   概要では、必要に応じてキャンペーンを変更し、パラメーターが正しくないか、または見つからないかを確認できます。

   ![](assets/in_app_create_5.png)

1. キャンペーンが正しく設定されていることを確認してから、「**[!UICONTROL アクティブ化]**」をクリックします。

これで、キャンペーンがアクティブ化されました。 キャンペーンに設定されているアプリ内通知は、即座に、または指定した日付に送信されます。

送信後は、キャンペーンレポート内でアプリ内メッセージの影響を測定できます。 レポートについて詳しくは、[この節](inapp-report.md)を参照してください。

**関連トピック：**

* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内レポート](inapp-report.md)
* [アプリ内設定](inapp-configuration.md)

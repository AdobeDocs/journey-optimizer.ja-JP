---
title: アプリ内通知の作成
description: Journey Optimizer で アプリ内メッセージを作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: アプリ内, メッセージ, 作成, 開始
exl-id: b3b79fe2-7db3-490d-9c3d-87267aa55eea
source-git-commit: 1af9a3adeb6727e965e61434b0ed2c41ff3d4911
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 51%

---

# アプリ内メッセージの作成  {#create-in-app}

アプリ内メッセージは、キャンペーンのコンテキストで作成されます。

アプリ内メッセージを作成するには、次の手順に従います。

1. **[!UICONTROL キャンペーン]**&#x200B;メニューにアクセスし、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

1. 内 **[!UICONTROL プロパティ]** 「 」セクションで、キャンペーンの実行タイプを次の中から選択します。スケジュール済みまたは API トリガー。 キャンペーンのタイプについて詳しくは、 [このページ](../campaigns/create-campaign.md#campaigntype).

1. 「**[!UICONTROL アクション]**」セクションで、**[!UICONTROL アプリ内メッセージ]**&#x200B;と、アプリ内メッセージにあらかじめ設定されている&#x200B;**[!UICONTROL アプリサーフェス]**&#x200B;を選択します。次に、「**[!UICONTROL 作成]**」をクリックします。

   アプリ内設定について詳しくは、 [このページ](inapp-configuration.md).

   ![](assets/in_app_create_1.png)

1. 次の **[!UICONTROL プロパティ]** セクションに、 **[!UICONTROL タイトル]** そして **[!UICONTROL 説明]** 説明。

1. アプリ内メッセージにカスタムまたはコアのデータ使用状況ラベルを割り当てるには、「 **[!UICONTROL アクセスを管理]**. [詳細情報](../administration/object-based-access.md)。

1. 「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform セグメントのリストからターゲットオーディエンスを定義します。 [詳細情報](../segment/about-segments.md)。

   ![](assets/in_app_create_2.png)

1. 「**[!UICONTROL ID 名前空間]**」フィールドで、選択したセグメントから個人を識別するために使用する名前空間を選択します。[詳細情報](../event/about-creating.md#select-the-namespace)。

1. クリック **[!UICONTROL 編集トリガー]** メッセージをトリガーするイベントと条件を選択するには：

   1. クリック **条件を追加** 複数のイベントや条件をトリガーで考慮する場合。
   1. イベントのリンク方法を選択します。例えば、メッセージを表示するために「**両方**」のトリガーを true にする場合は「**[!UICONTROL および]**」を選択し、トリガーの「**どちらか**」が true の場合にメッセージを表示する場合は「**[!UICONTROL または]**」を選択します。
   1. クリック **[!UICONTROL グループ化]** を使用して、トリガーをグループ化します。

   ![](assets/in_app_create_3.png)

1. アプリ内メッセージがアクティブな場合のトリガーの頻度を選択します。 次のオプションがあります。

   * **[!UICONTROL 毎回]**:イベントが **[!UICONTROL モバイルアプリトリガー]** ドロップダウンが発生します。
   * **[!UICONTROL 1 回]**:このメッセージは、 **[!UICONTROL モバイルアプリトリガー]** ドロップダウンが発生します。
   * **[!UICONTROL クリックスルーまで]**:このメッセージを、 **[!UICONTROL モバイルアプリトリガー]** ドロップダウンは、SDK が「クリック済み」のアクションと共にインタラクションイベントを送信するまで発生します。
   * **[!UICONTROL X 回]**:このメッセージを X 回表示します。

1. 必要に応じて、選択します **[!UICONTROL 曜日]** または **[!UICONTROL 時刻]** アプリ内メッセージが表示されます。

1. キャンペーンは、特定の日付に実行するか、繰り返し頻度で実行するように設計されています。キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/create-campaign.md#schedule)を参照してください。

   ![](assets/in-app-schedule.png)

1. これで、「**[!UICONTROL コンテンツを編集]**」ボタンでコンテンツのデザインを開始できます。[詳細情報](design-in-app.md)

   ![](assets/in_app_create_4.png)


## チュートリアルビデオ{#video}

以下のビデオでは、キャンペーンでアプリ内メッセージを作成、設定および公開する方法を示しています。

>[!VIDEO](https://video.tv.adobe.com/v/3410430?quality=12&learn=on)


**関連トピック：**

* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内メッセージのテストと送信](send-in-app.md)
* [アプリ内レポート](../reports/campaign-global-report.md#inapp-report)
* [アプリ内設定](inapp-configuration.md)
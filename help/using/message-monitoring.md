---
title: メッセージ実行の監視
description: 監視ガイドラインの詳細
source-git-commit: 3f02a5debbc870915175d2802eb30ff567a3c159
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 85%

---

# メッセージの監視{#monitor-message-execution}

![](assets/do-not-localize/badge.png)

メッセージが正常に実行、送信、配信されるように、[!DNL Journey Optimizer]オファー機能を使用して、現在公開およびトリガされているメッセージを監視します。 **[!UICONTROL 実行]**&#x200B;リストーから、ジャーニー<!--and APIs-->の間でメッセージがどのように実行されているかをリアルタイムで確認できます。

このリストにアクセスするには、**[!DNL Journey Optimizer]**&#x200B;ホームページか&#x200B;**[!UICONTROL メッセージ]**&#x200B;を選択し、**[!UICONTROL 実行]** tブをクリックします。

このタブには、2 つの表示があります。**[!UICONTROL ライブ表示]**&#x200B;と&#x200B;**[!UICONTROL グローバル表示]**&#x200B;です。

* **[!UICONTROL ライブ表示]**&#x200B;タブには、1つ以上の[ジャーニー](building-journeys/journey.md) **が過去24時間のみ**&#x200B;にトリガーし、実行されたすべてのメッセージ&#x200B;**の**&#x200B;リアルタイムの概要が表示されます。

   ![](assets/message-execution-tab-live.png)

   このリストは、60 秒ごとに自動更新されます。 特定のメッセージに対して過去 24 時間何も実行されなかった場合、すべての列にそのメッセージの null値 (0)が表示されます。

* **[!UICONTROL グローバル表示]** タブには、**メッセージ開始日以降**&#x200B;に 1 つ以上の[ジャーニー](building-journeys/journey.md)によってトリガーされ、**実行されたすべてのメッセージの概要** が表示されます。

   ![](assets/message-execution-tab-global.png)

   このリストは、90 分ごとに自動更新されます。 データは、各メッセージ開始日以降の時間にわたって集計されます。

ジャーニーが発行したが、まだトリガーしていないメッセージは、どのタブにも表示されません。 次の要素のみが表示されます。
* トリガーされたが、まだ開始されていない（保留中の）メッセージ。
* トリガーされ、現在実行中のメッセージ。

<!--For multichannel messages, one row per channel is displayed for each message. STILL VALID? looks like NOT-->

>[!NOTE]
>
>メッセージが複数のジャーニーで使用されている場合、各実行につき1行が表示されます。

<!--![](assets/message-execution-multichannel.png)-->

<!--If a message has been used in several journeys, the **[!UICONTROL Source]** column displays **[!UICONTROL Multiple]**.-->

デフォルトでは、メッセージは最新の実行日から表示されます。Click the **[!UICONTROL フィルター]** アイコンをクリックし、チャネル、開始日、終了日に従ってメッセージを検索します。

![](assets/message-execution-tab-filters.png)

2番目の列では、対応する [メッセージ](create-message.md) を開くことができ、**[!UICONTROL ライブビュー]**&#x200B;の場合は[ライブレポート](reports/live-report.md)に&#x200B;**[!UICONTROL グローバルビュー]**&#x200B;の場合は[グローバルレポート](reports/global-report.md) にアクセスできます。

![](assets/message-execution-open-live-report.png)

メッセージの実行ごとに、次の数のインジケーターが表示されます。

* **[!UICONTROL メッセージラベル]**: メッセージの [作成時に定義したメッセージのタイトル](create-message.md)。自動的に生成される実行IDは括弧で囲まれて表示されます。

   <!--**[!UICONTROL Execution ID]**: Automatically generated identifier.
  **[!UICONTROL Source]**: Name of the journey leveraging that message.-->

* **[!UICONTROL ジャーニー — バージョン — アクション]**:メッセージを活用するジャーニーの名前、ジャーニーのバージョン、ジャーニー内のメッセージを活用するアクションのラベル。

* **[!UICONTROL ステータス]**:メッセージの実行ステータス。  <!--List all the possible statuses? For now only Live status? The user cannot stop or cancel the execution. TBC by Fred-->

* **[!UICONTROL 開始日]**：ジャーニーからメッセージが実行された日時。

   <!--Targeted: Number of targeted profiles for each message execution. To come?-->

* **[!UICONTROL 除外]**: 除外ルールによって初期ターゲットから除外されたプロファイルの数です。

* **[!UICONTROL 送信済み]**: 送信されたメッセージの数。

* **[!UICONTROL 配信済み]**: バウンスやその他の配信エラーを生成せずに、受信者のメールボックス（電子メール）またはデバイス（プッシュ）に正常に配信されたメッセージの数。

* **[!UICONTROL バウンス]**: 配信エラーが発生したため配信できないメッセージの数。[バウンスの詳細を表示します](suppression-list.md)。

* **[!UICONTROL 開封数]**: 開かれたメッセージの数。

* **[!UICONTROL クリック数]** : 電子メール内のリンクのクリック数。

   >[!NOTE]
   >
   >プッシュ通知にはクリックはありません。ユーザがプッシュ通知をクリックすると、アプリが開きます。アプリは開いていると見なされるだけです。

* **[!UICONTROL エラー]** : 技術的なエラーが原因で送信できないメッセージの数です。

* **[!UICONTROL スパムの苦情]**:受信者によってスパムとマークされたメッセージの数。[苦情の詳細](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html?lang=ja#metrics-for-deliverability)。

各ハイパーリンクをクリックすると、対応するメッセージの概要表示が開きます。 [メッセージの詳細](create-message.md)。

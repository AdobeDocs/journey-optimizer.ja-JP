---
title: メッセージの実行の監視
description: 監視のガイドラインを確認する
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# メッセージの監視{#monitor-message-execution}

![](assets/do-not-localize/badge.png)

メッセージが正常に実行、送信、配信されるように、[!DNL Journey Optimizer]オファー機能を使用して、現在公開およびトリガされているメッセージを監視します。 **[!UICONTROL 実行]**&#x200B;リストーから、ジャーニー<!--and APIs-->の間でメッセージがどのように実行されているかをリアルタイムで確認できます。

このリストにアクセスするには、**[!DNL Journey Optimizer]**&#x200B;ホームページから「**[!UICONTROL メッセージ]**」を選択し、「**[!UICONTROL 実行]**」タブをクリックします。

このタブには2つの表示があります。**[!UICONTROL ライブ表示]**&#x200B;と&#x200B;**[!UICONTROL グローバル表示]**。

* 「**[!UICONTROL ライブ表示]**」タブには、1つ以上の[ジャーニー](building-journeys/journey.md) **が過去24時間のみ**&#x200B;にトリガーした、実行されたすべてのメッセージ&#x200B;**の**&#x200B;リアルタイムの概要が表示されます。

   ![](assets/message-execution-tab-live.png)

   このリストは、60秒ごとに自動更新されます。 特定のメッセージに対して過去24時間何も実行されなかった場合、すべての列にそのメッセージのnull値(0)が表示されます。

* 「**[!UICONTROL グローバル表示]**」タブは、1つ以上の[ジャーニー](building-journeys/journey.md) **によってトリガされた、実行されたすべてのメッセージ**&#x200B;の概要を&#x200B;**提供します。**

   ![](assets/message-execution-tab-global.png)

   このリストは、90分ごとに自動更新されます。 データは、各メッセージ開始日以降の時間にわたって集計されます。

ジャーニーが発行したが、まだトリガーしていないメッセージは、どのタブにも表示されません。 次の要素のみが表示されます。
* トリガーされたが、まだ開始されていない（保留中の）メッセージ。
* トリガーされ、現在実行中のメッセージ。

マルチチャンネルメッセージの場合、チャネルごとに1行が表示されます。

![](assets/message-execution-multichannel.png)

メッセージが複数のジャーニーで使用されている場合、**[!UICONTROL Source]**&#x200B;列には&#x200B;**[!UICONTROL Multiple]**&#x200B;と表示されます。

デフォルトでは、メッセージは最新の実行日から表示されます。 **[!UICONTROL フィルター]**&#x200B;アイコンをクリックし、チャネル、開始日、終了日に従ってメッセージを検索します。

![](assets/message-execution-tab-filters.png)

2番目の列は、対応する[メッセージ](create-message.md)を開き、**[!UICONTROL ライブ表示]**&#x200B;にいる場合は[ライブレポート](reports/live-report.md)に、[グローバル表示](reports/global-report.md)にアクセスできます。>.****

![](assets/message-execution-open-live-report.png)

メッセージの実行ごとに、次の数のインジケーターが表示されます。

* **[!UICONTROL メッセージラベル]**:メッセージの [作成時に定義したメッセージのタイトル](create-message.md)。
* **[!UICONTROL 実行ID]**:自動的に生成された識別子。
* **[!UICONTROL ソース]**:そのメッセージを活用しているジャーニーの名前。
* **[!UICONTROL 開始日]**:ジャーニーからメッセージが実行された日時。
* **[!UICONTROL 除外]**:除外ルールによって初期ターゲットから除外されたプロファイルの数です。
* **[!UICONTROL 送信済み]**:送信されたメッセージの数。
* **[!UICONTROL 配信済み]**:バウンスやその他の配信エラーを生成せずに、受信者のメールボックス（電子メール）またはデバイス（プッシュ）に正常に配信されたメッセージの数です。
* **[!UICONTROL バウンス]**:配信エラーが発生したため配信できないメッセージの数です。[バウンスの詳細を表示します](suppression-lists.md#delivery-failures)。
* **[!UICONTROL 開く]**:開かれたメッセージの数。
* **[!UICONTROL クリック数]**:電子メール内のリンクのクリック数。

   >[!NOTE]
   >
   >プッシュ通知のクリックが存在しない：ユーザーがプッシュ通知をクリックすると、アプリが開きます。これは、開いていると見なすことのみ可能です。

* **[!UICONTROL エラー]**:技術的なエラーが原因で送信できないメッセージの数です。

各ハイパーリンクをクリックすると、対応するメッセージの概要表示が開きます。 [メッセージの詳細](create-message.md)。

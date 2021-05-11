---
title: 開始ジャーニーの実行
description: ジャーニーを開始し、メッセージを送信する方法を説明します
translation-type: tm+mt
source-git-commit: 4ff255b6b57823a1a4622dbc62b4b8886fd956a0
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# ジャーニーの実行{#message-execution}

![](../assets/do-not-localize/badge.png)

## ジャーニーのテスト

テストプロファイルを使用してジャーニーをテストできます。 設定とメッセージを検証する場合は、この手順を実行することをお勧めします。

詳しくは、[この節](testing-the-journey.md)を参照してください。

## ジャーニーのアクティベート

ジャーニーを公開してアクティブ化する必要があります。

![](../assets/jo-journeyuc2_32bis.png)

詳しくは、[この節](publishing-the-journey.md)を参照してください。


公開したら、専用のレポートツールを使用してジャーニーを監視し、ジャーニーの有効性を測定できます。

![](../assets/jo-dynamic_report_journey_12.png)

[レポートの詳細](../reports/live-report.md)

## メッセージの送信 {#send-messages}

メッセージにコンテンツが定義され、公開されると、[ジャーニー](journey.md)を介して送信できる状態になります。

>[!NOTE]
>
>ドラフトモードのメッセージをジャーニーに追加することはできますが、ジャーニーを公開する前に、メッセージが公開されていることを確認してください。

メッセージが送信されたら、複数のインジケーターを使用してメッセージの実行を監視できます。 [メッセージの実行の監視の詳細を表示します](../message-monitoring.md)。

## スケジュールメッセージ{#schedule-messages}

メッセージは、[ジャーニー](journey.md)の&#x200B;**[!UICONTROL セグメント]**&#x200B;を読むアクティビティを通じてスケジュールできます。 セグメントがジャーニーに入るタイミングを指定できます。 [セグメントアクティビティを読む](read-segment.md)。

これを行うには、以下の手順に従います。

1. ジャーニーを編集し、**[!UICONTROL セグメント]**&#x200B;を読み取りアクティビティと開始をドラッグ&amp;ドロップして設定します。 [「セグメントアクティビティを読む](read-segment.md#configuring-segment-trigger-activity)」の設定についての詳細。

1. 「**[!UICONTROL ジャーニースケジュール]**&#x200B;を編集」リンクをクリックして、ジャーニーのプロパティにアクセスします。

   ![](../assets/message-read-segment-schedule.png)

1. **[!UICONTROL スケジューラータイプ]**&#x200B;フィールドを設定します。リストから目的の値を選択し、特定の日時または定期的にセグメントがジャーニーに入るようにします。

   >[!NOTE]
   >
   >**[!UICONTROL スケジュール]**&#x200B;セクションは、**[!UICONTROL セグメントの読み取り]**&#x200B;アクティビティがキャンバスにドロップされた場合にのみ使用できます。

   ![](../assets/message-read-segment-scheduler.png)

1. 「**[!UICONTROL 1回]**」を選択した場合は、セグメントがジャーニーを入力する日時を定義します。

   ![](../assets/message-read-segment-scheduler-once.png)

1. 定期的な方法を選択した場合は、開始の日時を編集します。 オプションで終了日時を定義することもできます。

   ![](../assets/message-read-segment-scheduler-daily.png)

   >[!NOTE]
   >
   >デフォルトでは、セグメントはジャーニー&#x200B;**[!UICONTROL できるだけ早く]**&#x200B;に入ります。つまり、ジャーニーが公開されてから1時間後になります。

1. 「**[!UICONTROL OK]**」をクリックして変更を保存します。

<!--Unitary messages that are triggered by an event within a journey cannot be scheduled.-->

---
title: メッセージの公開と変更
description: メッセージを公開および更新する方法について学ぶ
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 116e2223-a806-4f68-9a8c-c0bde6008010
source-git-commit: b43e3432ede1d4985e0a6b57b57c5efc3cf60c50
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 83%

---

# メッセージの公開 {#publish-manage-messages}

## メッセージを公開する {#publish-message}

メッセージを作成したら、実行できるよう公開することができます。

>[!CAUTION]
>
>公開する前に、アラートを確認して解決します。[詳細情報](alerts.md)

![](assets/publish-message.png)

メッセージが公開されると、**[!UICONTROL 公開中のアイテム]**&#x200B;ステータスでメッセージリストに追加されます。

これで、1 つ以上の[ジャーニー](../building-journeys/journey.md)によってトリガーされる準備が整いました。

>[!NOTE]
>
>公開されたメッセージ内で直接または間接的に参照されるオファー、フォールバックオファー、オファーコレクション、またはオファーの決定を更新する場合、再公開する必要なく、更新内容が対応するメッセージに自動的に反映されるようになりました。 [オファーの詳細を表示](../offers/get-started/starting-offer-decisioning.md)

## 読み取り専用メッセージの更新 {#modify-message}

公開後、メッセージは読み取り専用モードになります。そのメッセージの新しいドラフトを作成して、更新することはできます。

これにより、メッセージが使用されているジャーニー全体を再度公開しなくても、コンテンツを更新したり、問題を修正することができます。

>[!NOTE]
>
>公開済みバージョンが公開され、アクティブとなっていても、ドラフトバージョンは編集できます。

公開済みメッセージを更新するには：

1. メッセージリストからメッセージを選択して開きます。

1. 「**[!UICONTROL 変更]**」をクリックします。

   ![](assets/message-modify.png)

1. 選択内容を確認します。メッセージのドラフトバージョンが作成されます。

   ![](assets/message-modify-v2.png)

1. 必要に応じて、コンテンツを編集するか、設定を変更します。
1. 「**[!UICONTROL 公開]**」をクリックします。このアクションにより、次回の実行に使用される新しいバージョンのメッセージが公開されます。

新しいバージョンが公開されるとすぐ、次回の API 呼び出し時に新しいメッセージ実行が生成されます。次回の受信プロファイルは、新しいバージョンを受け取ります。

<!--For batch messages, the audience/segment being processed in the previous execution will not be affected by the new version. Only the next incoming API call with an audience/segment will generate a new message execution with the new version. -->

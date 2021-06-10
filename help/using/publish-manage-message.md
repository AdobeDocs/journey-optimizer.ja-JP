---
title: メッセージの公開と変更
description: メッセージを公開および更新する方法について学ぶ
snippet: y
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: ht
source-wordcount: '219'
ht-degree: 100%

---

# メッセージを公開 {#publish-manage-messages}

![](assets/do-not-localize/badge.png)

## メッセージを公開する {#publish-message}

メッセージを作成したら、実行できるよう公開することができます。

>[!CAUTION]
>
>公開する前に、アラートを確認して解決します。[詳細情報](alerts.md)。

![](assets/publish-message.png)

メッセージが公開されると、**[!UICONTROL 公開中のアイテム]**&#x200B;ステータスでメッセージリストに追加されます。

これで、1 つ以上の[ジャーニー](building-journeys/journey.md)によってトリガーされる準備が整いました。

## 読み取り専用メッセージの更新{#modify-message}

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

<!--For batch messages, the audience/segment being processed in the previous execution will not be affected by the new version. Only the next incoming API call with an audience/segment will generate a new message execution with the new version.-->

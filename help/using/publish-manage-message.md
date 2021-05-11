---
title: メッセージの発行と変更
description: メッセージを公開および更新する方法について説明します。
snippet: y
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 3%

---

# メッセージを公開{#publish-manage-messages}

![](assets/do-not-localize/badge.png)

## メッセージを発行{#publish-message}

メッセージを作成したら、発行して実行可能にすることができます。

>[!CAUTION]
>
>発行する前に、アラートを確認して解決します。 [詳細情報](alerts.md).

![](assets/publish-message.png)

メッセージが発行されると、**[!UICONTROL 発行済み]**&#x200B;ステータスでメッセージリストに追加されます。

これで、1つ以上の[ジャーニー](building-journeys/journey.md)によってトリガされる準備ができました。

## 読み取り専用メッセージの更新{#modify-message}

発行後、メッセージは読み取り専用モードになります。 そのメッセージの新しいドラフトを作成して、更新することはできます。

これにより、メッセージが使用されているジャーニー全体を再公開することなく、コンテンツの更新や問題の修正が可能になります。

>[!NOTE]
>
>ドラフトバージョンは、公開済みバージョンが公開されアクティブな間は編集できます。

発行済みメッセージを更新するには：

1. メッセージリストからメッセージを選択して開きます。

1. 「**[!UICONTROL 変更]**」をクリックします。

   ![](assets/message-modify.png)

1. 選択内容を確認します。メッセージのドラフトバージョンが作成されます。

   ![](assets/message-modify-v2.png)

1. 必要に応じて、コンテンツを編集するか、設定を変更します。
1. 「**[!UICONTROL パブリッシュ]**」をクリックします。このアクションは、次の実行に使用される新しいバージョンのメッセージを発行します。

新しいバージョンが公開されるとすぐに、次のAPI呼び出し時に、新しいメッセージ実行が生成されます。 次の受信プロファイルは、新しいバージョンを受け取ります。

<!--For batch messages, the audience/segment being processed in the previous execution will not be affected by the new version. Only the next incoming API call with an audience/segment will generate a new message execution with the new version.-->

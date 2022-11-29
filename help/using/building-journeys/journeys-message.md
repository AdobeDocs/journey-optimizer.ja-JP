---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーへのメッセージの追加
description: ジャーニーにメッセージを追加する方法を説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 4db07a9e-c3dd-4873-8bd9-ac34c860694c
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 73%

---

# メール、SMS、プッシュ{#add-a-message-in-a-journey}

[!DNL Journey Optimizer] には、組み込みのメッセージ機能が付属しています。 ジャーニーにプッシュ、SMS またはメールのメッセージアクティビティを追加し、[設定とコンテンツを定義](../messages/messages-in-journeys.md)するだけです。その後、メッセージアクティビティがジャーニーのコンテキストで実行および送信されます。

また、メッセージを送信する特定のアクションを設定することもできます。

* サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを作成できます。詳しくは、[この節](../action/action.md)を参照してください。

* Campaign と Journey Optimizer を連携させる場合は、次の節を参照してください。

   * [[!DNL Journey Optimizer] と Campaign Classic v7／Campaign v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] と Campaign Standard](../action/acs-action.md)

ジャーニーにメッセージを追加するには、次の手順に従います。

1. ジャーニーを「[イベント](general-events.md)」または「[セグメントを読み取り](read-segment.md)」アクティビティで開始します。

1. パレットの「**アクション**」セクションで、**メール**、**SMS** または **プッシュ**&#x200B;アクティビティをキャンバスに追加します。

   ![](../messages/assets/add-a-message.png)


   メッセージを設定し、そのコンテンツを定義するすべての手順について詳しくは、[この節](../messages/get-started-content.md)を参照してください。

## ライブコンテンツを更新{#update-live-content}

ライブジャーニーでメッセージのコンテンツ（E メール、SMS、プッシュ）を更新できます。

これをおこなうには、ライブジャーニーを開き、メッセージアクティビティを選択して、 **コンテンツを編集**.

![](assets/add-a-message2.png)

ただし、プロファイル属性かコンテキストデータ（イベントプロパティまたはジャーニープロパティから）かにかかわらず、パーソナライゼーションで使用される属性は変更できません。

---
title: IP プールの作成
description: 「IP プール管理方法を学ぶ」
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: アプリケーション設定
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

---


# IP プールの作成

## IP プールについて

Journey Optimizer では、IP プールを作成して、サブドメインの IP アドレスをグループ化できます。

E メールの配信品質を高めるには、IP プールの作成を強くお勧めします。 これにより、サブドメインの評判が他のサブドメインに影響を与えるのを防ぐことができます。

例えば、マーケティングメッセージ用に 1 つの IP プールを用意し、トランザクションメッセージ用に別の IP プールを用意することをお勧めします。 こうすることで、あるマーケティングメッセージが上手くいかず、顧客によってスパムと指定された場合でも、この顧客に送信されるトランザクションメッセージ（購入確認、パスワード回復メッセージなど）には影響しません。

## IP プールの作成

IP プールを作成するには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL IP プール]**&#x200B;メニューにアクセスし、**[!UICONTROL IP プールの作成]**&#x200B;をクリックします。

   ![](../assets/ip-pool-create.png)

1. IP プールの名前と説明（オプション）を入力します。

   >[!NOTE]
   >
   >サブドメインの名前は文字（A～Z）で始め、英数字または特殊文字（_, ., - ）のみを使用してください。

1. プールに含める IP アドレスをドロップダウンリストから選択し、「**[!UICONTROL 送信]**」をクリックします。

   ![](../assets/ip-pool-config.png)

   >[!NOTE]
   >
   >インスタンスでプロビジョニングされた IP アドレスがすべてリストに表示されます。

IP プールが作成され、リストに表示されます。 選択してプロパティにアクセスし、関連するメッセージプリセットを表示することができます。 メッセージプリセットと IP プールを関連付ける方法の詳細は、[この節](message-presets.md))を参照してください。

![](../assets/ip-pool-created.png)

IP プールを編集するには、IP プールを開き、必要に応じてそのプロパティを編集します。

>[!NOTE]
>
>メッセージプリセットが IP プールに関連付けられている場合は、まず IP プールを編集する前に削除する必要があります。 変更を完了すると、メッセージプリセットを再度関連付けることができます。

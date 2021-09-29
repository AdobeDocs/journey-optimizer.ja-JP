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
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 606334c3-e3e6-41c1-a10e-63508a3ed747
source-git-commit: 7d7c1b72530d99b8cceb1067f2576ad66c0052a6
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 39%

---

# IP プールの作成

## IP プールについて {#about-ip-pools}

Journey Optimizer では、IP プールを作成して、サブドメインの IP アドレスをグループ化できます。

E メールの配信品質を高めるには、IP プールの作成を強くお勧めします。 これにより、サブドメインの評判が他のサブドメインに影響を与えるのを防ぐことができます。

例えば、マーケティングメッセージ用に 1 つの IP プールを用意し、トランザクションメッセージ用に別の IP プールを用意することをお勧めします。 この方法では、マーケティングメッセージのパフォーマンスが正しくなく、顧客によってスパムと宣言された場合でも、この顧客に送信されるトランザクションメッセージには影響を与えません（購入確認、パスワード回復メッセージなど）。

## IP プールの作成 {#create-ip-pool}

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

IPプールが作成され、リストに表示されます。 選択してプロパティにアクセスし、関連するメッセージプリセットを表示することができます。 メッセージプリセットと IP プールを関連付ける方法の詳細は、[この節](message-presets.md))を参照してください。

![](../assets/ip-pool-created.png)

## IPプールの編集 {#edit-ip-pool}

IPプールを編集するには：

1. リストで、IPプール名をクリックして開きます。

   ![](../assets/ip-pool-list.png)

1. 必要に応じて、プロパティを編集します。 説明を変更したり、IPアドレスを追加または削除したりできます。

   ![](../assets/ip-pool-edit.png)

   >[!CAUTION]
   >
   >IPの削除を検討する際は、別途注意が必要です。これにより、他のIPに負荷がかかり、配信品質に重大な影響が及ぶ場合があるからです。 不明な点がある場合は、配信品質のエキスパートにお問い合わせください。

1. 変更を保存します。

>[!NOTE]
>
>IPプール名は編集できません。 変更する場合は、IPプールを削除し、別のIPプールを任意の名前で作成する必要があります。

更新は、[メッセージプリセット](message-presets.md)に関連付けられているIPプールに応じて、即時または非同期で有効になります。

* IPプールがメッセージプリセットで選択されていない&#x200B;****&#x200B;の場合、更新は即時（**[!UICONTROL 成功]**&#x200B;ステータス）になります。
* IPプール&#x200B;**が**&#x200B;メッセージプリセットで選択されている場合、更新には最大7～10営業日（**[!UICONTROL 処理]**&#x200B;ステータス）かかる場合があります。

<!--If a message preset has been associated with the IP pool, you first need to remove it before editing the IP pool. Once the your modifications have been done, you can associate the message preset again.-->

IPプールの更新状態を確認するには、「**[!UICONTROL その他のアクション]**」ボタンをクリックし、「**[!UICONTROL 最近の更新]**」を選択します。

![](../assets/ip-pool-recent-update.png)

>[!NOTE]
>
>IPプールが正常に更新されたら、次の処理を待つ必要がある場合があります。
>* 単一のメッセージで消費される数分前
>* は、IPプールの次のバッチがバッチメッセージで有効になるまで。


**[!UICONTROL Delete]**&#x200B;ボタンを使用してIPプールを削除することもできます。 メッセージプリセットに関連付けられているIPプールは削除できません。


---
title: IPプールの作成
description: 「ipプールの管理方法の詳細」
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
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---


# IPプールの作成

## IPプールについて

Journey Optimizerでは、IPプールを作成して、サブドメインのIPアドレスをグループ化できます。

Eメールの配信品質を高めるには、IPプールの作成を強くお勧めします。 これにより、サブドメインのレピュテーションが他のサブドメインに影響を与えるのを防ぐことができます。

例えば、マーケティングメッセージ用に1つのIPプールを用意し、トランザクションメッセージ用に別のIPプールを用意することをお勧めします。 この方法では、マーケティングメッセージのパフォーマンスが正しくなく、顧客によってスパムと宣言された場合でも、この顧客に送信されるトランザクションメッセージには影響しません（購入確認、パスワード回復メッセージなど）。

## IPプールの作成

IPプールを作成するには、次の手順に従います。

1. **[!UICONTROL チャネル]** / **[!UICONTROL IPプール]**&#x200B;メニューにアクセスし、**[!UICONTROL IPプールを作成]**&#x200B;をクリックします。

   ![](../assets/ip-pool-create.png)

1. IPプールの名前と説明（オプション）を入力します。

   >[!NOTE]
   >
   >サブドメインの名前は文字(A ～ Z)で始まり、英数字または特殊文字( _ 、 . 、 - )のみを含める必要があります。

1. プールに含めるIPアドレスをドロップダウンリストから選択し、「**[!UICONTROL 送信]**」をクリックします。

   ![](../assets/ip-pool-config.png)

   >[!NOTE]
   >
   >インスタンスでプロビジョニングされたIPアドレスがすべてリストに表示されます。

IPプールが作成され、リストに表示されます。 選択してプロパティにアクセスし、関連するメッセージプリセットを表示できます。 メッセージプリセットとIPプールを関連付ける方法について詳しくは、[この節](message-presets.md)を参照してください。

![](../assets/ip-pool-created.png)

IPプールを編集するには、IPプールを開き、必要に応じてそのプロパティを編集します。

>[!NOTE]
>
>メッセージプリセットがIPプールに関連付けられている場合は、まずIPプールを編集する前に削除する必要があります。 変更が完了したら、メッセージプリセットを再度関連付けることができます。

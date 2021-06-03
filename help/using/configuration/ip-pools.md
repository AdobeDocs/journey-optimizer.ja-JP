---
title: IPプールの作成
description: xxxxの方法を説明します
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
source-git-commit: 2d8b7bbaee7509d4cc33445c64b2382ed14a9678
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

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

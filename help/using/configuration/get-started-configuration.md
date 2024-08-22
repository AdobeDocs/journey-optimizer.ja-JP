---
solution: Journey Optimizer
product: journey optimizer
title: ' [!DNL Journey Optimizer]  設定の概要'
description: ' [!DNL Journey Optimizer]  設定について説明します。'
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
keywords: 設定,メッセージ,チャネル,サンドボックス,Optimizer
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 95%

---


# [!DNL Journey Optimizer] 設定の基本を学ぶ {#start-optimizer-configuration}

[!DNL Journey Optimizer]に初めてアクセスする際には、実稼動用サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。

ジャーニーを作成しメッセージを送信するには、次の設定手順を完了する必要があります。

## メッセージとチャネルの設定

1. メッセージを作成して送信するには、チャネルに応じて特定の設定を行う必要があります。

   * **メール**&#x200B;チャネルの場合は、サブドメインをアドビにデリゲートし、IP プールを作成して IP アドレスをグループ化する必要があります。[詳細情報](../email/get-started-email-config.md)

   * **プッシュ**&#x200B;チャネルの場合は、[!DNL Adobe Experience Platform] と [!DNL Adobe Experience Platform Launch] の両方でプッシュ通知設定を定義する必要があります。[詳細情報](../push/push-configuration.md)

   * **SMS** チャネルの場合は、プロバイダー設定を [!DNL Journey Optimizer] と統合するなど、SMS を送信するようにインスタンスを設定する必要があります。[詳細情報](../sms/sms-configuration.md)

1. 完了したら、**チャネル設定** を作成して、メッセージの配信に必要なすべての技術的パラメーターを設定する必要があります。 [詳細情報](channel-surfaces.md)

1. 以下を行うこともできます。

   * 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。[詳細](manage-suppression-list.md)

   * **メールの BCC オプション**&#x200B;を有効にして、個人に送信されたメッセージのコピーを保持します。[詳細情報](archiving-support.md#enable-bcc)

   * **ビジネスルール**&#x200B;を設定して、受信者を過度に勧誘しないようにします。[詳細情報](frequency-rules.md)

   * Adobe Experience Platform で使用可能なメールアドレス／電話番号が複数ある場合、受信者に優先して使用するメールアドレス／電話番号を決定します。[詳細情報](primary-email-addresses.md)

<!--* Understand the push notification flow. [Learn more](../push/push-gs.md)-->

>[!NOTE]
>
>これらの手順は、[Adobe Journey Optimizer システム管理者](../start/path/administrator.md)が実行する必要があります。

## ジャーニーの設定

ジャーニーを作成するには、**[!UICONTROL データソース]**、**[!UICONTROL イベント]**&#x200B;および&#x200B;**[!UICONTROL アクション]**&#x200B;を設定する必要があります。[詳細情報](about-data-sources-events-actions.md)

![](assets/admin-menu.png)

* **データソース**&#x200B;設定では、ジャーニーで使用する追加情報を取得するためにシステムへの接続を定義できます。[詳細情報](../datasource/about-data-sources.md)

* **イベント**&#x200B;を使用すると、ジャーニーをまとめてトリガーし、ジャーニーに流入してくる個人にリアルタイムでメッセージを送信できます。イベントの設定では、ジャーニーで想定されるイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取り込み API から取り込みます。[詳細](../event/about-events.md)

* [!DNL Journey Optimizer] には、コンテンツのデザインと送信を可能にするメッセージ機能が組み込まれています。サードパーティシステムを使用してメッセージを送信する場合は、**カスタムアクション**&#x200B;を作成します。[詳細情報](../action/action.md)
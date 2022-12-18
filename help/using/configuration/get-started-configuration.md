---
solution: Journey Optimizer
product: journey optimizer
title: ' [!DNL Journey Optimizer]  設定の概要'
description: ' [!DNL Journey Optimizer]  設定について説明します。'
role: Admin
level: Intermediate
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
source-git-commit: c6498633fdfdc9442203a3bf980f1b12bd1c6a6b
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 54%

---


# [!DNL Journey Optimizer] 設定の基本を学ぶ {#start-optimizer-configuration}

[!DNL Journey Optimizer]に初めてアクセスする際には、実稼動用サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。

ジャーニーを作成してメッセージを送信するには、次の設定手順に従う必要があります。

## メッセージとチャネルの設定

1. メッセージを作成して送信するには、チャネルに応じて特定の設定をおこなう必要があります。

   * の **電子メール** channel では、サブドメインをAdobeにデリゲートし、IP プールを作成して IP アドレスをグループ化する必要があります。 [詳細情報](../email/get-started-email-config.md)

   * の **プッシュ** チャネル、プッシュ通知設定を [!DNL Adobe Experience Platform] および [!DNL Adobe Experience Platform Launch]. [詳細情報](../push/push-configuration.md)

   * の **SMS** チャネルに接続する場合は、プロバイダーの設定と [!DNL Journey Optimizer]. [詳細情報](../sms/sms-configuration.md)

1. 完了したら、 **チャンネルサーフェス** ：メッセージの配信に必要なすべての技術的パラメーターを設定します。 [詳細情報](channel-surfaces.md)

1. 以下の手順でも可能です。

   * 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。[詳細](manage-suppression-list.md)

   * を有効にします。 **BBC メールオプション** 個人に送信するメッセージのコピーを保持する場合。 [詳細情報](archiving-support.md#enable-bcc)

   * 設定 **頻度ルール** 受信者に過度の勧誘をしないようにする場合。 [詳細情報](frequency-rules.md)

   * Adobe Experience Platformで複数のアドレスや番号が使用可能な場合、受信者に優先して使用する電子メールアドレスや電話番号を決定します。 [詳細情報](primary-email-addresses.md)

<!--* Understand the push notification flow. [Learn more](../push/push-gs.md)-->

>[!NOTE]
>
>これらの手順は、[Adobe Journey Optimizer システム管理者](../start/path/administrator.md)が実行する必要があります。

## ジャーニーの設定

ジャーニーを作成するには、次を設定する必要があります **[!UICONTROL データソース]**, **[!UICONTROL イベント]** および **[!UICONTROL アクション]**. [詳細情報](about-data-sources-events-actions.md)

![](assets/admin-menu.png)

* **データソース**&#x200B;設定では、ジャーニーで使用する追加情報を取得するためにシステムへの接続を定義できます。[詳細情報](../datasource/about-data-sources.md)

* **イベント**&#x200B;を使用すると、ジャーニーをまとめてトリガーし、ジャーニーに流入してくる個人にリアルタイムでメッセージを送信できます。イベントの設定では、ジャーニーで必要なイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取り込み API から取り込みます。[詳細](../event/about-events.md)

* [!DNL Journey Optimizer] には、コンテンツのデザインと送信を可能にするメッセージ機能が組み込まれています。サードパーティシステムを使用してメッセージを送信する場合は、**カスタムアクション**&#x200B;を作成します。[詳細情報](../action/action.md)
---
solution: Journey Optimizer
product: journey optimizer
title: 設定を使用した作業の  [!DNL Journey Optimizer]  開始
description: 設定について  [!DNL Journey Optimizer]  詳しくは、
role: Admin
level: Intermediate
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
source-git-commit: c6498633fdfdc9442203a3bf980f1b12bd1c6a6b
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---


# 設定を使用した作業の [!DNL Journey Optimizer] 開始 {#start-optimizer-configuration}

初めてアクセス [!DNL Journey Optimizer] するときには、実働サンドボックスが提供され、契約によっては一定数の IPs が割り当てられます。

Journeys を作成し、メッセージを送信するには、以下の設定手順を実行する必要があります。

## メッセージとチャネルの設定

1. メッセージを作成して送信できるようにするには、チャネルに応じて特定の設定を行う必要があります。

   * **電子メール** チャンネルについては、Adobe にサブドメインを委任し、ip アドレスをグループ化するための ip プールを作成する必要があります。[詳細情報](../email/get-started-email-config.md)

   * **プッシュ** チャネルについては、と [!DNL Adobe Experience Platform Launch] の両方 [!DNL Adobe Experience Platform] にプッシュ通知設定を定義する必要があります。[詳細情報](../push/push-configuration.md)

   * **Sms** チャネルについては、プロバイダー設定 [!DNL Journey Optimizer] の統合を含む、sms を送信するようにインスタンスを設定する必要があります。[詳細情報](../sms/sms-configuration.md)

1. その後、メッセージを配信するために必要なすべての技術パラメーターを設定するために、チャネルサーフェス **を作成** する必要があります。[詳細情報](channel-surfaces.md)

1. 次のこともできます。

   * 電子メールアドレスを抑制リストに送信する前にリトライが実行される日数を管理します。 [詳細情報](manage-suppression-list.md)

   * 個人に送信されたメッセージのコピーを保存するには、 **「BBC 電子メール」オプション** をオンにします。 [詳細情報](archiving-support.md#enable-bcc)

   * 頻度ルール **を構成** して、受信者の solicitating オーバーを回避します。[詳細情報](frequency-rules.md)

   * Adobe エクスペリエンスプラットフォームでいくつかのアドレスと電話番号が使用可能な場合に、宛先にどの電子メールアドレスと電話番号を使用するかを指定します。 [詳細情報](primary-email-addresses.md)

<!--* Understand the push notification flow. [Learn more](../push/push-gs.md)-->

>[!NOTE]
>
>これらの手順は、 [ Adobe 旅オプティマイザーのシステム管理者 ](../start/path/administrator.md) が実行する必要があります。

## Journeys の構成

Journeys を作成するには、と **[!UICONTROL Actions]** を **[!UICONTROL Events]** 設定 **[!UICONTROL Data Sources]** する必要があります。[詳細情報](about-data-sources-events-actions.md)

![](assets/admin-menu.png)

* **データソース** 設定を使用すると、journeys で使用される追加情報を取得するための、システムへの接続を定義することができます。[詳細情報](../datasource/about-data-sources.md)

* **イベント** を使用すると、journeys unitarily を利用して、その過程に流れている個々のメッセージをリアルタイムに送信することができます。 イベントの設定では、journeys に必要なイベントを設定します。 受信イベントデータは、Adobe エクスペリエンスデータモデル (XDM) の後に標準化されています。 イベントは、認証および認証されていないイベント (Adobe Mobile SDK イベントなど) 用のストリーミング取り込み Api によって発生します。 [詳細情報](../event/about-events.md)

* [!DNL Journey Optimizer] に用意されているメッセージ機能によって、コンテンツをデザインして送信することができます。 サードパーティシステムを使用してメッセージを送信する場合は、カスタムアクション **を** 作成します。[詳細情報](../action/action.md)
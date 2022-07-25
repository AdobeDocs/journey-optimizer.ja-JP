---
title: ' [!DNL Journey Optimizer]  設定の概要'
description: ' [!DNL Journey Optimizer]  設定について説明します。'
role: Admin
level: Intermediate
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 76%

---


# [!DNL Journey Optimizer] 設定の基本を学ぶ {#start-optimizer-configuration}

[!DNL Journey Optimizer]に初めてアクセスする際には、実稼動用サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。

ジャーニーを作成してメッセージを送信するには、次の設定手順に従う必要があります。

1. **メッセージとチャネルの設定**:チャネルサーフェスを定義し、メッセージを調整してカスタマイズします。

   * チャネルサーフェスを作成して、メッセージの配信に必要なすべての技術的パラメータを設定します。 [詳細](message-presets.md)

   * Adobe Experience Platform で使用可能なアドレスが複数ある場合、受信者に優先して使用するメールアドレスを決定します。[詳細](primary-email-addresses.md)

   * 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。[詳細](manage-suppression-list.md)

   * [!DNL Adobe Experience Platform]と[!DNL Adobe Experience Platform Launch]の両方でプッシュ通知の設定を定義します。[詳細](../configuration/push-gs.md)

   <!--* Understand the push notification flow. [Learn more](../configuration/push-gs.md)-->

   * SMS を送信するようにインスタンスを設定します（現在は一連の組織でのみ使用可能 — 限定提供）。 [詳細](sms-configuration.md)


1. **サブドメインをデリゲート**：Journey Optimizer で新規サブドメインを使用する場合、最初の手順としてそのサブドメインをデリゲートします。[詳細](about-subdomain-delegation.md)

   ![](assets/subdomain.png)

1. **IP プールの作成**：インスタンスでプロビジョニングされた IP アドレスをグループ化することで、E メールの配信品質と評判を向上させます。[詳細](ip-pools.md)

   ![](assets/ip-pool.png)

1. **ジャーニーの設定**：ジャーニーを作成するには、**[!UICONTROL データソース]**、**[!UICONTROL イベント]** と **[!UICONTROL アクション]**&#x200B;を設定する必要があります。[詳細](about-data-sources-events-actions.md)

   ![](assets/admin-menu.png)

   * この **データソース** 設定を使用すると、システムへの接続を定義して、ジャーニーで使用される追加情報を取得できます。 [詳細情報](../datasource/about-data-sources.md)

   * **イベント**&#x200B;を使用すると、ジャーニーをまとめてトリガーし、ジャーニーに流入してくる個人にリアルタイムでメッセージを送信できます。イベントの設定では、ジャーニーで必要なイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取り込み API から取り込みます。[詳細](../event/about-events.md)

   * [!DNL Journey Optimizer] には、コンテンツのデザインと送信を可能にする組み込みのメッセージ機能が付属しています。 サードパーティシステムを使用してメッセージを送信する場合は、**カスタムアクション**&#x200B;を作成します。[詳細情報](../action/action.md)
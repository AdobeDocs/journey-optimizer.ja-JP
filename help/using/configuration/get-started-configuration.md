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
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 70%

---


# [!DNL Journey Optimizer] 設定の基本を学ぶ {#start-optimizer-configuration}

[!DNL Journey Optimizer]に初めてアクセスする際には、実稼動用サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。

ジャーニーを作成してメッセージを送信するには、次の設定手順に従う必要があります。

## メッセージとチャネルの設定

チャネルサーフェスを定義し、メッセージを調整してカスタマイズします。

* [サブドメインをAdobeにデリゲート](about-subdomain-delegation.md) を使用してメールを送信し、 [IP プールの作成](ip-pools.md) ：インスタンスでプロビジョニングされた IP アドレスをグループ化します。

* 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。[詳細](manage-suppression-list.md)

* [!DNL Adobe Experience Platform]と[!DNL Adobe Experience Platform Launch]の両方でプッシュ通知の設定を定義します。[詳細](../push/push-gs.md)

   <!--* Understand the push notification flow. [Learn more](../push/push-gs.md)-->

* SMS を送信するようにインスタンスを設定します（現在は一連の組織でのみ使用できます - 使用制限あり）。 [詳細情報](../sms/sms-configuration.md)

* チャネルサーフェスを作成して、メッセージの配信に必要なすべての技術パラメーターを設定します。 [詳細情報](channel-surfaces.md)

* Adobe Experience Platformで複数のアドレスや番号が使用可能な場合、受信者に優先して使用する電子メールアドレスや電話番号を決定します。 [詳細情報](primary-email-addresses.md)

## ジャーニーの設定

ジャーニーを作成するには、次を設定する必要があります **[!UICONTROL データソース]**, **[!UICONTROL イベント]** および **[!UICONTROL アクション]**. [詳細情報](about-data-sources-events-actions.md)

![](assets/admin-menu.png)

* **データソース**&#x200B;設定では、ジャーニーで使用する追加情報を取得するためにシステムへの接続を定義できます。[詳細情報](../datasource/about-data-sources.md)

* **イベント**&#x200B;を使用すると、ジャーニーをまとめてトリガーし、ジャーニーに流入してくる個人にリアルタイムでメッセージを送信できます。イベントの設定では、ジャーニーで必要なイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取り込み API から取り込みます。[詳細](../event/about-events.md)

* [!DNL Journey Optimizer] には、コンテンツのデザインと送信を可能にするメッセージ機能が組み込まれています。サードパーティシステムを使用してメッセージを送信する場合は、**カスタムアクション**&#x200B;を作成します。[詳細情報](../action/action.md)
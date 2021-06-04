---
title: Journey Optimizer設定と設定のガイドライン
description: メッセージとジャーニー設定のガイドラインを説明します
audience: administrators
content-type: reference
role: Administrator
level: Intermediate
product: Adobe Journey Optimizer
solution: Journey Optimizer
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
source-git-commit: 03d003682d796906fcf89af02aa98d549b5214a3
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 29%

---


# [!DNL Journey Optimizer]設定の基本を学ぶ

[!DNL Journey Optimizer]に初めてアクセスする場合は、実稼動用サンドボックスがプロビジョニングされ、契約に応じて一定数のIPが割り当てられます。

ジャーニーを作成してメッセージを送信するには、次の設定手順に従う必要があります。

1. **メッセージとチャネルの設定**:プリセットの定義、Eメールおよびプッシュメッセージの適応とカスタマイズ

   * [!DNL Adobe Experience Platform]と[!DNL Adobe Experience Platform Launch]の両方でプッシュ通知の設定を定義します。 [詳細情報](../push-gs.md)

   * メッセージプリセットを作成して、電子メールおよびプッシュ通知メッセージに必要なすべての技術的パラメーターを設定します。 [詳細情報](message-presets.md)

   * Adobe Experience Platformで複数のアドレスが使用可能な場合、受信者に優先して使用する電子メールアドレスを決定します。 [詳細情報](primary-email-addresses.md)

   * 抑制リストに電子メールアドレスを送信する前に再試行が実行される日数を管理します。 [詳細情報](manage-suppression-list.md)

   <!--
    * Understand push notification flow. [Learn more](../push-gs.md)
    -->

1. **サブドメインをデリゲート**:Journey Optimizerで使用される新しいサブドメインの場合、最初の手順はそれをデリゲートすることです。[詳細情報](about-subdomain-delegation.md)

   ![](../assets/subdomain.png)

1. **IPプールの作成**:インスタンスでプロビジョニングされたIPアドレスをグループ化することで、Eメールの配信品質とレピュテーションを向上させます。[詳細情報](ip-pools.md)

   ![](../assets/ip-pool.png)

1. **ジャーニーの設定**:ジャーニーを作成するには、データソース **[!UICONTROL 、イベン]**&#x200B;ト、アクション **** を設定する **[!UICONTROL 必要]**&#x200B;があります。[詳細情報](about-data-sources-events-actions.md)

   ![](../assets/admin-menu.png)

   * **データソース**&#x200B;設定を使用すると、システムへの接続を定義して、ジャーニーで使用される追加情報を取得できます。 データソースについて詳しくは、この[セクション](../datasource/about-data-sources.md)を参照してください

   * **イベントを使用すると、ジャーニーを一元的にトリガーし、ジャーニーに流れ込む個人にリアルタイムでメッセージを送信できます。**&#x200B;イベントの設定では、ジャーニーで必要なイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取得 API から提供されます。イベントについて詳しくは、この[セクション](../event/about-events.md)を参照してください

   * [!DNL Journey Optimizer] には、次の組み込みのメッセージ機能が備わっています。コンテンツをデザインし、メッセージを公開できます。サードパーティシステムを使用してメッセージを送信する場合は、**カスタムアクション**&#x200B;を作成します。 アクションについて詳しくは、この[セクション](../action/action.md)を参照してください
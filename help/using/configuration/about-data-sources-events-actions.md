---
title: 管理と設定
description: 管理と設定のガイドラインを学ぶ
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
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
source-git-commit: a65cefd0bbd15ffa389bac910eaceb40181cb38d
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 75%

---

# ジャーニーの設定

ジャーニーを含むメッセージを送信するには、**[!UICONTROL データソース]**、**[!UICONTROL イベント]**、**[!UICONTROL アクション]**&#x200B;を設定する必要があります。

![](../assets/admin-menu.png)

## データソース

データソースを設定すると、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義できます。[詳細情報](../../using/datasource/about-data-sources.md)

## イベント

イベントを使用すると、ジャーニーを一元的にトリガーし、ジャーニーに流れ込む個人にリアルタイムでメッセージを送信できます。

イベントの設定では、ジャーニーで必要なイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取得 API から提供されます。[詳細情報](../../using/event/about-events.md)

## アクション

Journey Optimizerメッセージ機能は次の組み込み機能です。必要なのは、コンテンツのデザインとメッセージのパブリッシュだけです。 サードパーティシステムを使用してメッセージを送信する場合は、カスタムアクションを作成できます。[詳細情報](../../using/action/action.md)

---
title: 意思決定管理イベント入門
description: Adobe エクスペリエンスプラットフォームで意思決定管理レポートを作成する方法について説明します。
feature: Offers
topic: Integrations
role: User
level: Beginner
exl-id: 51830c63-fa88-47e7-8605-192297fcf6b8
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 0%

---

# 意思決定管理イベント入門 {#monitor-offer-events}

特定のプロファイルについて意思決定を行うたびに、それらのイベントに関する情報が Adobe エクスペリエンスプラットフォームに自動的に送信されます。

これにより、これらのデータを書き出して、独自のレポートシステムに解析することができます。 また、Adobe エクスペリエンス Platform [ クエリーサービス ](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) と他のツールを組み合わせて使用して、解析とレポート作成のための機能が強化されています。

意思決定管理イベントを含むデータセットには、Adobe エクスペリエンス Platform **[!UICONTROL Datasets]** メニューからアクセスできます。 各インスタンスに対して、1つのデータセットが自動的に作成されます。

![](../assets/events-datasets-list.png)

これらのデータセットは、スキーマに **[!UICONTROL ODE DecisionEvents]** 基づいています。これらのフィールドには、意志決定管理から Adobe エクスペリエンスプラットフォームに情報を送信するために必要なすべての XDM フィールドが含まれています。

>[!NOTE]
>
>DecisionEvents はプロファイルデータセット **では** ないので、リアルタイムのユーザープロファイルで使用できるように、経験のあるプラットフォームに ingested ことはできません。

**関連トピック:**

* [意思決定管理イベントキー情報](../reports/key-information.md)
* [Access イベント &quot;XDM&quot; フィールド](../reports/xdm-fields.md)

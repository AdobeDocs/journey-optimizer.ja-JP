---
title: 意思決定管理イベントキー情報
description: 各意思決定管理イベントによって送信される主な情報について詳しく説明しています。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 07be59e8-e994-4854-8089-25614d005dbe
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# 意思決定管理イベントキー情報 {#events-key-information}

決定が実行されたときに送られる各イベントには、解析およびレポート用に活用できる4つの主要なデータポイントが含まれています。

![](../assets/events-dataset-preview.png)

* **[!UICONTROL Fallback]**: 「代替オファーが選択されていない場合は、フォールバックオファーの名前と ID」を指定します。
* **[!UICONTROL Placement]**: オファーを配信するために使用される配置の名前、ID、およびチャンネル
* **[!UICONTROL Selections]**: プロファイルに選択された offer の名前と ID。
* **[!UICONTROL Activity]**: 意思決定を実行するための「名前」と「ID」を指定します。

さらに、および **[!UICONTROL Timestamp]** の **[!UICONTROL identityMap]** フィールドを使用して、プロファイルに関する情報や申し出が配信された時刻を取得することもできます。

各決定によって送信される XDM のすべてのフィールドについて詳しくは、ここ ](xdm-fields.md) を [ 参照してください。

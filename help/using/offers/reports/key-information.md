---
title: 意思決定管理イベントの主な情報
description: '各意思決定管理イベントで送信される主な情報について詳しく説明します。 '
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 07be59e8-e994-4854-8089-25614d005dbe
source-git-commit: 51254efaab08a572def118d475dc18f74c9d29b7
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 100%

---

# 意思決定管理イベントの主な情報 {#events-key-information}

決定時に送信される各イベントには、分析とレポートに利用できる 4 つの主要なデータポイントが含まれています。

![](../../assets/events-dataset-preview.png)

* **[!UICONTROL フォールバック]**：フォールバックオファーの名前と ID（パーソナライズされたオファーが選択されていない場合）
* **[!UICONTROL プレースメント]**：オファーの配信に使用するプレースメントの名前、ID、チャネル
* **[!UICONTROL 選択]**：プロファイルに対して選択したオファーの名前と ID
* **[!UICONTROL アクティビティ]**：決定の名前と ID

さらに、**[!UICONTROL identityMap]** と **[!UICONTROL Timestamp]** の各フィールドを利用して、オファー配信時のプロファイルと時刻に関する情報を取得することもできます。

決定のたびに送信されるすべての XDM フィールドについて詳しくは、[この節](xdm-fields.md)を参照してください。

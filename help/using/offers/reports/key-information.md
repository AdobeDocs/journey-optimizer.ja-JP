---
title: Decision Managementイベントの主な情報
description: 各Decision Managementイベントと共に送信される主要な情報について詳しく説明します。
translation-type: tm+mt
source-git-commit: db7fd318b14d01a0369c934a3e01c6e368d7658d
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 75%

---

# Decision Managementイベントの主な情報{#events-key-information}

決定時に送信される各イベントには、分析とレポートに利用できる 4 つの主要なデータポイントが含まれています。

![](../../assets/events-dataset-preview.png)

* **[!UICONTROL Fallback]**：フォールバックオファーの名前と ID（パーソナライズされたオファーが選択されていない場合）
* **[!UICONTROL Placement]**：オファーの配信に使用するプレースメントの名前、ID、チャネル
* **[!UICONTROL Selections]**：プロファイルに対して選択したオファーの名前と ID
* **[!UICONTROL アクティビティ]**:決定の名前とID(旧称オファーアクティビティ)。

さらに、**[!UICONTROL identityMap]** と **[!UICONTROL Timestamp]** の各フィールドを利用して、オファー配信時のプロファイルと時刻に関する情報を取得することもできます。

決定のたびに送信されるすべての XDM フィールドについて詳しくは、[この節](xdm-fields.md)を参照してください。

---
title: キャンペーンの変更または停止
description: でライブキャンペーンを変更、停止、複製する方法を説明します。 [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 1b88c84e-9d92-4cc1-b9bf-27a2f1d29569
source-git-commit: 711fdf1dce0688d2e21d405a4e3e8777612b2f3b
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 40%

---

# ライブキャンペーンの管理 {#modify-stop-campaign}

キャンペーンがアクティブ化されると、いつでも変更または停止できます。 これらの操作は、繰り返し実行されるキャンペーンでのみ使用できます。

さらに、ライブキャンペーン（1 回実行するか、繰り返し実行する）を複製して、新しいキャンペーンを作成できます。

## 繰り返しキャンペーンの変更 {#modify}

繰り返しキャンペーンの新しいバージョンを変更および作成するには、次の手順に従います。

1. キャンペーンを開き、「**[!UICONTROL キャンペーンを変更]**」ボタンをクリックします。

1. キャンペーンの新しいバージョンが作成されます。ライブバージョンを確認するには、「**[!UICONTROL ライブバージョンを開く]**」をクリックします。

   ![](assets/create-campaign-draft.png)

   キャンペーンリストで、ドラフトバージョンが進行中のアクティブ化されたキャンペーンは、**[!UICONTROL ステータス]**&#x200B;列に特定のアイコンで表示されます。このアイコンをクリックして、キャンペーンのドラフトバージョンを開きます。

   ![](assets/create-campaign-edit-list.png)

1. 変更の準備が整ったら、新しいバージョンのキャンペーンをアクティブ化できます（[キャンペーンのレビューとアクティブ化](create-campaign.md#review-activate)を参照）。

   >[!IMPORTANT]
   >
   >ドラフトをアクティブ化すると、キャンペーンのライブバージョンが置き換えられます。

## 繰り返しキャンペーンを停止 {#stop}

繰り返しキャンペーンを停止するには、キャンペーンを開き、 **[!UICONTROL キャンペーンを停止]** 」ボタンをクリックします。

![](assets/create-campaign-stop.png)

>[!IMPORTANT]
>
>キャンペーンを停止しても、継続的な送信は停止されませんが、スケジュールされた送信は停止されます。送信が既に進行中の場合は、次の送信が停止されます。

<!-- inbound campaign (inapp): can stop and resume -->

## キャンペーンの複製 {#duplicate}

ライブキャンペーンを複製して、新しいキャンペーンを作成できます。 これをおこなうには、キャンペーンを開き、 **[!UICONTROL 複製]**.

![](assets/create-campaign-duplicate.png)

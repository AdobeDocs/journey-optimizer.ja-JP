---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの変更または停止
description: ' [!DNL Journey Optimizer] でライブキャンペーンを変更、停止、複製する方法を説明します。'
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 1b88c84e-9d92-4cc1-b9bf-27a2f1d29569
source-git-commit: 0433e312db84ee16a076c183a82345de372c6ae7
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---

# キャンペーンの管理 {#modify-stop-campaign}

キャンペーンがアクティブ化されると、いつでも変更または停止できます。これらの操作は、繰り返し実行されるキャンペーンでのみ使用できます。

さらに、ライブキャンペーン（1 回実行または繰り返し実行）を複製して新しいキャンペーンを作成し、完了または停止したキャンペーンをアーカイブできます。

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

## 繰り返しキャンペーンの停止 {#stop}

繰り返しキャンペーンを停止するには、キャンペーンを開いてから「**[!UICONTROL キャンペーンを停止]**」ボタンをクリックします。

![](assets/create-campaign-stop.png)

>[!IMPORTANT]
>
>キャンペーンを停止しても、その時点で送信中のキャンペーンは停止されませんが、スケジュール済みの送信や、送信中のキャンペーンの次回の送信が停止されます。

<!-- inbound campaign (inapp): can stop and resume -->

## キャンペーンの複製 {#duplicate}

ライブキャンペーンを複製して、新しいキャンペーンを作成できます。これを行うには、キャンペーンを開き、「**[!UICONTROL 複製]**」をクリックします。

![](assets/create-campaign-duplicate.png)

## キャンペーンのアーカイブ {#archive}

時間が経過すると、キャンペーンのリストは増え続け、最終的には完了済みのキャンペーンと停止済みのキャンペーンを参照するのが難しくなります。

これを防ぐには、不要になった完了済みのキャンペーンと停止済みのキャンペーンをアーカイブします。これを行うには、「...」ボタンをクリックし、**[!UICONTROL アーカイブ]**&#x200B;を選択します。

![](assets/create-campaign-archive.png)

アーカイブされたキャンペーンは、リスト内の専用フィルターを使用して取得できます。[キャンペーンへのアクセス方法を学ぶ](get-started-with-campaigns.md#access)

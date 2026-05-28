---
solution: Journey Optimizer
product: journey optimizer
title: アクションキャンペーンオーディエンスの定義
description: アクションキャンペーンオーディエンスの定義方法について説明します。
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: 作成, Optimizer, キャンペーン, サーフェス, メッセージ
exl-id: 5635ef04-c69d-4397-9762-7a6f1265d453
TQID: https://experienceleague.adobe.com/3lWwW0Lru2D5D83QqHl48Gsxv7JVKjX8ZBmZAiMFiB0
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a653cc2e-bc85-4353-a306-399e5b247978
subfeature_v2:
  - id: f7479fa1-474b-479d-8c98-f6cee5865a38
  - id: ee67bd4a-25ee-4cdd-9eab-0d7549fde0c6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 210
ht-degree: 100%

---

# アクションキャンペーンオーディエンスの定義 {#action-campaign-audience}

「**[!UICONTROL オーディエンス]**」タブを使用して、キャンペーンオーディエンスを定義します。

![](assets/campaign-audience.png)

1. **オーディエンスを選択**

   マーケティングキャンペーンの場合は、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用できる Adobe Experience Platform オーディエンスのリストを表示します。 [詳しくは、オーディエンスを参照してください](../audience/about-audiences.md)。

   >[!IMPORTANT]
   >
   >[オーディエンス構成](../audience/get-started-audience-orchestration.md)からのオーディエンスおよび属性は現在、Healthcare Shield または Privacy and Security Shield では使用できません。

1. **ID タイプを選択**

   「**[!UICONTROL ID タイプ]**」フィールドで、選択したオーディエンスから個人を識別するために使用するキーのタイプを選択します。 既存の ID タイプを使用することも、Adobe Experience Platform ID サービスを使用して新しい ID タイプを作成することもできます。 標準 ID 名前空間について詳しくは、[このページ](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces#standard){target="_blank"}を参照してください。

   1 つのキャンペーンで使用できる ID タイプは 1 つだけです。 様々な ID の中から選択した ID タイプを持たないセグメントに属する個人は、キャンペーンのターゲットにすることができません。 ID タイプと名前空間について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja){target="_blank"}を参照してください。

## 次の手順 {#next}

アクションキャンペーンのオーディエンスの準備が整ったら、キャンペーンをスケジュールできます。 [詳細情報](campaign-schedule.md)

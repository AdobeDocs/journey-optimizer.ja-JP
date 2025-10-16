---
solution: Journey Optimizer
product: journey optimizer
title: API トリガーキャンペーンのプロパティの定義
description: API トリガーキャンペーンのプロパティの定義方法について説明します。
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: キャンペーン, API トリガー, REST, Optimizer, メッセージ
exl-id: bda7e337-a246-4f01-b935-4a234d4c4baa
source-git-commit: 93698c93f3750b4d7feff18509f8144a7c79f156
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 86%

---

# API トリガーキャンペーンのプロパティの定義 {#api-properties}

新しい API トリガーキャンペーンを作成するには、次の手順に従います。

1. **[!UICONTROL キャンペーン]**&#x200B;メニューに移動し、「**[!UICONTROL API トリガー]**」タブを選択します。

1. 「**[!UICONTROL キャンペーンを作成]**」ボタンをクリックし、キャンペーンのタイプを選択します。

   * **[!UICONTROL API トリガー - マーケティング]** - ターゲットオーディエンスにパーソナライズされたマーケティングコミュニケーションを送信するには、この API トリガーキャンペーンのタイプを選択します。

   * **[!UICONTROL API トリガー – トランザクション]** - トランザクションキャンペーンは、トランザクションメッセージ、つまり、個人が実行したアクション（パスワードのリセットリクエスト、買い物かごの購入など）に続いて送信されるメッセージを送信することを目的としています。

   ![](assets/api-triggered-modal.png)

1. 「**[!UICONTROL プロパティ]**」タブで、キャンペーンの名前と説明を入力します。

   ![](assets/create-campaign-properties.png)

1. 「**タグ**」フィールドを使用して、Adobe Experience Platform 統合タグをキャンペーンに割り当てます。これにより、キャンペーンを簡単に分類し、キャンペーンリストからの検索を改善できます。[詳しくは、タグの操作方法を参照してください](../start/search-filter-categorize.md#tags)。

1. アクセスラベルに基づいて、このキャンペーンへのアクセスを制限できます。アクセス制限を追加するには、このページの上部にある「**[!UICONTROL アクセスを管理]**」ボタンを参照します。権限のあるラベルのみを選択します。[詳しくは、オブジェクトレベルのアクセス制御を参照してください](../administration/object-based-access.md)。

## 次の手順 {#next}

キャンペーンの設定とコンテンツの準備が整ったら、このアクションを設定できます。[詳細情報](api-triggered-campaign-action.md)

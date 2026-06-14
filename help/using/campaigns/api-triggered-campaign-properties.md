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
TQID: https://experienceleague.adobe.com/qUWCJifjUbLmapOtZlk9elkRZLcr-XGXNzuy0rayx-8
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: a653cc2e-bc85-4353-a306-399e5b247978
subfeature_v2:
  - id: f7479fa1-474b-479d-8c98-f6cee5865a38
  - id: ee67bd4a-25ee-4cdd-9eab-0d7549fde0c6
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: a5c0537a45acbc708ce62bd05a569630230201ac
workflow-type: tm+mt
source-wordcount: 330
ht-degree: 91%

---

# API トリガーキャンペーンのプロパティの定義 {#api-properties}

>[!BEGINSHADEBOX]

**このページ：** API トリガーのキャンペーンを作成し、そのタイプ、名前、タグ、およびアクセスラベルを設定して、最初から正しい範囲で簡単に見つけられるようにします。

>[!ENDSHADEBOX]

新しい API トリガーキャンペーンを作成するには、次の手順に従います。

1. **[!UICONTROL キャンペーン]**&#x200B;メニューに移動し、「**[!UICONTROL API トリガー]**」タブを選択します。

1. 「**[!UICONTROL キャンペーンを作成]**」ボタンをクリックし、キャンペーンのタイプを選択します。

   * **[!UICONTROL API トリガー - マーケティング]** - ターゲットオーディエンスにパーソナライズされたマーケティングコミュニケーションを送信するには、この API トリガーキャンペーンのタイプを選択します。

   * **[!UICONTROL API トリガー - トランザクション]** - トランザクションキャンペーンは、トランザクションメッセージ、つまり、個人が実行したアクション（パスワードのリセットリクエスト、買い物かごでの購入など）に続いて送信されるメッセージの送信を目的としています。

     +++高スループットモード

     トランザクション API トリガーキャンペーンの場合は、**[!UICONTROL 高スループット]**&#x200B;モードを有効にすることができます。 このモードは、大規模なリアルタイムメッセージ（1 秒あたり最大 5000 トランザクション）向けに設計され、少ない待ち時間でより高い可用性を実現します。 [高スループットモードの操作方法の詳細情報](../campaigns/api-triggered-high-throughput.md)

     >[!AVAILABILITY]
     >
     >現在、高スループットモードは、メールチャネルと米国地域でのみ使用できます。
     >
     >この機能は、アドビの&#x200B;**高スループットトランザクションメッセージ**&#x200B;のアドオン機能を購入した組織でのみ使用できます。 詳しくは、アドビ担当者にお問い合わせください。

     +++

   ![](assets/api-triggered-modal.png)

1. 「**[!UICONTROL プロパティ]**」タブで、キャンペーンの名前と説明を入力します。

   ![](assets/create-campaign-properties.png)

1. 「**タグ**」フィールドを使用して、Adobe Experience Platform 統合タグをキャンペーンに割り当てます。 これにより、キャンペーンを簡単に分類し、キャンペーンリストからの検索を改善できます。 [詳しくは、タグの操作方法を参照してください](../start/search-filter-categorize.md#tags)。

1. アクセスラベルに基づいて、このキャンペーンへのアクセスを制限できます。 アクセス制限を追加するには、このページの上部にある「**[!UICONTROL アクセスを管理]**」ボタンを参照します。 権限のあるラベルのみを選択します。 [詳しくは、オブジェクトレベルのアクセス制御を参照してください](../administration/object-based-access.md)。

## 次の手順 {#next}

キャンペーンの設定とコンテンツの準備が整ったら、このアクションを設定できます。 [詳細情報](api-triggered-campaign-action.md)

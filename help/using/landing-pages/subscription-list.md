---
title: Create a subscription list
description: Journey Optimizerで購読リストを設定する方法を説明します
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
source-git-commit: 4d564ff89a8cb6c6d76161f2e6cedf39d33e70a0
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---

# 購読リストの作成 {#create-subscription-list}

## 購読リストとは

サブスクリプションサービスとは、特定の対象、イベント、興味などに関するコミュニケーションの受信を選択した顧客に提供されるマーケティング商品やサービスを指します。 on an ongoing basis. In [!DNL Journey Optimizer]の場合、これらのオプトイン済みの顧客は、購読リストに収集されます。

購読サービスには、次のようなものがあります。

* a newsletter, for example “Running series”
* an event, for example “Summit 2021”
* a webinar, for example &quot;Learn more about crypto&quot;
* 特定の製品/スポーツ/サービス等に対する関心（例えば、「次の 12 ヶ月間に家を買うことに関心がある」）
* 通知方法の優先度（例：「E メールで新しい曲の通知を受信する」）

The profiles can be added to a subscription list through a [landing page](create-lp.md). 例については、 [この節](get-started-lp.md#subscription-to-a-service).

## 購読リストを定義 {#define-subscription-list}

購読リストを作成するには、次の手順に従います。

1. 購読リストにアクセスするには、 **[!UICONTROL 顧客]** > **[!UICONTROL 購読リスト]**.

   ![](../assets/lp_subscription-lists.png)

1. 購読リストで、 **[!UICONTROL 購読を作成]** リスト。

   ![](../assets/lp_create-subscription-list.png)

1. Add a name and a description. These fields are mandatory.

1. You can define a start date and end date.

   ![](../assets/lp_subscription-list-dates.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

リストには、作成されたすべての購読リストが表示されます。 作成日または変更日に基づいてフィルタリングできます。

![](../assets/lp_subscription-filters.png)

The possible statuses are as follows:

* **[!UICONTROL 未開始]**:開始日を現在の日付より後に定義しました。 The profiles subscribed to this list will not receive yet communications relating to this subscription list.
* **[!UICONTROL ライブ]**:現在の日付は、購読リストの開始日と終了日の間に含まれます。または、終了日/開始日を定義していない場合は、購読リストが常にライブになっています。
* **[!UICONTROL Expired]**: The end date is passed, the subscription list is not valid anymore. Any profile subscribed to this list will not receive any more communications relating to this subscription list.

購読リストを作成したら、ランディングページで使用して、プロファイルがフォームをオプトインし、リストに追加できるようにします。 [詳細情報](design-lp.md)

You can also use subscription lists as segments when building journeys and personalization.

<!--

**Questions**

* Can't see the newly created subscription list in UI because their name included spacing > bug - to follow up (should be fixed for Dec. release)

* How do you handle the different statuses? Live, Not started, Expired? Is it only through start/end dates?

* What does it mean when a subscription list is expired or not started? You can't use it in a LP? And if a user is subscribed to this service, then he won't receive communications any more?

* What else can you currently do with subscription lists apart from attach them to a landing page?

* Can you update the subscription list in a way other than through a LP? Not in UI but with APIs > to follow up with Fred

-->
---
title: 購読リストの作成
description: Journey Optimizerで購読リストを設定する方法を説明します
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
exl-id: 5e5419a0-5121-4aa7-a975-b1f08e2918c9
source-git-commit: 88b037e079a46e10f7ee4715e78e5edc5a34a6ce
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# 購読リスト {#create-subscription-list}

## 購読リストとは

サブスクリプションサービスとは、特定の対象、イベント、興味などに関するコミュニケーションの受信を選択した顧客に提供されるマーケティング商品やサービスを指します。 継続的に In [!DNL Journey Optimizer]の場合、これらのオプトイン済みの顧客は、購読リストに収集されます。

購読サービスには、次のようなものがあります。

* ニュースレターの例：&quot;シリーズを実行中&quot;
* イベントの例：&quot;Summit 2021&quot;
* ウェビナーの例：暗号の詳細
* 特定の製品、スポーツ、サービスなどに対する関心：「今後 12 ヶ月で家を買いたい」
* 通知方法に関する環境設定。次に例を示します。&quot;メールで新しい曲の通知を受信&quot;

プロファイルは、 [ランディングページ](create-lp.md). 例については、 [この節](lp-use-cases.md#subscription-to-a-service).

## 購読リストを定義 {#define-subscription-list}

購読リストを作成するには、次の手順に従います。

1. 購読リストにアクセスするには、 **[!UICONTROL 顧客]** > **[!UICONTROL 購読リスト]**.

   ![](../assets/lp_subscription-lists.png)

1. を選択します。 **[!UICONTROL 購読リストを作成]** 」ボタンをクリックします。

   ![](../assets/lp_create-subscription-list.png)

1. 名前と説明を追加します。 これらのフィールドは必須です。

1. 開始日と終了日を定義できます。

   ![](../assets/lp_subscription-list-dates.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

リストには、作成されたすべての購読リストが表示されます。 作成日や変更日、およびステータスに基づいてフィルタリングできます。

![](../assets/lp_subscription-filters.png)

ステータスには次のものが考えられます。

* **[!UICONTROL 未開始]**:開始日を現在の日付より後に定義しました。 購読されたプロファイルは、この購読リストに関する通信をまだ受け取っていません。
* **[!UICONTROL ライブ]**:現在の日付は、購読リストの開始日と終了日の間に含まれます。または、終了日/開始日を定義していない場合は、購読リストが常にライブになっています。
* **[!UICONTROL 期限切れ]**:終了日が過ぎたので、購読リストは無効になりました。 この配信登録リストに関連する通信は、配信登録されたプロファイルには送信されません。

購読リストを作成したら、ランディングページで使用できます。 ランディングページフォームをオプトインしたプロファイルがリストに追加されます。 [詳細情報](design-lp.md)

購読リストは、 [ジャーニーの構築](../building-journeys/journey-gs.md#jo-build) パーソナライゼーションの追加。

>[!NOTE]
>
>特定のレポートを使用して、購読リストの影響を監視できます。 [詳細情報](subscription-report.md)

<!--

**Questions**

* Can't see the newly created subscription list in UI because their name included spacing > bug - to follow up (should be fixed for Dec. release)

* Can you update the subscription list in a way other than through a LP? Not in UI but with APIs > to follow up with Fred

-->

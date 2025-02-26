---
solution: Journey Optimizer
product: journey optimizer
title: サブスクリプションリストの作成
description: Journey Optimizer で購読リストを設定する方法を学ぶ
feature: Subscriptions
topic: Content Management
role: User
level: Beginner
keywords: ランディング, ランディングページ, リスト, 購読, サービス
exl-id: 5e5419a0-5121-4aa7-a975-b1f08e2918c9
source-git-commit: c66fe22f0cf81cf8e14592df1433739735afbe43
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 61%

---

# サブスクリプションリスト {#create-subscription-list}

>[!CONTEXTUALHELP]
>id="ajo_subscription_list"
>title="サブスクリプションリストの設定"
>abstract="サブスクリプションリストを作成して、特定の件名またはイベントに関するお知らせの受信をオプトインしたプロファイルを収集します。 "
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/subscription-list.html?lang=ja#define-subscription-list" text="サブスクリプションリストの作成"

購読サービスとは、特定の対象、イベント、興味などに関するコミュニケーションの受信を選択した顧客に対して継続的に提供される、マーケティング商品やサービスを指します。[!DNL Journey Optimizer] では、これらのオプトイン済みの顧客は、購読リストに収集されます。

購読サービスは、次の目的で使用できます。

* ニュースレター（例：「連載中のシリーズ」）
* イベント（例：「Summit 2021」）
* ウェビナー（例：「暗号の詳細を学ぼう」）
* 特定の製品、スポーツ、サービスなどに対する興味（例：「今後 12 か月で家を購入することに関心がある」）
* 通知方法に関する環境設定（例：「新曲のお知らせをメールで受信する」）

プロファイルは、[ランディングページ](create-lp.md)から購読リストに追加できます。例については、[この節](lp-use-cases.md#subscription-to-a-service)で示します。

## サブスクリプションリストの作成 {#define-subscription-list}

購読リストを作成するには、次の手順に従います。

1. 購読リストにアクセスするには、 **[!UICONTROL 顧客]**／**[!UICONTROL 購読リスト]**&#x200B;を選択します。

   ![](assets/lp_subscription-lists.png)

1. 「**[!UICONTROL 購読リストを作成]**」ボタンを選択します。

   ![](assets/lp_create-subscription-list.png)

1. 名前と説明を追加します。これらのフィールドは必須です。

   ![](assets/lp_subscription-list-name.png)

   >[!CAUTION]
   >
   >現在、「**[!UICONTROL タイトル]**」フィールドには、別の購読リストに既に存在する名前やスペースを入力することはできません。

1. 開始日と終了日を定義できます。

   ![](assets/lp_subscription-list-dates.png)

1. 「**[!UICONTROL タグ]**」フィールドから Adobe Experience Platform タグを選択または作成してランディングページを分類し、検索の向上を図ります。[詳細情報](../start/search-filter-categorize.md#tags)

1. 「**[!UICONTROL 保存]**」をクリックします。

## 購読リストを使用 {#use-subscription-lists}

購読リストを作成すると、次の操作を実行できます。

* 購読リストへのプロファイルの追加

  ニュースレターを購読したり、イベントに登録したりして、ユーザーを **リストに参加** するように招待できます。 また、購読者に **パーソナライズされたメッセージの送信** を行うこともできます。

  例えば、オーディエンスをイベントへの登録やニュースレターの購読に招待するには、ランディングページへのリンクを含んだメッセージを送信して、オーディエンスがイベントに参加したり購読したりできるようにします。 ランディングページフォームからオプトインしたプロファイルは、この目的で作成した購読リストに追加されます。

* 購読者へのメッセージの送信

  ジャーニーを作成し、パーソナライゼーションを追加する際に、購読リストをオーディエンスとして使用することもできます。

  例えば、お客様がストリーミングサービスを購読する際に、「ようこそ」メールシリーズの即時ディスパッチをトリガーし、アプリに初めてログインして閲覧環境設定を設定するように促すことができます。

購読リストの使用方法については、[ このユースケース ](lp-use-cases.md#subscription-to-a-service) を参照してください。


## 購読リストの参照 {#browse-subscription-lists}

リストには、作成したすべての購読リストが表示されます。リストは、作成日や変更日、およびステータスに基づいてフィルター処理できます。

![](assets/lp_subscription-filters.png)

ステータスは次のいずれかになります。

* **[!UICONTROL 未開始]**：定義された開始日は本日より後の日付です。購読されたプロファイルは、この購読リストに関するお知らせをまだ受け取っていません。
* **[!UICONTROL ライブ]**：現在の日付が、購読リストの開始日と終了日の間にある、または終了日／開始日を定義していませんん（つまり、購読リストが常にライブになっています）。
* **[!UICONTROL 期限切れ]**：終了日が過ぎたので、購読リストは無効になりました。購読されたプロファイルには、今後この購読リストに関するお知らせは届きません。


## 購読リストの監視 {#monitor-subscription-lists}

専用のレポートを通じて、購読リストの影響を監視できます。 次の 2 種類のレポートにアクセスできます。

* 購読リストライブレポート

  「過去 24 時間」タブからアクセスできるライブレポートには、過去 24 時間以内に発生したイベントが、イベント発生から最小 2 分の時間間隔で表示されます。[詳細情報](../reports/subscription-report-live.md)

* 購読リスト Customer Journey Analyticsを使用した、すべての時間レポート

  これらのレポートは、少なくとも 2 時間前に発生したイベントに焦点を当て、選択した期間のイベントが表示されます。 **購読レポート** は、特定のリストに関連付けられたプロファイルの購読と購読解除に関する重要なインサイトを提供し、エンゲージメントとコンバージョンを促進するうえで、様々な購読キャンペーンやイニシアチブの効果を理解するのに役立ちます。 [詳細情報](../reports/subscription-report-global-cja.md)

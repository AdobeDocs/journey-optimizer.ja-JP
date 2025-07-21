---
solution: Journey Optimizer
product: journey optimizer
title: API トリガーキャンペーンのレビューとアクティブ化
description: API トリガーキャンペーンをレビューおよびアクティブ化する方法について説明します。
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: キャンペーン, API トリガー, REST, Optimizer, メッセージ
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 53%

---


# API トリガーキャンペーンのレビューとアクティブ化 {#api-review}

アクションキャンペーンを設定したら、アクティブ化する前にそのパラメーターとコンテンツをレビューする必要があります。 それには、次の手順に従います。

>[!IMPORTANT]
>
> キャンペーンが承認ポリシーの対象となっている場合、キャンペーンを送信できるようにするには、承認をリクエストする必要があります。[詳細情報](../test-approve/gs-approval.md)

1. キャンペーンの設定画面で、「**[!UICONTROL アクティブ化するレビュー]**」をクリックして、キャンペーンの概要を表示します。

   ![](assets/campaign-review.png)

1. キャンペーン設定の概要が表示され、パラメーターが正しくないか、見つからないかを確認し、必要に応じてキャンペーンを変更できます。

   エラーが発生した場合は、キャンペーンをアクティブ化できません。続行する前にエラーを解決します。

   ![](assets/create-campaign-alerts.png)

1. キャンペーンが正しく設定されていることを確認してから、「**[!UICONTROL アクティブ化]**」をクリックします。

1. キャンペーンがアクティブ化されます。 ステータスは **[!UICONTROL ライブ]**、開始日を入力した場合は **[!UICONTROL スケジュール済み]** です。

   **[!UICONTROL 完了]** ステータスは、キャンペーンがアクティブ化されてから 3 日後、または繰り返し実行されている場合はキャンペーンの終了日に自動的に割り当てられます。 [詳しくは、キャンペーンのステータスを参照してください](get-started-with-campaigns.md#statuses)。

   終了日が指定されていない場合、キャンペーンは **[!UICONTROL ライブ]** ステータスのままとなります。 変更するには、キャンペーンを手動で停止する必要があります。[キャンペーンの停止方法についてはこちらを参照](modify-stop-campaign.md)


1. キャンペーンがアクティブ化されると、キャンペーンを開いて、いつでもその情報を確認できます。概要では、ターゲットプロファイルの数と、配信されたアクションおよび失敗したアクションの数に関する統計情報を取得できます。

   「**[!UICONTROL レポート]**」ボタンをクリックして、専用レポートでさらに統計情報を取得することもできます。([詳細情報](../reports/campaign-global-report-cja.md))

   ![](assets/create-campaign-summary.png)

## 次の手順 {#next}

API トリガーキャンペーンの準備が整ったら、API を使用して実行をトリガーできます。 [詳細情報](trigger-campaigns.md)

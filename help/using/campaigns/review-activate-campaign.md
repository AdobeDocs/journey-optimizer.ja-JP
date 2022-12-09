---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの確認とアクティブ化
description: でキャンペーンを確認およびアクティブ化する方法について説明します。 [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 7c4afc98-0d79-4e26-90f8-558bac037169
source-git-commit: fa5a3cc25fa083754e00dbde7743e032c065f210
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# キャンペーンの確認とアクティブ化 {#review-activate}

キャンペーンの設定が完了したら、アクティブ化する前に、そのパラメーターとコンテンツを確認する必要があります。 これを行うには、次の手順を実行します。

1. キャンペーンコンフィギュレーション画面で、をクリックし **[!UICONTROL Review to activate]** て、キャンペーンの概要を表示します。

   この概要を使用して、必要に応じてキャンペーンを変更し、パラメーターが間違っていたり、失われていないかどうかをチェックすることができます。

   >[!IMPORTANT]
   >
   >エラーが発生した場合は、キャンペーンのライセンス認証を行うことはできません。 続行する前に、エラーを解決してください。

   ![](assets/create-campaign-alerts.png)

1. キャンペーンが正しく設定されていることを確認してから、をクリック **[!UICONTROL Activate]** します。

   ![](assets/create-campaign-review.png)

1. これで、キャンペーンが有効になります。 その状態は、開始日を入力した場合に **[!UICONTROL Scheduled]** 表示さ **[!UICONTROL Live]** れます。[キャンペーンのステータス ](get-started-with-campaigns.md#statuses) に関する詳細情報を表示します。

   キャンペーンに設定されたメッセージは、ただちに送信されるか、指定した日付に送られます。

   >[!NOTE]
   >
   >**[!UICONTROL Completed]**&#x200B;状態は、有効にされた後3日後、またはキャンペーンが定期的に実行された場合に、自動的にキャンペーンに割り当てられます。
   >
   >終了日を指定しなかった場合は、キャンペーンにより状態が維持 **[!UICONTROL Live]** されます。 この設定を変更するには、キャンペーンを手動で停止する必要があります。 [キャンペーンの停止方法について学習します。](modify-stop-campaign.md)

1. キャンペーンがアクティブになった後は、いつでもその情報を開くことができます。 この概要を使用して、ターゲットのプロファイル数と配信および失敗したアクションについての統計情報を取得することができます。

   ボタンをクリックしても、 **[!UICONTROL Reports]** 専用レポートに追加の統計情報を表示できます。 [詳細情報](../reports/campaign-global-report.md)

   ![](assets/create-campaign-summary.png)

---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Journey Optimizerを使用した調整されたキャンペーンの開始と監視
description: Adobe Journey Optimizerでオーケストレーションされたキャンペーンを開始および監視する方法について説明します。
hide: true
hidefromtoc: true
exl-id: 5fc2d1d6-75c3-4b45-bb2b-09982b9bd5ed
source-git-commit: 5ebc82f566d416a177a3278816c60d896a10eff6
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 19%

---

# 調整されたキャンペーンの開始と監視 {#start-monitor}

>[!CONTEXTUALHELP]
>id="ajo_campaign_publication"
>title="調整されたキャンペーンの公開"
>abstract="キャンペーンを開始するには、公開する必要があります。公開前に、すべての警告がクリアされていることを確認します。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md) | [ キャンペーンの作成を調整するための主な手順 ](gs-campaign-creation.md)<br/><br/>[ キャンペーンの作成およびスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティの調整 ](orchestrate-activities.md)<br/><br/><b>[ キャンペーンの開始および監視 ](start-monitor-campaigns.md)</b><br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [&#128279;](activities/save-audience.md) [&#128279;](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

キャンバスで実行するタスクを調整および設計して作成したら、そのタスクを公開し、実行方法を監視できます。

また、キャンペーンをテストモードで実行して、その実行と様々なアクティビティの結果を確認することもできます。

## 公開前にキャンペーンをテスト {#test}

Journey Optimizerでは、運用開始前に調整されたキャンペーンをテストできます。 テストモードでは、**[!UICONTROL オーディエンスを保存]** アクティビティとチャネルアクティビティを除く、キャンバス内のすべてのアクティビティが実行されます。 データやオーディエンスへの機能的な影響はありません。

キャンペーンをテストするには：

1. オーケストレーションされたキャンペーンを開きます。
2. 「**[!UICONTROL 開始]**」をクリックします。

![](assets/campaign-start.png){zoomable="yes"}

キャンペーン内の各アクティビティは、図の最後に達するまで順番に実行されます。 テストの実行中に、キャンバスのアクションバーを使用してキャンペーンを管理できます。 ここから、次のことができます。

* **停止** 実行はいつでも行います。
* **開始** 実行を再度行います。
* **再開** 問題が原因で以前に実行が一時停止された場合、実行します。

実行中にエラーや警告が発生した場合は、キャンバスツールバーの **[!UICONTROL アラート]**/**[!UICONTROL 警告]** アイコンで通知されます。

![](assets/campaign-warning.png){zoomable="yes"}

また、各アクティビティに直接表示される [ 視覚的なステータスインジケーター ](#activities) を使用して、失敗したアクティビティをすばやく識別することもできます。 トラブルシューティングについて詳しくは、[campaign のログ ](#logs-tasks) を開くと、エラーとそのコンテキストに関する詳細が表示されます。

## キャンペーンの公開 {#publish}

キャンペーンがテストされ、準備が整ったら、「**[!UICONTROL 公開]**」をクリックしてライブにします。

![](assets/campaign-publish.png){zoomable="yes"}

視覚的なフローが再開し、実際のプロファイルがジャーニーをリアルタイムで流れ始めます。

## キャンペーン実行の監視 {#monitor}

### 視覚的なフロー監視 {#flow}

（テストモードまたはライブモードで）実行中、視覚的なフローは、プロファイルがジャーニー内をどのように移動するかをリアルタイムで示します。 タスク間で移行中のプロファイルの数が表示されます。

![](assets/workflow-execution.png){zoomable="yes"}

トランジションによって 1 つのアクティビティから別のアクティビティに移されたデータは、一時的なワークテーブルに保存されます。 このデータは、トランジションごとに表示できます。アクティビティ間で渡されるデータを検査するには：

1. トランジションを選択します。
1. プロパティペインで **[!UICONTROL スキーマをプレビュー]** をクリックし、ワークテーブルのスキーマを表示します。 **[!UICONTROL 結果をプレビュー]** を選択して、転送されたデータを表示します。

![](assets/transition.png){zoomable="yes"}

### アクティビティ実行指標 {#activities}

視覚的なステータス指標は、各アクティビティのパフォーマンスを把握するのに役立ちます。

| 視覚的な指標 | 説明 |
|-----|------------|
| ![](assets/activity-status-pending.png){zoomable="yes"}{width="70%"} | このアクティビティは現在実行中です。 |
| ![](assets/activity-status-orange.png){zoomable="yes"}{width="70%"} | このアクティビティには注意が必要です。これには、配信の送信確認や、必要なアクションの実行が含まれる場合があります。 |
| ![](assets/activity-status-red.png){zoomable="yes"}{width="70%"} | アクティビティでエラーが発生しました。この問題を解決するには、調整されたキャンペーンログを開いて詳細を確認します。 |
| ![](assets/activity-status-green.png){zoomable="yes"}{width="70%"} | アクティビティが正常に実行されました。 |

### ログとタスク {#logs-tasks}

>[!CONTEXTUALHELP]
>id="ajo_campaign_logs"
>title="ログとタスク"
>abstract="**ログとタスク** 画面には、調整されたキャンペーンの実行履歴が表示され、すべてのユーザーのアクションと発生したエラーが記録されます。"

ログとタスクの監視は、調整されたキャンペーンを分析し、それらが正しく実行されていることを確認するための重要な手順です。 ログとタスクには、「**[!UICONTROL ログ]**」ボタンからアクセスできます。このボタンは、キャンバスツールバーのテストモードとライブモードの両方、または各アクティビティのプロパティパネルで使用できます。

**[!UICONTROL ログとタスク]** 画面には、キャンペーンの実行の完全な履歴が表示され、すべてのユーザーのアクションと発生したエラーが記録されます。

![](assets/workflow-logs.png){zoomable="yes"}

次の 2 種類の情報を使用できます。

* 「**[!UICONTROL ログ]**」タブには、すべての操作とエラーの時系列の履歴が表示されます。
* **[!UICONTROL タスク]** タブでは、アクティビティの実行シーケンスの詳細が手順ごとに表示されます。

両方のタブで、表示される列とその順序を選択し、フィルターを適用し、検索フィールドを使用して目的の情報をすばやく見つけることができます。

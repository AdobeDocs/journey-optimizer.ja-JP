---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーン作成の主な手順
description: Adobe Journey Optimizerを使用したオーケストレートキャンペーン作成の主な原則について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: b04aa15a-71bf-4683-bcbf-f611c189ffe1
source-git-commit: 935ab0399da88c792104b7dc14793b69713951fc
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 24%

---


# 調整されたキャンペーン作成の主な手順 {#orchestrated-campaign-creation}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | キャンペーンアクティビティをキャンセル |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md) | <b>[ オーケストレーションされたキャンペーンの作成 ](gs-campaign-creation.md)</b><br/><br/>[ キャンペーンの作成と設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](send-messages.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ 分割 ](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

調整されたキャンペーンを視覚的なキャンバスに作成して、セグメント化、キャンペーン実行、ファイル処理などのクロスチャネルプロセスを設計できます。

## 調整されたキャンペーンへのアクセス

**[!UICONTROL キャンペーン]** メニューで、複数手順タブを参照し、オーケストレーションされたキャンペーンの完全なリストにアクセスします。

リスト内のオーケストレーションされた各キャンペーンには、現在の [ ステータス ](#status)、前回の実行または変更日時、および次にスケジュールされた実行日時に関する情報が表示されます。

リストの右上隅にある「**[!UICONTROL カスタムレイアウトの列を設定]**」アイコンをクリックすると、表示される列をカスタマイズできます。これにより、オーケストレーションされた各キャンペーンでエラーになった最後のアクティビティや、適用されたターゲティングディメンションなどの情報をリストに追加できます。

また、検索バーとフィルターを使用して、リスト内での検索を簡単にすることができます。例えば、オーケストレーションされたキャンペーンをフィルタリングして、キャンペーンに属するキャンペーンや、特定の日付範囲内に処理されたキャンペーンのみを表示できます。

オーケストレーションされたキャンペーンを複製または削除するには、省略記号ボタンをクリックし、**[!UICONTROL 複製]** または **[!UICONTROL 削除]** を選択します。

>[!NOTE]
>
>オーケストレーションされたキャンペーンが進行中の場合、そのキャンペーンは複製できますが、削除することはできません。

## オーケストレーションされたキャンペーンの内部とは {#gs-ms-campaign-inside}

調整されたキャンペーンキャンバスは、実行される処理を表現したものです。 これは、実行される様々なタスクと、タスク同士の関係を示すものです。

![](assets/workflow-example.png){zoomable="yes"} {zoomable="yes"}

調整された各キャンペーンには、次が含まれます。

* **アクティビティ**：アクティビティとは、実行されるタスクです。各種アクティビティは、ダイアグラム内にアイコンで示されます。各アクティビティには、特定のプロパティと、すべてのアクティビティに共通のその他のプロパティがあります。

  調整されたキャンペーン図では、特定のアクティビティが、特にループまたは繰り返しアクションがある場合に複数のタスクを生成できます。

* **トランジション**：トランジションは、ソースアクティビティを宛先アクティビティにリンクし、そのシーケンスを定義します。

* **作業用テーブル**：作業用テーブルには、トランジションによって実行されるすべての情報が含まれます。調整されたキャンペーンごとに、複数のワークテーブルが使用されます。 これらのテーブルで伝達されたデータは、調整されたキャンペーンのライフサイクルを通じて使用できます。

## ステータスとライフサイクル {#status}

キャンペーンには複数のステータスがあります。

* **[!UICONTROL ドラフト]**：オーケストレーションされたキャンペーンが作成され、保存されました。
* **[!UICONTROL 処理中]**：オーケストレーションされたキャンペーンは現在実行中です。
* **[!UICONTROL 完了]**：調整されたキャンペーンの実行が完了しました。
* **[!UICONTROL 一時停止]**：オーケストレーションされたキャンペーンが一時停止されました。
* **[!UICONTROL エラー]**：オーケストレーションされたキャンペーンでエラーが発生しました。 調整したキャンペーンを開き、ログとタスクにアクセスしてエラーを特定し解決します。

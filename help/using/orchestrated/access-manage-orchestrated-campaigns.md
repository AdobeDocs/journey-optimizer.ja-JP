---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンへのアクセスと管理
description: Adobe Journey Optimizerを使用したオーケストレートキャンペーン作成の主な原則について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 7b42d317-cd01-4c6a-b61e-5b03e5a8ff3c
source-git-commit: cd42bca1a36344f688b2d90e1c0b96a9ef2a53ce
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 22%

---

# 調整されたキャンペーンへのアクセスと管理 {#orchestrated-campaign-creation}

>[!CONTEXTUALHELP]
>id="ajo_targeting_workflow_list"
>title="調整されたキャンペーン"
>abstract="この画面では、調整されたキャンペーンの完全なリストにアクセスし、現在のステータス、前回／次回の実行日を確認して、新しい調整されたキャンペーンを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_campaign_action"
>title="アクション"
>abstract="この節では、オーケストレーションされたキャンペーン内で使用されるすべてのアクションを示します。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/><b>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)</b> | [ オーケストレーションされたキャンペーンの作成 ](gs-campaign-creation.md)<br/><br/>[ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](send-messages.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ 分割 ](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

## 調整されたキャンペーンへのアクセス

**[!UICONTROL キャンペーン]** メニューに移動し、「**[!UICONTROL オーケストレーション]** タブを選択して、オーケストレーションされたキャンペーンの完全なリストにアクセスします。

![ オーケストレーションされたキャンペーンのインベントリを示す画像 ](assets/inventory.png){zoomable="yes"}{zoomable="yes"}

リスト内でオーケストレーションされた各キャンペーンには、キャンペーンの現在の [ ステータス ](#status)、関連付けられたチャネルとタグ、前回の変更日時などの情報が表示されます。 「![ レイアウトの設定 ](assets/do-not-localize/inventory-configure-layout.svg) ボタンをクリックすると、表示される列をカスタマイズできます。

また、検索バーとフィルターを使用して、リスト内での検索を簡単にすることができます。例えば、オーケストレーションされたキャンペーンをフィルタリングして、特定のチャネルやタグに関連付けられているキャンペーンや、特定の日付範囲内に作成されたキャンペーンのみを表示できます。

## オーケストレーションされたキャンペーンの内部とは {#gs-ms-campaign-inside}

調整されたキャンペーンキャンバスは、実行される処理を表現したものです。 これは、実行される様々なタスクと、タスク同士の関係を示すものです。

![ 調整されたキャンペーンキャンバスを示す画像 ](assets/canvas-example.png){zoomable="yes"}{zoomable="yes"}

調整された各キャンペーンには、次が含まれます。

* **アクティビティ**：アクティビティとは、実行されるタスクです。各種アクティビティは、ダイアグラム内にアイコンで示されます。各アクティビティには、特定のプロパティと、すべてのアクティビティに共通のその他のプロパティがあります。

  調整されたキャンペーン図では、特定のアクティビティが、特にループまたは繰り返しアクションがある場合に複数のタスクを生成できます。

* **トランジション**：トランジションは、ソースアクティビティを宛先アクティビティにリンクし、そのシーケンスを定義します。

* **作業用テーブル**：作業用テーブルには、トランジションによって実行されるすべての情報が含まれます。調整されたキャンペーンごとに、複数のワークテーブルが使用されます。 これらのテーブルで伝達されたデータは、調整されたキャンペーンのライフサイクルを通じて使用できます。

## キャンペーンのステータス {#status}

調整されたキャンペーンには、次の複数のステータスがあります。

* **[!UICONTROL ドラフト]**：オーケストレーションされたキャンペーンが作成されました。 まだ公開されていません。
* **[!UICONTROL 公開中]**：オーケストレーションされたキャンペーンを公開しています。
* **[!UICONTROL ライブ]**：オーケストレーションされたキャンペーンが公開され、実行中です。
* **[!UICONTROL スケジュール済み]**：オーケストレーションされたキャンペーンの実行がスケジュールされています。
* **[!UICONTROL 完了]**：オーケストレーションされたキャンペーンの実行が完了しました。 キャンペーンがエラーなしでメッセージの送信を完了してから最大 3 日後に、完了ステータスが自動的に割り当てられます。
* **[!UICONTROL 終了]**：このステータスは、繰り返しキャンペーンが停止されたときに表示されます。
<!--Comment une campaign devient Closed?
[CPR] : A vérifier avec Fred si cette fonctionalité est toujours d'actualité. Normalement c'est sur action de l'utilisateur sur une campaine récurrente only
= pas trouvé-->
* **[!UICONTROL アーカイブ済み]**：オーケストレーションされたキャンペーンはアーカイブされています。 アーカイブされたすべてのキャンペーンは、最終変更日から 30 日後にローリング再スケジュールで削除されます。 必要に応じて、アーカイブしたキャンペーンを複製して、作業を続行できます。
<!--Comment une campaign devient Archived?
[CPR] : Soit par action manuel sur une campagne en statut "final" (Completed, Closed, Stopped, etc. ...)
= pas trouvé -->
* **[!UICONTROL 停止]**：オーケストレーションされたキャンペーンの実行が停止しました。 キャンペーンを再度開始するには、複製する必要があります。

## 調整されたキャンペーンの複製と削除 {#duplicate-delete}

停止されたキャンペーンを実行したり、スケジュールされたキャンペーンの実行頻度を変更したりするために、オーケストレーションされたキャンペーンを複製する必要が生じる場合があります。 これを行うには、キャンペーンインベントリの「![ その他のアクション」ボタンを示す画像 ](assets/do-not-localize/rule-builder-icon-more.svg) ボタンをクリックし、「複製 **[!UICONTROL を選択します]**

<!--Une fois une campaign Scheduled, on ne peut plus changer l'execution frequency = la solution est de dupliquer la campaign ?
[CPR] : Actuellement oui, mais on est en discussion pour pouvoir revenir en mode "draft" et quelles seraient les actions à nouveau disponibles. A vérifier avec Fred-->

キャンペーンを削除するには、「![ その他のアクション」ボタンを示す画像 ](assets/do-not-localize/rule-builder-icon-more.svg) ボタンをクリックし、「**[!UICONTROL 削除]**」を選択します。

>[!NOTE]
>
>削除できるキャンペーンは **[!UICONTROL ドラフト]** のみです。

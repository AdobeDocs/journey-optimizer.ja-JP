---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンへのアクセスと管理
description: Adobe Journey Optimizerを使用したオーケストレートキャンペーン作成の主な原則について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 7b42d317-cd01-4c6a-b61e-5b03e5a8ff3c
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 48%

---

# 調整されたキャンペーンへのアクセスと管理 {#orchestrated-campaign-creation}

>[!CONTEXTUALHELP]
>id="ajo_targeting_workflow_list"
>title="調整されたキャンペーン"
>abstract="この画面では、オーケストレートキャンペーンの完全なリストにアクセスし、現在のステータス、最後/次回の実行日を確認して、新しいオーケストレートキャンペーンを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_campaign_action"
>title="アクション"
>abstract="この節では、オーケストレートキャンペーン内で使用されるすべてのアクションを示します。"

+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](gs-schemas.md)</li><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul><br/><br/><b>[ オーケストレートキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)</b><br/><br/>[ オーケストレートキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [キャンペーンの作成とスケジュール](create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](start-monitor-campaigns.md)<br/><br/>[レポート](reporting-campaigns.md) | [ルールビルダーの操作](orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](build-query.md)<br/><br/>[式の編集](edit-expressions.md)<br/><br/>[リターゲティング](retarget.md) | [アクティビティの基本を学ぶ](activities/about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](activities/and-join.md) - [オーディエンスを作成](activities/build-audience.md) - [ディメンションを変更](activities/change-dimension.md) - [チャネルアクティビティ](activities/channels.md) - [結合](activities/combine.md) - [重複排除](activities/deduplication.md) - [エンリッチメント](activities/enrichment.md) - [分岐](activities/fork.md) - [紐付け](activities/reconciliation.md) - [オーディエンスを保存](activities/save-audience.md) - [分割](activities/split.md) - [待機](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

## オーケストレーションされたキャンペーンへのアクセス

**[!UICONTROL キャンペーン]** メニューに移動し、「**[!UICONTROL オーケストレーション]** タブを選択して、オーケストレーションされたキャンペーンの完全なリストにアクセスします。

![ オーケストレーションされたキャンペーンのインベントリを示す画像 ](assets/inventory.png){zoomable="yes"}{zoomable="yes"}

リスト内のオーケストレーションされた各キャンペーンには、キャンペーンの現在の [ ステータス ](#status)、関連するチャネルとタグ、前回の変更日時などの情報が表示されます。 ![「レイアウトを設定」ボタン](assets/do-not-localize/inventory-configure-layout.svg) ボタンをクリックすると、表示される列をカスタマイズできます。

また、検索バーとフィルターを使用して、リスト内での検索を簡単にすることができます。例えば、オーケストレートキャンペーンをフィルタリングして、特定のチャネルやタグに関連付けられているキャンペーンや、特定の日付範囲内に作成されたキャンペーンのみを表示できます。

キャンペーン在庫の ![「その他のアクション」ボタンを示す画像](assets/do-not-localize/rule-builder-icon-more.svg) ボタンを使用すると、以下に説明する様々な操作を実行できます。

![キャンペーン在庫の画像](assets/inventory-actions.png)

* **[!UICONTROL 全期間のレポートを表示]**／**[!UICONTROL 過去 24 時間のレポートを表示]** - レポートにアクセスして、調整されたキャンペーンの影響とパフォーマンスを測定および視覚化します。[ オーケストレートキャンペーンレポートについて詳しくはこちらを参照 ](../orchestrated/reporting-campaigns.md)
* **[!UICONTROL タグを編集]** - キャンペーンに関連付けられたタグを編集します。
* **[!UICONTROL 複製]** – 停止されたキャンペーンを実行したり、スケジュールされたキャンペーンの実行頻度を変更したりするために、オーケストレーションされたキャンペーンを複製する必要がある場合があります。
* **[!UICONTROL 削除]** - キャンペーンを削除します。このアクションは、**[!UICONTROL ドラフト]**&#x200B;キャンペーンでのみ使用できます。
* **[!UICONTROL アーカイブ]** - キャンペーンをアーカイブします。すべてのアーカイブ済みキャンペーンは、最終変更日から 30 日後にローリング再スケジュールで削除されます。このアクションは、**[!UICONTROL ドラフト]**&#x200B;キャンペーンを除くすべてのキャンペーンで使用できます。

## Orchestrated キャンペーンの内部とは {#gs-ms-campaign-inside}

オーケストレーションされたキャンペーンキャンバスは、実行される処理を表現したものです。 これは、実行される様々なタスクと、タスク同士の関係を示すものです。

![ オーケストレーションされたキャンペーンキャンバスを示す画像 ](assets/canvas-example.png)

調整された各キャンペーンには、次が含まれます。

* **アクティビティ**：アクティビティとは、実行されるタスクです。各種アクティビティは、ダイアグラム内にアイコンで示されます。各アクティビティには、特定のプロパティと、すべてのアクティビティに共通のその他のプロパティがあります。

  オーケストレーションされたキャンペーンのダイアグラムでは、特定のアクティビティが、特にループまたは繰り返しアクションがある場合に複数のタスクを生成できます。

* **トランジション**：トランジションは、ソースアクティビティを宛先アクティビティにリンクし、そのシーケンスを定義します。

* **ワークテーブル**：ワークテーブルには、トランジションによって実行されるすべての情報が含まれます。調整されたキャンペーンごとに、複数のワークテーブルが使用されます。 これらのテーブルで伝達されたデータは、調整されたキャンペーンのライフサイクルを通じて使用できます。

## キャンペーンのステータス {#status}

調整されたキャンペーンには複数のステータスがあります。

* **[!UICONTROL ドラフト]**：オーケストレーションされたキャンペーンが作成されました。 まだ公開されていません。
* **[!UICONTROL 公開中]**：オーケストレーションされたキャンペーンを公開しています。
* **[!UICONTROL ライブ]**：オーケストレーションされたキャンペーンが公開され、実行中です。
* **[!UICONTROL スケジュール済み]**：オーケストレーションされたキャンペーンの実行がスケジュールされています。
* **[!UICONTROL 完了]**：オーケストレーションされたキャンペーンの実行が完了しました。 キャンペーンがエラーなしでメッセージの送信を完了してから最大 3 日後に、完了ステータスが自動的に割り当てられます。
* **[!UICONTROL クローズ済み]**：このステータスは、繰り返しキャンペーンがクローズされた際に表示されます。キャンペーンはすべてのアクティビティが完了するまで引き続き実行しますが、それ以上のプロファイルはキャンペーンにエントリできません。
* **[!UICONTROL アーカイブ済み]**：オーケストレーションされたキャンペーンはアーカイブされています。 すべてのアーカイブ済みキャンペーンは、最終変更日から 30 日後にローリング再スケジュールで削除されます。必要に応じて、アーカイブ済みキャンペーンを複製して、引き続き作業できます。
* **[!UICONTROL 停止]**：オーケストレーションされたキャンペーンの実行が停止しました。 キャンペーンを再度開始するには、複製する必要があります。

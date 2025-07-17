---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンのガードレールと制限
description: オーケストレートキャンペーンのガードレールと制限について学ぶ
hide: true
hidefromtoc: true
exl-id: 82744db7-7358-4cc6-a9dd-03001759fef7
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# ガードレールと制限 {#guardrails}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](gs-schemas.md)</li><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [ ](activities/save-audience.md) [ ](activities/split.md) [ ](activities/wait.md) - |

{style="table-layout:fixed"}

+++

## データフローからデータセットへの制限

Adobe Experience Platformの各データセットは、一度に 1 つのアクティブなデータフローにのみ関連付けることができます。 この 1:1 のカーディナリティは、プラットフォームによって厳密に適用されます。

データソースを切り替える必要がある場合（例：Amazon S3 からSalesforce）:

データセットに接続されている既存のデータフローを削除する必要があります。

次に、同じデータセットにマッピングされた新しいソースを使用して、新しいデータフローを作成します。

これにより、信頼性の高いデータ取り込みが確保されます。これは、増分更新のために定義されたプライマリキーとバージョン属性（lastmodified など）に依存する Change Data Capture （CDC）を使用する場合に不可欠です。


## リレーショナルスキーマ/データ取り込みの制限

* スキーマ数 – リレーショナルスキーマ（リレーショナルデータストア内のテーブル）の最大数は 200 です
* リレーショナルスキーマのサイズ – キャンペーンオーケストレーションの最大リレーショナルスキーマのサイズは 100 GB です。
* データ取り込み頻度 – Campaign オーケストレーションのバッチデータ取り込み頻度は、15 分ごとに 1 つを超えないようにします。
* 変更/更新 – 毎日の更新/変更は、特定のリレーショナルスキーマの合計レコードの 20% 未満にする必要があります

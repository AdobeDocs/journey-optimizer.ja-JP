---
solution: Journey Optimizer
product: journey optimizer
title: 設定の手順
description: DDL をアップロードしてAdobe Experience Platform内にリレーショナルスキーマを作成する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
source-git-commit: 25120dd71159d0233783ac4c189f528ff2c93ae3
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 5%

---

# スキーマと関連の基本を学ぶ {#file-upload-schema}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [&#128279;](activities/save-audience.md) [&#128279;](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

このガイドでは、リレーショナルスキーマの作成、オーケストレートキャンペーン用のデータセットの設定、S3 ソースを介したデータの取り込み、AP プラットフォームで取り込んだデータのクエリのプロセスについて説明します。

この例では、設定に 2 つの主要なエンティティ **ロイヤルティトランザクション** と **ロイヤルティ報酬** の統合が含まれており、それらを既存のコアエンティティ **受信者** と **ブランド** にリンクしています。

![](assets/do-not-localize/schema_admin.png)

1. [リレーショナルスキーマと関連するデータセットの作成](#schema)

   **ロイヤルティメンバーシップ**、**ロイヤルティトランザクション**、**ロイヤルティ報酬** エンティティ、必須のキーおよびバージョン属性など、調整されたキャンペーンのリレーショナルデータモデルを定義します。

1. [スキーマをリンク](#link-schema)

   **ロイヤルティトランザクション** エンティティを **受信者** に、**ロイヤルティ報酬** を **ブランド** にリンクして、パーソナライズされたカスタマージャーニーをサポートする接続されたデータモデルを作成します。

1. [データの取り込み](#ingest)

   SFTP、クラウドストレージ、データベースなど、サポートされているソースからAdobe Experience Platformにデータを取り込みます。


<!--### Setting Up Change data capture ingestion {#cdc-ingestion}

If you need to change the data source, you must delete the existing dataflow and create a new one pointing to the same dataset with the new source.

When using Change Data Capture (CDC), it is essential that the source and dataset remain in sync to ensure accurate incremental updates. Follow the steps below:

1. **Schema Requirements**
   - Your schema must include:
     - A **primary key** (e.g., `transaction_id`)
     - A **versioning field** (e.g., `lastmodified` or an incrementing `version_id`)
   - Enable the dataset for **Orchestrated Campaigns** if needed.

2. **CDC Dataflow Setup**
   - During dataflow creation, after choosing your source and files:
     - **Enable the CDC option**
     - Select your CDC-ready dataset
     - Confirm field mappings (especially version field)

3. **Keep Source and Target in Sync**
   - The source system must consistently update the version field so the platform can detect changes accurately.

Once set up, the platform will automatically ingest **only changed or new records** each time the flow runs.
-->

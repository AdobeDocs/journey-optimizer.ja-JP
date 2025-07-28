---
solution: Journey Optimizer
product: journey optimizer
title: 設定の手順
description: DDL をアップロードしてAdobe Experience Platform内にリレーショナルスキーマを作成する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 327597f6-8a53-42dc-966a-baae49b58bb3
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 25%

---

# スキーマとデータセットの基本を学ぶ{#gs-schemas}

+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](gs-schemas.md)</li><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul>[ オーケストレートキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレートキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [キャンペーンの作成とスケジュール](create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](start-monitor-campaigns.md)<br/><br/>[レポート](reporting-campaigns.md) | [ルールビルダーの操作](orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](build-query.md)<br/><br/>[式の編集](edit-expressions.md)<br/><br/>[リターゲティング](retarget.md) | [アクティビティの基本を学ぶ](activities/about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](activities/and-join.md) - [オーディエンスを作成](activities/build-audience.md) - [ディメンションを変更](activities/change-dimension.md) - [チャネルアクティビティ](activities/channels.md) - [結合](activities/combine.md) - [重複排除](activities/deduplication.md) - [エンリッチメント](activities/enrichment.md) - [分岐](activities/fork.md) - [紐付け](activities/reconciliation.md) - [オーディエンスを保存](activities/save-audience.md) - [分割](activities/split.md) - [待機](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

このガイドでは、リレーショナルスキーマの作成、オーケストレートキャンペーン用のデータセットの設定、データの取り込みのプロセスについて説明します。

![](assets/do-not-localize/schema_admin.png)

1. [ リレーショナルスキーマを手動で ](manual-schema.md) または [DDL ファイルを使用して ](file-upload-schema.md) 作成

   テーブル、属性、関係を含む、データモデルの構造を定義します。 ユーザーインターフェイスでスキーマを手動で作成するか、DDL ファイルをアップロードしてセットアップを迅速化するかを選択します。

1. [スキーマをリンク](file-upload-schema.md)

   スキーマ間の関係を確立してデータの一貫性を確保し、クロスエンティティクエリを有効にします。 例えば、ロイヤルティトランザクションを受信者にリンクしたり、報酬をブランドにリンクしたりします。

1. [データを取得](ingest-data.md)

   サポートされているソース（SFTP、クラウドストレージ、データベースなど）からAdobe Experience Platformにデータを取り込みます。


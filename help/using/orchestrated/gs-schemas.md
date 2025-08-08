---
solution: Journey Optimizer
product: journey optimizer
title: 設定の手順
description: DDL をアップロードしてAdobe Experience Platform内にリレーショナルスキーマを作成する方法を説明します
exl-id: 327597f6-8a53-42dc-966a-baae49b58bb3
source-git-commit: 7fc03d15c63789a2c35e3d517ca0c63f93545d4c
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 3%

---


# リレーショナルスキーマとデータセットの基本を学ぶ{#gs-schemas}

このガイドでは、リレーショナルスキーマの作成、オーケストレートキャンペーン用のデータセットの設定、データの取り込みのプロセスについて説明します。

![](assets/do-not-localize/schema_admin.png)

1. [ リレーショナルスキーマを手動で ](manual-schema.md) または [DDL ファイルを使用して ](file-upload-schema.md) 作成

   テーブル、属性、関係を含む、データモデルの構造を定義します。 ユーザーインターフェイスでスキーマを手動で作成するか、DDL ファイルをアップロードしてセットアップを迅速化するかを選択します。

   また、スキーマを手動で作成する場合は、データセットも手動で作成して有効にする必要があります。 DDL ファイルを使用する場合、データセットの作成とイネーブルメントは自動的に行われます。

1. [スキーマをリンク](file-upload-schema.md)

   スキーマ間の関係を確立してデータの一貫性を確保し、クロスエンティティクエリを有効にします。 例えば、ロイヤルティトランザクションを受信者にリンクしたり、報酬をブランドにリンクしたりします。

1. [データを取得](ingest-data.md)

   サポートされているソース（SFTP、クラウドストレージ、データベースなど）からAdobe Experience Platformにデータを取り込みます。


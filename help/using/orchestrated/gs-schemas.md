---
solution: Journey Optimizer
product: journey optimizer
title: 設定の手順
description: DDL をアップロードして Adobe Experience Platform 内でリレーショナルスキーマを作成する方法について説明します。
exl-id: 327597f6-8a53-42dc-966a-baae49b58bb3
version: Campaign Orchestration
source-git-commit: 07ec28f7d64296bdc2020a77f50c49fa92074a83
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 93%

---


# リレーショナルスキーマとデータセットの基本を学ぶ{#gs-schemas}

このガイドでは、リレーショナルスキーマの作成、調整されたキャンペーン用のデータセットの設定、データの取り込みのプロセスについて説明します。

![](assets/do-not-localize/schema_admin.png)

データセットは、スキーマ（列）とフィールド（行）で構成されるデータコレクション（通常はテーブル）を格納し管理するための構造です。Experience Platformに正常に取り込まれたデータは、データセットとしてデータレイク内に保存されます。

スキーマは、データの構造と形式を表し、検証します。現実のオブジェクト（人物など）の概念上の定義を提供し、そのオブジェクトの各インスタンスに含める必要があるデータ（名前や誕生日など）の概要を説明します。


1. [リレーショナルスキーマを手動](manual-schema.md)で作成するか、[DDL ファイルを使用](file-upload-schema.md)して作成

   テーブル、属性、関係を含むデータモデルの構造を定義します。ユーザーインターフェイスでスキーマを手動で作成するか、設定の高速化に DDL ファイルをアップロードするかを選択します。

   また、スキーマを手動で作成する際は、データセットも手動で作成して有効にする必要があります。DDL ファイルを使用する際、データセットの作成とイネーブルメントは自動的に行われます。

1. [スキーマをリンク](file-upload-schema.md)

   スキーマ間の関係を確立して、データの一貫性を確保し、クロスエンティティクエリを有効にします。例えば、ロイヤルティトランザクションを受信者にリンクしたり、報酬をブランドにリンクしたりします。

1. [データを取得](ingest-data.md)

   SFTP、クラウドストレージ、データベースなどのサポートされているソースからデータを Adobe Experience Platform に取り込みます。


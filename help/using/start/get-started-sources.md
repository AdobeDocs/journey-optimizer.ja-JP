---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer におけるソースコネクタの基本を学ぶ
description: Adobe Journey Optimizer で外部ソースからデータを取り込む方法を説明します
feature: Integrations, Data Ingestion
role: User
level: Beginner
exl-id: 359ea3c6-7746-469e-8a24-624f9726f2d8
source-git-commit: 7864012ad148c2e52bc38598016e7bd7fac9644e
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 11%

---

# ソースコネクタの基本を学ぶ {#sources-gs}

## ソースとは {#what-is-source}

**ソース** は、外部データをAdobe Journey Optimizerに取り込むコネクタです。 ソースを使用すると、CRM プラットフォーム、クラウドストレージ、データベースなど、既に使用しているシステムから顧客情報をインポートし、そのデータをパーソナライズされたカスタマージャーニーの作成に使用できます。

ソースは、Journey Optimizerと外部データシステムの間のブリッジと考えてください。 データが自動的に同期されるので、常に最新の顧客情報を入手してマーケティングキャンペーンを強化できます。

## ソースが重要な理由 {#why-sources-matter}

ソースは、パーソナライズされた、データに基づくJourney Optimizerのカスタマーエクスペリエンスを作成するために不可欠です。 その理由は次のとおりです。

* **統合された顧客表示** – 複数のシステムのデータを組み合わせて、各顧客の全体像を確認できます
* **リアルタイムパーソナライゼーション** – 新しいデータを使用して、適切なメッセージをタイムリーにジャーニーに届けます
* **自動データ同期** – 手動でデータをインポートすることなく、顧客情報を最新の状態に保ちます。
* **効率的なワークフロー** – 一度接続すると、データがジャーニーに自動的に送られます

例えば、ソースを使用して、e コマースプラットフォームから購入履歴を読み込み、顧客が購入したものに基づいてパーソナライズされた製品のお勧めを送信するジャーニーを作成できます。

## ソースの機能 {#sources-use-cases}

Journey Optimizerのソースの一般的なユースケースを次に示します。

* **CRM システムからの顧客データのインポート** - SalesforceやMicrosoft Dynamicsなどのプラットフォームから、連絡先情報、環境設定、エンゲージメント履歴を同期します
* **購入データの接続** - e コマースプラットフォームから注文履歴や製品環境設定を取り込んで、オファーをパーソナライズします
* **ロイヤルティプログラムデータの統合** - アクセスポイントの残高と階層情報を活用して、最も関与した顧客に報酬を与えます
* **行動データの同期** - web サイトのインタラクションとアプリの使用パターンをインポートして、関連するジャーニーをトリガーにします
* **プロファイル属性の更新** - クラウドストレージまたはデータベースからのデータを使用して顧客プロファイルを最新の状態に保ちます

## 一般的なソースタイプ {#source-types}

Journey Optimizerでは、既存のシステムに接続するための様々なタイプのソースがサポートされています。

**Adobe アプリケーション：**
* Adobe Analytics
* Adobe Audience Manager
* Adobe Campaign
* Adobe Commerce

**クラウドストレージ：**
* Amazon S3
* Azure Blob ストレージ
* Google Cloud Storage
* SFTP

**データベース：**
* Amazon Redshift
* Google BigQuery
* Microsoft SQL Server
* MySQL
* PostgreSQL

**CRM とマーケティングの自動化：**
* Microsoft Dynamics
* Salesforce
* Salesforce Marketing Cloud

➡️ 完全なリストについては、[Experience Platform ソースカタログを参照してください ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html#sources-catalog){target="_blank"}

## 始める前に {#prerequisites}

ソースを設定する前に、次のことを確認します。

* **適切な権限** - Adobe Experience Platformでソースを管理するためのアクセス権
* **Source システム資格情報** – 接続する外部システムの認証の詳細
* **データの把握** – 必要なデータフィールドと、それらがJourney Optimizer プロファイルにどのようにマッピングされるかを把握します。

➡️ アクセス制御と権限 [ について ](../administration/permissions.md) しく説明します

## ソースの仕組み {#how-sources-work}

Adobe Journey Optimizerは、Adobe Experience Platformのソースフレームワークを使用します。 基本ワークフローを次に示します。

1. **接続** – 外部データシステムへの認証を設定します
2. **データを選択** - インポートするデータと同期の頻度を選択します
3. **フィールドをマッピング** – 外部データフィールドとJourney Optimizer プロファイル属性との対応方法を定義します
4. **スケジュール** - データの自動更新間隔を設定します
5. **監視** - データフローを追跡し、同期の問題を解決します

設定が完了すると、ソースはバックグラウンドで自動的に実行され、顧客データを最新の状態に保ち、ジャーニーで使用できるようになります。

## 詳細情報 {#learn-more}

![](assets/sources-home.png)

このビデオを視聴すると、ソースコネクタと、Journey Optimizerでソースコネクタを設定する方法を理解できます。

>[!VIDEO](https://video.tv.adobe.com/v/335919?quality=12)

ソースの設定と管理について詳しくは、[Adobe Experience Platform ソースのドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja){target="_blank"} を参照してください。

## 次の手順 {#next-steps}

これで、ソースの概要と重要性を理解できました。

* [ ソースカタログ ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html#sources-catalog){target="_blank"} を参照して、システムのコネクタを見つけます
* 詳細情報 [ ソース接続の作成 ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/overview.html){target="_blank"}
* [ データマッピングと変換 ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/overview.html){target="_blank"} について
* 詳しくは、[ 読み込んだデータをジャーニーで使用する ](../building-journeys/journey-gs.md) を参照してください。

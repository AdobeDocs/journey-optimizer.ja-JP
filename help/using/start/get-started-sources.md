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
workflow-type: ht
source-wordcount: '584'
ht-degree: 100%

---

# ソースコネクタの基本を学ぶ {#sources-gs}

## ソースとは {#what-is-source}

**ソース**&#x200B;とは、外部データを Adobe Journey Optimizer に取り込むコネクタです。ソースを使用すると、CRM プラットフォーム、クラウドストレージ、データベースなど、既に使用しているシステムから顧客情報をインポートし、そのデータをパーソナライズされたカスタマージャーニーの作成に使用できます。

ソースは、Journey Optimizer と外部データシステム間の橋渡しと考えてください。データが自動的に同期されるので、常に最新の顧客情報を入手し、マーケティングキャンペーンを強化できます。

## ソースが重要な理由 {#why-sources-matter}

Journey Optimizer で、パーソナライズされたデータ駆動型のカスタマーエクスペリエンスを作成するには、ソースが不可欠です。理由は次のとおりです。

* **統合顧客ビュー** - 複数のシステムからデータを組み合わせて、各顧客の全体像を確認します
* **リアルタイムパーソナライゼーション** - 新しいデータを使用して、ジャーニーにおいてタイムリーで関連性の高いメッセージを配信します
* **自動データ同期** - 手動でデータをインポートすることなく、顧客情報を最新の状態に保持します
* **効率的なワークフロー** - 一度接続すると、データが自動的にジャーニーにフローされます

例えば、ソースを使用して、e コマースプラットフォームから購入履歴をインポートし、顧客が購入した商品に基づいてパーソナライズされた製品のレコメンデーションを送信するジャーニーを作成できます。

## ソースを使用して実行できること {#sources-use-cases}

Journey Optimizer のソースの一般的なユースケースは次のとおりです。

* **CRM システムから顧客データを読み込む** - Salesforce や Microsoft Dynamics などのプラットフォームから連絡先情報、環境設定、エンゲージメント履歴を同期します
* **購入データの接続** - eコマースプラットフォームから注文履歴や製品の環境設定を取り込んで、オファーをパーソナライズします
* **ロイヤルティプログラムデータの統合** - ポイント残高や階層情報にアクセスし、最も関与した顧客に報酬を提供します
* **行動データの同期** - web サイトのインタラクションやアプリの使用パターンをインポートして、関連性の高いジャーニーをトリガーします
* **プロファイル属性の更新** - クラウドストレージやデータベースからのデータを使用して、顧客プロファイルを最新の状態に保持します

## 一般的なソースタイプ {#source-types}

Journey Optimizer では、既存のシステムに接続するための様々なタイプのソースをサポートしています。

**アドビアプリケーション：**
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

**CRM とマーケティングオートメーション：**
* Microsoft Dynamics
* Salesforce
* Salesforce Marketing Cloud

➡️完全なリストについて詳しくは、[Experience Platform ソースカタログ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja#sources-catalog){target="_blank"}を参照してください

## 始める前に {#prerequisites}

ソースを設定する前に、以下の点を確認します。

* **適切な権限** - Adobe Experience Platform のソースを管理するためのアクセス権
* **ソースシステムの資格情報** - 接続する外部システムの認証の詳細
* **データの理解** - 必要なデータフィールドと、Journey Optimizer プロファイルにマッピングされる仕組みを把握します

➡️詳しくは、[アクセス制御と権限](../administration/permissions.md)を参照してください

## ソースの仕組み {#how-sources-work}

Adobe Journey Optimizer は、Adobe Experience Platform のソースフレームワークを使用します。基本ワークフローを次に示します。

1. **接続** - 外部データシステムへの認証を設定します
2. **データを選択** - インポートするデータと同期する頻度を選択します
3. **フィールドをマッピング** - 外部データフィールドと Journey Optimizer プロファイル属性との対応方法を定義します
4. **スケジュール** - 自動データ更新間隔を設定します
5. **監視** - データフローを追跡し、同期に関する問題を解決します

設定が完了すると、ソースはバックグラウンドで自動的に実行され、顧客データが最新の状態に保持され、ジャーニーで使用できるようになります。

## 詳細情報 {#learn-more}

![](assets/sources-home.png)

ソースコネクタの概要、および Journey Optimizer でのソースコネクタの設定方法について詳しくは、次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/335919?quality=12)

ソースの設定と管理について詳しくは、[Adobe Experience Platform ソースドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja){target="_blank"}を参照してください。

## 次の手順 {#next-steps}

ソースの概要と重要な理由を理解したら、次のことを行います。

* [ソースカタログ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja#sources-catalog){target="_blank"}を参照して、システムのコネクタを見つけます
* [ソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/overview.html?lang=ja){target="_blank"}方法を学びます
* [データマッピングと変換](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/overview.html?lang=ja){target="_blank"}について理解します
* [インポートしたデータをジャーニーで使用](../building-journeys/journey-gs.md)する方法を確認します

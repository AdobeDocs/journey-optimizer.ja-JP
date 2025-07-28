---
solution: Journey Optimizer
product: journey optimizer
title: 設定の手順
description: DDL をアップロードしてAdobe Experience Platform内にリレーショナルスキーマを作成する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 88eb1438-0fe5-4a19-bfb6-2968a427e9e8
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 58%

---

# DDL ファイルを使用したリレーショナルスキーマの作成 {#file-upload-schema}

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

**ロイヤルティメンバーシップ**、**ロイヤルティトランザクション**、**ロイヤルティ報酬** などのスキーマを作成して、調整されたキャンペーンに必要なリレーショナルデータモデルを定義します。 各スキーマには、プライマリキー、バージョン管理属性、参照エンティティへの適切な関係（**Recipients** や **Brands** など）を含める必要があります。

スキーマは、インターフェイスを通じて手動で作成することも、DDL ファイルを使用して一括で読み込むこともできます。

この節では、DDL（データ定義言語）ファイルをアップロードして Adobe Experience Platform 内でリレーショナルスキーマを作成する方法について、手順を追って説明します。DDL ファイルを使用すると、テーブル、属性、キー、関係など、データモデルの構造を事前に定義できます。

1. [DDL ファイルをアップロード ](#ddl-upload) して、リレーショナルスキーマを作成し、その構造を定義します。

1. データモデルのテーブル間の [ 関係の定義 ](#relationships)。

1. [ スキーマをリンク ](#link-schema)：リレーショナルデータを既存のプロファイルエンティティ（受信者やブランドなど）に接続します。

1. サポートされているソースからデータセットへの [ データの取り込み ](ingest-data.md)。

## DDL ファイルのアップロード{#ddl-upload}

DDL ファイルをアップロードすることで、テーブル、属性、キー、関係など、データモデルの構造を事前に定義できます。

Excel ベースのスキーマファイルのアップロードがサポートされています。 [ 提供のテンプレート ](assets/template.zip) をダウンロードして、スキーマ定義を簡単に準備します。

+++Adobe Experience Platformでリレーショナルスキーマを作成する場合、次の機能がサポートされます

* **列挙**\
  ENUM フィールドは、DDL ベースのスキーマ作成と手動のスキーマ作成の両方でサポートされており、許可された値の固定セットを使用して属性を定義できます。

* **データガバナンスのスキーマラベル**\
  ラベル設定は、アクセス制御や使用制限などのデータガバナンスポリシーを適用するためにスキーマフィールドレベルでサポートされています。 詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。

* **複合キー**\
  複合プライマリキーはリレーショナルスキーマ定義でサポートされるので、複数のフィールドを一緒に使用してレコードを一意に識別できます。

+++

1. Adobe Experience Platformにログインします。

1. **データ管理**/**スキーマ** メニューに移動します。

1. **スキーマを作成** をクリックします。

1. **[!UICONTROL スキーマタイプ]** として **リレーショナル** を選択します。

   ![](assets/admin_schema_1.png)

1. 「**[!UICONTROL DDL ファイルをアップロード]**」を選択し、エンティティ関係ダイアグラムを定義して、スキーマを作成します。

   テーブル構造には、次の項目を含める必要があります。
   * 1 つ以上のプライマリキー
   * バージョン識別子（`datetime` タイプまたは `number` タイプの「`lastmodified`」フィールドなど）。
   * Change Data Capture （CDC）の取り込みの場合、`_change_request_type` 型の `String` という特別な列。データ変更のタイプ（挿入、更新、削除など）を示し、増分処理を有効にします


   >[!IMPORTANT]
   >
   > ターゲティングに使用されるスキーマには、関連付けられた `String`ID 名前空間 **を持つ** タイプの ID フィールドが少なくとも 1 つ含まれている必要があります。\
   >これにより、Adobe Journey Optimizerのターゲティング機能および ID 解決機能との互換性が確保されます。

1. DDL ファイルをドラッグ＆ドロップし、「**[!UICONTROL 次へ]**」をクリックします。

   DDL ファイルでサポートされる最大サイズは 10 MB です。

1. **[!UICONTROL スキーマ名]**&#x200B;を入力します。

1. 各スキーマとその列を設定し、プライマリキーが指定されていることを確認します。

   `lastmodified` などの 1 つの属性をバージョン記述子として指定する必要があります。この属性は通常、`datetime`、`long` または `int` のタイプで、データセットが最新のデータバージョンで更新されるようにする取得プロセスに不可欠です。

   ![](assets/admin_schema_2.png)

1. 完了したら、「**[!UICONTROL 完了]**」をクリックします。

これで、キャンバス内でテーブルとフィールドの定義を確認できるようになりました。[詳しくは、以下の節を参照してください。](#entities)

## 関係の定義 {#relationships}

スキーマ内のテーブル間の論理接続を定義するには、次の手順に従います。

1. データモデルのキャンバス表示にアクセスし、リンクする 2 つのテーブルを選択します

1. ソース結合の横にある「![](assets/do-not-localize/Smock_AddCircle_18_N.svg)」ボタンをクリックし、矢印をドラッグしてターゲット結合の方向に誘導し、接続を確立します。

   ![](assets/admin_schema_5.png)

1. 指定されたフォームに入力してリンクを定義し、設定が完了したら「**適用**」をクリックします。

   ![](assets/admin_schema_3.png)

   **基数**：

   * **一対多**：ソーステーブルの 1 つのオカレンスは、ターゲットテーブルの複数のオカレンスに対応させることができますが、ターゲットテーブルの 1 つのオカレンスは、ソーステーブルの最大 1 つのオカレンスにのみ対応させることができます。

   * **多対一**：ターゲットテーブルの 1 つのオカレンスは、ソーステーブルの複数のオカレンスに対応させることができますが、ソーステーブルの 1 つのオカレンスは、ターゲットテーブルの最大 1 つのオカレンスにのみ対応させることができます。

   * **一対一**：ソーステーブルの 1 つのオカレンスは、最大でターゲットテーブルの 1 つのオカレンスに対応させることができます。

1. データモデルで定義されたすべてのリンクは、キャンバス表示では矢印として表されます。必要に応じて、詳細を表示したり、編集したり、リンクを削除したりするには、2 つのテーブル間の矢印をクリックします。

   ![](assets/admin_schema_6.png)

1. ツールバーを使用して、キャンバスをカスタマイズおよび調整します。

   ![](assets/toolbar.png)

   * **ズームイン**：データモデルの詳細がより明確に表示するには、キャンバスを拡大します。

   * **ズームアウト**：データモデルをより広く表示するには、キャンバスサイズを縮小します。

   * **表示に合わせる**：すべてのスキーマを表示領域内に合わせるには、ズームを調整します。

   * **フィルター**：キャンバス内に表示するスキーマを選択します。

   * **自動レイアウトを適用**：スキーマを自動的に整理して、より適切に整理します。

   * **マップを表示**：ミニマップオーバーレイを切り替えると、大規模スキーマレイアウトや複雑なスキーマレイアウトをより簡単に移動できます。

1. 完了したら、「**保存**」をクリックします。このアクションにより、スキーマと関連するデータセットが作成され、データセットを調整されたキャンペーンで使用できます。

1. 「**[!UICONTROL ジョブを開く]**」をクリックして、作成ジョブの進行状況を監視します。このプロセスは、DDL ファイルで定義されているテーブルの数に応じて、数分かかる場合があります。

   また、「**[!UICONTROL DDL ファイルのアップロード]**」ウィンドウを開き、「**[!UICONTROL すべてのリレーショナルジョブの表示]**」を選択して、リレーショナルジョブにアクセスすることもできます。

   ![](assets/admin_schema_4.png)

## リンクスキーマ {#link-schema}

>[!IMPORTANT]
>
> DDL ファイル内で明示的に定義された関係のみがシステムによって認識されます。 DDL ファイルの外部に存在するエンティティの関係は無視され、処理されません。

**ロイヤルティトランザクション**&#x200B;スキーマと&#x200B;**受信者**&#x200B;スキーマ間の関係を確立して、各トランザクションを正しい顧客レコードに関連付けます。

1. **[!UICONTROL スキーマ]**&#x200B;に移動し、以前に作成した&#x200B;**ロイヤルティトランザクション**&#x200B;を開きます。

1. 顧客の&#x200B;**[!UICONTROL フィールドプロパティ]**&#x200B;から「**[!UICONTROL 関係を追加]**」をクリックします。

   ![](assets/schema_1.png)

1. 「**[!UICONTROL 多対一]**」を関係&#x200B;**[!UICONTROL タイプ]**&#x200B;として選択します。

1. 既存の&#x200B;**受信者**&#x200B;スキーマにリンクします。

   ![](assets/schema_2.png)

1. **[!UICONTROL 現在のスキーマからの関係名]**&#x200B;と&#x200B;**[!UICONTROL 参照スキーマからの関係名]**&#x200B;を入力します。

1. 「**[!UICONTROL 適用]**」をクリックして変更を保存します。

続けて、**ロイヤルティ報酬**&#x200B;スキーマと&#x200B;**ブランドスキーマ**&#x200B;の関係を作成し、各報酬エントリを適切なブランドに関連付けます。

![](assets/schema_3.png)


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

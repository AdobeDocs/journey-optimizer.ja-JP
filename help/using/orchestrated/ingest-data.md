---
solution: Journey Optimizer
product: journey optimizer
title: 設定の手順
description: サポートされているソース（SFTP、クラウドストレージ、データベースなど）からAdobe Experience Platformにデータを取り込む方法を説明します。
exl-id: 7f1e7985-b68e-43d6-9c8f-fea2469f8af9
source-git-commit: c1201025af216f8f3019e7696b6eb906962b681b
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 22%

---


# データを取得 {#ingest-data}

>[!IMPORTANT]
>
>データセットのデータソースを変更するには、まず既存のデータフローを削除してから、同じデータセットと新しいソースを参照する新しいデータフローを作成する必要があります。
>
>Adobe Experience Platformでは、データフローとデータセットの間に厳密な 1 対 1 の関係を適用します。 これにより、ソースとデータセットの間の同期を維持して、正確な増分取り込みを行うことができます。

Adobe Experience Platform を使用すると、データを外部ソースから取得しながら、Experience Platform サービスを使用して、受信データの構造化、ラベル付け、拡張を行うことができます。アドビのアプリケーション、クラウドベースのストレージ、データベースなど、様々なソースからデータを取り込むことができます。

データセットは、スキーマ（列）とフィールド（行）で構成されるデータコレクション（通常はテーブル）を格納し管理するための構造です。Experience Platformに正常に取り込まれたデータは、データセットとしてデータレイク内に保存されます。

## 調整されたキャンペーンでサポートされるソース {#supported}

オーケストレートキャンペーンでの使用では、次のソースがサポートされます。

<table>
  <thead>
    <tr>
      <th>タイプ</th>
      <th>ソース</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="3">クラウドストレージ</td>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3">Amazon S3</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/google-cloud-storage">Google Cloud Storage</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/sftp">SFTP</a></td>
    </tr>
      <td rowspan="4">クラウドデータウェアハウス</td>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/databases/snowflake">Snowflake</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/databases/bigquery">Google BigQuery</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/data-landing-zone">Data Landing Zone<a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/databases/databricks">Azure Databricks</a></td>
    </tr>
    <tr>
      <td rowspan="3">ファイルベースのアップロード</td>
      <td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/local-system/local-file-upload">ローカルファイルのアップロード<a></td>
    </tr>

</tbody>
</table>

## リレーショナルスキーマデータハイジーンのガイドライン {#cdc}

**[!UICONTROL Change data capture]** が有効になっているデータセットの場合、削除を含むすべてのデータ変更が、ソースシステムからAdobe Experience Platformに自動的にミラーリングされます。

Adobe Journey Optimizer キャンペーンでは、すべてのオンボードされたデータセットで **[!UICONTROL Change data capture]** を有効にする必要があるので、ソースでの削除を管理するのは顧客の責任です。 ソースシステムから削除されたレコードは、Adobe Experience Platformの対応するデータセットから自動的に削除されます。

ファイルベースの取り込みを使用してレコードを削除するには、顧客のデータファイルで、`D` フィールドの `Change Request Type` 値を使用してレコードをマークする必要があります。 これは、ソースシステムをミラーリングして、Adobe Experience Platformでレコードを削除する必要があることを示します。

元のソースデータに影響を与えずに、Adobe Experience Platformからのみレコードを削除したい場合は、次のオプションを使用できます。

* **変更データ取得レプリケーションのプロキシまたはサニタイズされたテーブル**

  お客様は、プロキシまたはサニタイズされたソーステーブルを作成して、どのレコードをAdobe Experience Platformにレプリケートするかを制御できます。 その後、この中間テーブルから削除を選択的に管理できます。

* **データDistillerによる削除**

  ライセンスを取得している場合は、**Data Distiller** を使用して、ソースシステムに依存せずに、Adobe Experience Platform内で直接削除操作をサポートできます。

  [ 詳しくは、Data Distillerを参照してください ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/data-distiller/overview)

## データフローの設定

この例では、構造化データをAdobe Experience Platformに取り込むデータフローの設定方法を示します。 設定されたデータフローは、スケジュールに沿った自動インジェストをサポートし、リアルタイムの更新を可能にします。

1. **[!UICONTROL 接続]**&#x200B;メニューから、**[!UICONTROL ソース]**&#x200B;メニューにアクセスします。

1. [ オーケストレートキャンペーンでサポートされているソース ](#supported) に応じてソースを選択します。

   ![](assets/admin_sources_1.png)

1. クラウドベースのソースを選択した場合は、クラウドストレージまたはGoogle クラウドストレージアカウントを接続します。

   ![](assets/admin_sources_2.png)

1. Adobe Experience Platformに取り込むデータを選択します。

   ![](assets/S3_config_1.png)

1. **[!UICONTROL データセットの詳細]** ページで、「**[!UICONTROL 変更データキャプチャを有効にする]**」をチェックして、リレーショナルスキーマにマッピングされ、プライマリキーとバージョン記述子の両方が含まれるデータセットのみを表示します。

[リレーショナルスキーマのデータハイジーンに関するガイドラインについて詳しく説明します](#cdc)

   >[!IMPORTANT]
   >
   > **ファイルベースのソースのみ** の場合、データファイルの各行には、`_change_request_type` （upsert）または `U` （delete）の値を持つ `D` 列を含める必要があります。 この列がないと、システムはデータをサポートする変更トラッキングとして認識せず、オーケストレーションされたキャンペーンの切り替えは表示されず、データセットがターゲティング用に選択されません。

   ![](assets/S3_config_6.png)

1. 以前に作成したデータセットを選択し、「**[!UICONTROL 次へ]**」をクリックします。

   ![](assets/S3_config_3.png)

1. ファイルベースのソースのみを使用している場合は、**[!UICONTROL データを選択]** ウィンドウからローカルファイルをアップロードし、構造と内容をプレビューします。

   サポートされる最大サイズは 100 MB です。

1. **[!UICONTROL マッピング]** ウィンドウで、各ソースファイル属性がターゲットスキーマの対応するフィールドに正しくマッピングされていることを確認します。 [ターゲティングディメンションの詳細情報を参照してください](target-dimension.md)。

   完了したら、「**[!UICONTROL 次へ]**」をクリックします。

   ![](assets/S3_config_4.png)

1. 目的の頻度に基づいてデータフローの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定します。

1. 「**[!UICONTROL 終了]**」をクリックしてデータフローを作成します。定義したスケジュールに従って自動的に実行されます。

1. **[!UICONTROL 接続]**&#x200B;メニューから「**[!UICONTROL ソース]**」を選択し、「**[!UICONTROL データフロー]**」タブにアクセスして、フローの実行を追跡し、取得されたレコードを確認し、エラーをトラブルシューティングします。

   ![](assets/S3_config_5.png)



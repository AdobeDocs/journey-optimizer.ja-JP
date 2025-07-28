---
solution: Journey Optimizer
product: journey optimizer
title: 設定の手順
description: ユーザーインターフェイスを介して直接リレーショナルスキーマを作成する方法を説明します。
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 8c785431-9a00-46b8-ba54-54a10e288141
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 10%

---

# 手動のリレーショナルスキーマの設定 {#manual-schema}

+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br><ul><li>[ スキーマとデータセットの概要 ](gs-schemas.md)</li><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul>[ オーケストレートキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレートキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [キャンペーンの作成とスケジュール](create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](start-monitor-campaigns.md)<br/><br/>[レポート](reporting-campaigns.md) | [ルールビルダーの操作](orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](build-query.md)<br/><br/>[式の編集](edit-expressions.md)<br/><br/>[リターゲティング](retarget.md) | [アクティビティの基本を学ぶ](activities/about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](activities/and-join.md) - [オーディエンスを作成](activities/build-audience.md) - [ディメンションを変更](activities/change-dimension.md) - [チャネルアクティビティ](activities/channels.md) - [結合](activities/combine.md) - [重複排除](activities/deduplication.md) - [エンリッチメント](activities/enrichment.md) - [分岐](activities/fork.md) - [紐付け](activities/reconciliation.md) - [オーディエンスを保存](activities/save-audience.md) - [分割](activities/split.md) - [待機](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

リレーショナルスキーマは、ユーザーインターフェイスを通じて直接作成でき、属性、プライマリキー、バージョンフィールド、関係の詳細な設定を可能にします。

次の例では、**ロイヤルティメンバーシップ** スキーマを手動で定義して、オーケストレートキャンペーンに必要な構造を示します。

1. Adobe Experience Platform インターフェイスを使用して [ リレーショナルスキーマを手動で作成 ](#schema) ます。

1. [ 属性を追加 ](#schema-attributes) ます（顧客 ID、メンバーシップレベル、ステータスフィールドなど）。

1. キャンペーンターゲティング用の受信者などのビルトインスキーマへの [ スキーマのリンク ](#link-schema)。

1. スキーマに基づいて [ データセットを作成 ](#dataset) し、オーケストレートキャンペーンで使用できるようにします。

1. サポートされているソースからデータセットへの [ データの取り込み ](ingest-data.md)。

## スキーマの作成 {#schema}

まず、Adobe Experience Platformで新しいリレーショナルスキーマを手動で作成します。 このプロセスを使用すると、名前や動作などのスキーマ構造を最初から定義できます。

1. Adobe Experience Platformにログインします。

1. **[!UICONTROL データ管理]**/**[!UICONTROL スキーマ]** メニューに移動します。

1. **[!UICONTROL スキーマを作成]** をクリックします。

1. **[!UICONTROL スキーマタイプ]** として **リレーショナル** を選択します。

   ![](assets/admin_schema_1.png){zoomable="yes"}

1. フィールドを手動で追加してスキーマを構築する場合は、「**[!UICONTROL 手動で作成]**」を選択します。

1. **[!UICONTROL スキーマ表示名]** を入力します。

1. **[!UICONTROL スキーマ動作]** として **[!UICONTROL レコード]** を選択します。

   ![](assets/schema_manual_8.png){zoomable="yes"}

1. 「**終了**」をクリックして、スキーマの作成に進みます。

これで、スキーマに属性を追加して、構造を定義できるようになりました。

## スキーマへの属性の追加 {#schema-attributes}

次に、属性を追加してスキーマの構造を定義します。 これらのフィールドは、顧客識別子、メンバーシップの詳細、アクティビティの日付など、オーケストレートキャンペーンで使用される主要なデータポイントを表します。 これらを正確に定義すると、信頼性の高いパーソナライゼーション、セグメント化およびトラッキングが保証されます。

ターゲティングに使用されるスキーマには、関連する ID 名前空間を持つ `String` タイプの ID フィールドが少なくとも 1 つ含まれている必要があります。 これにより、Adobe Journey Optimizerのターゲティング機能および ID 解決機能との互換性が確保されます。

+++Adobe Experience Platformでリレーショナルスキーマを作成する場合、次の機能がサポートされます

* **列挙**\
  ENUM フィールドは、DDL ベースのスキーマ作成と手動のスキーマ作成の両方でサポートされており、許可された値の固定セットを使用して属性を定義できます。

* **データガバナンスのスキーマラベル**\
  ラベル設定は、アクセス制御や使用制限などのデータガバナンスポリシーを適用するためにスキーマフィールドレベルでサポートされています。 詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。

* **複合キー**\
  複合プライマリキーはリレーショナルスキーマ定義でサポートされるので、複数のフィールドを一緒に使用してレコードを一意に識別できます。

+++

1. キャンバスで ![](assets/do-not-localize/Smock_AddCircle_18_N.svg) スキーマ名 **の横にある** をクリックして、属性の追加を開始します。

   ![](assets/schema_manual_1.png){zoomable="yes"}

1. 属性 **[!UICONTROL フィールド名]**、**[!UICONTROL 表示名]**、**[!UICONTROL タイプ]** を入力します。

   この例では、以下の表で詳しく説明している属性を **ロイヤルティメンバーシップ** スキーマに追加しました。

+++ 属性の例

   | 属性名 | データタイプ | 追加の属性 |
   |-|-|-|
   | 顧客 | STRING | プライマリキー |
   | membership_level | STRING | 必須 |
   | points_balance | 整数 | 必須 |
   | enrollment_date | 日付 | 必須 |
   | last_status_change | 日付 | 必須 |
   | expiration_date | 日付 | - |
   | is_active | BOOLEAN | 必須 |
   | lastmodified | 日時 | 必須 |

+++

1. 適切なフィールドを **[!UICONTROL プライマリキー]** および **[!UICONTROL バージョン記述子]** として割り当てます。

   手動スキーマを作成する場合は、次の必須フィールドが含まれていることを確認します。

   * 1 つ以上のプライマリキー
   * バージョン識別子（`datetime` タイプまたは `number` タイプの「`lastmodified`」フィールドなど）。
   * チェンジ・データ・キャプチャ（CDC）の取り込みの場合、`_change_request_type` タイプの `String` という特別な列。データ変更のタイプ（挿入、更新、削除など）を示し、増分処理を使用可能にします。

   ![](assets/schema_manual_2.png){zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

属性を作成したら、新しく作成したスキーマをビルトインスキーマにリンクする必要があります。

## リンクスキーマ {#link-schema}

2 つのスキーマ間に関係を作成すると、プライマリプロファイルスキーマの外部に保存されたデータでオーケストレートキャンペーンを強化できます。

1. 新しく作成したスキーマから、リンクとして使用する属性を選択し、「**[!UICONTROL 関係を追加]**」をクリックします。

   ![](assets/schema_manual_3.png){zoomable="yes"}

1. **[!UICONTROL 参照スキーマ]** と **[!UICONTROL 参照フィールド]** を選択して、との関係を確立します。

   この例では、`customer` 属性が `recipients` スキーマにリンクされています。

   ![](assets/schema_manual_4.png){zoomable="yes"}

1. 現在のスキーマと参照スキーマの関係名を入力します。

1. 設定が完了したら、「**[!UICONTROL 適用]**」をクリックします。

関係が確立されたら、スキーマに基づいてデータセットを作成する必要があります。

## スキーマのデータセットの作成 {#dataset}

スキーマを定義したら、次の手順はそれに基づいてデータセットを作成します。 このデータセットには、取り込んだデータが格納されており、Adobe Journey Optimizerでアクセスできるようにするには、オーケストレートキャンペーンを有効にする必要があります。 このオプションを有効にすると、データセットが認識され、リアルタイムオーケストレーションおよびパーソナライゼーションワークフローで使用できるようになります。

1. **[!UICONTROL データ管理]**/**[!UICONTROL データセット]** メニューに移動し、「**[!UICONTROL データセットを作成]**」をクリックします。

   ![](assets/schema_manual_5.png){zoomable="yes"}

1. 「**[!UICONTROL スキーマからデータセットを作成]**」をクリックします。

1. 以前に作成したスキーマを選択し、ここで **ロイヤルティメンバーシップ** を選択して、「次へ **[!UICONTROL をクリックし]** す。

   ![](assets/schema_manual_6.png){zoomable="yes"}

1. **[!UICONTROL データセット]** の **[!UICONTROL 名前]** を入力し、「**[!UICONTROL 終了]**」をクリックします。

次に、オーケストレートキャンペーン用のデータセットを有効にする必要があります。

## オーケストレートキャンペーン用データセットの有効化 {#enable}

データセットを作成したら、オーケストレートキャンペーン用に明示的に有効にする必要があります。 この手順では、データセットがAdobe Journey Optimizer内でリアルタイムのオーケストレーションとパーソナライゼーションに使用できるようにします。

1. **[!UICONTROL データセット]** リストでデータセットを見つけます。

1. 「**[!UICONTROL データセット]**」設定から、「**オーケストレートキャンペーン**」オプションを有効にして、オーケストレートキャンペーンでデータセットを使用できるようにします。

   ![](assets/schema_manual_7.png){zoomable="yes"}

1. イネーブルメントプロセスが完了するまで数分待ちます。 データの取り込みとキャンペーンの使用は、この設定が完全にアクティブ化された後にのみ可能であることに注意してください。

これで、選択したソースを使用してスキーマへのデータの取り込みを開始できます。

➡️[ データの取り込み方法を学ぶ ](ingest-data.md)

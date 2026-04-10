---
title: 移行APIの決定
description: Decisioning Migration Service APIを使用して、自動依存関係の解決とロールバックのサポートを使用してサンドボックス間で意思決定管理オブジェクトを移行する方法を説明します。
feature: Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 3ec084ca-af9e-4b5e-b66f-ec390328a9d6
source-git-commit: d7d9c371f4b0d8b4ea51e1f23eb9a2f665711fce
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 5%

---

# 移行APIの決定 {#decisioning-migration-api}

Decisioning Migration Service APIを使用すると、あるサンドボックスから別のサンドボックスに意思決定管理オブジェクトを移行できます。 移行プロセスは、依存関係の分析、実行、オプションのロールバック機能を含む非同期ワークフローとして実行されます。

このAPIを使用すると、データの整合性と関係を維持しながら、環境<!--(e.g., from development to staging, or staging to production) -->間で意思決定コンテンツをシームレスに移行できます。

意思決定管理と比較した意思決定の利点と機能については、[このページ ](migrate-to-decisioning.md)を参照してください。

## 機能 {#capabilities}

Decisioning Migration Service APIには、次の機能が用意されています。

* **依存関係分析** – 属性、セグメント、データセット要件など、ソース サンドボックスとターゲット サンドボックス間に必要なすべての依存関係を特定します。
* **柔軟な移行スコープ** – 必要に応じて、サンドボックス、オファー、決定レベルで移行を実行します。
* **ロールバック サポート** – 検証中に問題が検出された場合、完了した移行を元に戻します。

## 前提条件 {#prerequisites}

### 必要な権限 {#permissions}

移行APIを使用するには、ソースサンドボックスとターゲットサンドボックスの両方に適切な権限が必要です。

**Source サンドボックス** – 意思決定管理オブジェクトへの読み取りアクセス

**Target サンドボックス** - Decisioning オブジェクトへのアクセス権の作成と編集

一般的な権限には、次のものがあります。

* 決定の管理/表示
* 決定の管理/表示
* オファーの管理
* ランキング戦略の管理
* キャンペーンの管理（キャンペーン関連のアーティファクトを移行する場合）
* データストリームの管理/表示（データストリームを作成する場合）
* スキーマの管理/表示

>[!NOTE]
>
>[このセクション ](gs-experience-decisioning.md#steps)で決定権限を割り当てる方法について説明します。 権限の完全なリストについては、[組み込みの権限](../administration/ootb-permissions.md#ootb-permissions) ページを参照してください。

### ターゲットサンドボックスの準備 {#target-sandbox-preparation}

移行を実行する前に、ターゲットサンドボックスが適切に設定されていることを確認します。

* **属性** – 必要なプロファイル属性とコンテキスト属性がターゲットサンドボックスに存在することを確認するか、マッピングを準備します。
* **セグメント** – 必要なセグメントがターゲットサンドボックスに存在することを確認するか、名前空間とIDを使用してセグメントをマッピングすることを計画します。
* **データセット** – 移行に使用するデータセット名を特定します（`dependency.datasetName`）。
* **データストリーム** – 移行でデータストリーム （`createDataStream`）を作成するかどうかを決定します。

サンドボックス管理について詳しくは、[ サンドボックスの使用と割り当て](../administration/sandboxes.md)を参照してください。

## API の基本 {#api-basics}

### ベース URL {#base-url}

次のベース URLを使用します。

* **本番**: `https://decisioning-migration.adobe.io`
  <!--* **Staging**: `https://decisioning-migration-stage.adobe.io`-->

### 認証 {#authentication}

すべてのAPI リクエストには、次のヘッダーが必要です。

* `Authorization: Bearer <IMS_ACCESS_TOKEN>`
* `x-gw-ims-org-id: <IMS_ORG_ID>`
* `Content-Type: application/json`

認証の設定手順について詳しくは、[Journey Optimizer認証ガイド ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}を参照してください。

### ワークフローモデル {#workflow-model}

各API呼び出しは、ワークフローリソースを作成または取得します。 ワークフローは、移行タスクの進行状況と結果を追跡する非同期操作です。

ワークフローには次のプロパティがあります。

* `id` – 一意のワークフロー識別子（UUID）
* `status` – 現在のワークフロー状態：`New`、`Running`、`Completed`または`Failed`
* `result` – 完了時のワークフロー出力（移行結果と警告を含む）
* `errors` – 失敗したときに構造化エラーの詳細
* `_links.self` - ステータスを取得するためのワークフローURL
  <!--* `_etag` - Version identifier used for delete operations (service users only)-->

## 移行ワークフロー {#migration-workflow}

移行プロセスは、依存関係の分析と移行の実行という2つの主な手順で構成されます。 移行を成功させるには、次の手順に従います。

### 手順1：依存関係の分析 {#analyze-dependencies}

移行前に、依存関係ワークフローを使用して、ターゲット サンドボックスの意思決定管理から決定にマッピングする必要がある項目を特定します。 この分析は、オブジェクト間の関係を理解し、必要なマッピングを準備するのに役立ちます。

#### 依存関係ワークフローの作成 {#create-dependency-workflow}

次のAPI呼び出しを使用して、依存関係分析ワークフローを作成します。

**API 形式**

```http
POST /workflows/generate-dependencies
```

**サンドボックスレベルの依存関係（最初に推奨）**

サンドボックスレベルの分析から始めて、あらゆる依存関係を包括的に把握します。

```shell
curl --request POST \
  --url "https://decisioning-migration.adobe.io/workflows/generate-dependencies" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "Content-Type: application/json" \
  --data '{
    "imsOrgId": "<IMS_ORG_ID>",
    "sourceSandboxDetails": { "sandboxName": "<SOURCE_SANDBOX_NAME>" },
    "targetSandboxDetails": { "sandboxName": "<TARGET_SANDBOX_NAME>" },
    "requestLevel": "sandbox"
  }'
```

**オファーレベルの依存関係**

特定のオファーの依存関係のみを分析するには、`requestLevel: "offer"`を設定し、分析するオファーIDを`offersList`配列に指定します。

**決定レベルの依存関係**

特定の決定の依存関係のみを分析するには、`requestLevel: "decision"`を設定し、分析する決定IDを`decisionsList`配列に指定します。

#### 依存関係ワークフローの状態を確認する {#poll-dependency-status}

依存関係ワークフローをポーリングして、分析が完了したときに確認します。

**API 形式**

```http
GET /workflows/generate-dependencies/{id}
```

**リクエスト**

```shell
curl --request GET \
  --url "https://decisioning-migration.adobe.io/workflows/generate-dependencies/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>"
```

`status` フィールドに`Completed`が表示されると、依存関係の分析の準備が整います。 ワークフロー出力を使用して、移行依存関係マッピングを構築します。

* **profileAttributes** - ソースプロファイル属性をターゲットプロファイル属性にマッピングします
* **contextAttributes** - ソースコンテキスト属性をターゲットコンテキスト属性にマッピングします
* **セグメント** - ソース セグメント キーをターゲット セグメント ID （`{namespace, id}`）にマッピングします
* **datasetName** – 移行のターゲットデータセット名を指定します

### 手順2：移行の実行 {#execute-migration}

依存関係を分析し、マッピングを準備したら、移行を実行できます。

#### 移行ワークフローの作成 {#create-migration-workflow}

手順1の依存関係マッピングを使用して、移行を設定および実行します。

**API 形式**

```http
POST /workflows/migration
```

**サンドボックスレベルの移行**

すべての決定オブジェクトを1つのサンドボックスから別のサンドボックスに移行するには：

```shell
curl --request POST \
  --url "https://decisioning-migration.adobe.io/workflows/migration" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "Content-Type: application/json" \
  --data '{
    "imsOrgId": "<IMS_ORG_ID>",
    "sourceSandboxDetails": { "sandboxName": "<SOURCE_SANDBOX_NAME>" },
    "targetSandboxDetails": { "sandboxName": "<TARGET_SANDBOX_NAME>" },
    "createDataStream": true,
    "dependency": {
      "profileAttributes": {
        "sourceAttr1": "targetAttr1"
      },
      "segments": {
        "sourceSegmentKey1": {
          "namespace": "<TARGET_SEGMENT_NAMESPACE>",
          "id": "<TARGET_SEGMENT_ID>"
        }
      },
      "contextAttributes": {
        "sourceCtx1": "targetCtx1"
      },
      "datasetName": "<TARGET_DATASET_NAME>"
    },
    "requestLevel": "sandbox"
  }'
```

**オファーレベルの移行**

特定のオファーのみを移行するには、`requestLevel: "offer"`を使用して`offersList`配列を追加します。

```json
"offersList": ["offer-id-1", "offer-id-2"]
```

**決定レベルの移行**

特定の決定のみを移行するには、`requestLevel: "decision"`を使用して`decisionsList`配列を追加します。

```json
"decisionsList": ["decision-id-1", "decision-id-2"]
```

#### 移行ステータスの監視 {#poll-migration-status}

移行ワークフローをポーリングして、進行状況を追跡します。

**API 形式**

```http
GET /workflows/migration/{id}
```

**リクエスト**

```shell
curl --request GET \
  --url "https://decisioning-migration.adobe.io/workflows/migration/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>"
```

**移行結果**

`status` フィールドに`Completed`が表示されている場合、移行は成功しました。 ワークフロー`result`には次のものが含まれます。
* 移行されたオブジェクトのマッピング
* 移行中に発生した警告

`status` フィールドに`Failed`が表示されたら、`errors[]`配列と`result.error` フィールドで、問題の詳細を確認します。

## 移行の検証 {#validate-migration}

移行が正常に完了したら、すべてのオブジェクトが正しく移行されたことを確認します。

### 検証チェックリスト {#validation-checklist}

1. **セグメント** – 参照されているすべてのセグメントが、マッピングに従ってターゲットサンドボックスで正しく解決されていることを確認します。
2. **属性** – すべてのプロファイル属性とコンテキスト属性がターゲットサンドボックスに存在し、正しくマッピングされていることを確認します。
3. **オブジェクトの決定** - Journey Optimizer ユーザーインターフェイスで移行されたオブジェクトを確認します。
   * オファー（決定項目）
   * 実施要件ルール
   * ランキング式
   * 選択戦略
   * 決定ポリシー
4. **データストリームテスト** - データストリームが作成された場合は、Edge Interact APIを使用してランタイム配信をテストします。

### 例 {#test-runtime-delivery}

移行でデータストリームを作成した場合は、次の例を使用してオファー配信をテストできます。

```shell
curl --request POST \
  --url "https://edge.adobedc.net/ee/or2/v1/interact?configId=<DATASTREAM_ID>" \
  --header "Content-Type: application/json" \
  --header "x-request-id: <uuid>" \
  --data '{ "events": [ ... ] }'
```

## 移行のロールバック {#rollback}

検証中に問題が発生した場合は、完了した移行をロールバックして、ターゲットサンドボックスを以前の状態に戻すことができます。

### ロールバックワークフローの作成 {#create-rollback-workflow}

元に戻す移行を参照するロールバックワークフローを作成して、ロールバックを開始します。

**API 形式**

```http
POST /workflows/rollback
```

**リクエスト**

```shell
curl --request POST \
  --url "https://decisioning-migration.adobe.io/workflows/rollback" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "Content-Type: application/json" \
  --data '{ "rollbackWorkflowId": "<MIGRATION_WORKFLOW_ID>" }'
```

`<MIGRATION_WORKFLOW_ID>`を、ロールバックする移行ワークフローのIDに置き換えます。

### ロールバックステータスの監視 {#poll-rollback-status}

ロールバックワークフローをポーリングして、進行状況を追跡します。

**API 形式**

```http
GET /workflows/rollback/{rollbackWorkflowId}
```

**リクエスト**

```shell
curl --request GET \
  --url "https://decisioning-migration.adobe.io/workflows/rollback/<ROLLBACK_WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>"
```

## 同時ワークフローへの対応 {#handle-concurrency}

移行APIでは、組織ごとに一度に1つのワークフローのみを実行できます。 別のワークフローが進行中の間に新しいワークフローを作成しようとすると、**409 Conflict** エラー応答（「ワークフローは既に進行中です…」）が表示されます。

この場合、処理中のワークフローが完了するのを待つか、ワークフローIDを取得してステータスをポーリングします。 現在のワークフローが完了したら、新しいワークフローを作成できます。

## エンティティマッピング参照 {#entity-mapping}

意思決定管理から決定に移行する場合、エンティティは次のようにマッピングされます。

| 意思決定管理 | 決定 |
|-------------------|-------------|
| オファー | 決定項目 |
| オファーコレクション | アイテムコレクション |
| 実施要件ルール | 実施要件ルール |
| ランキング式 | ランキング式 |
| 決定 | 選択戦略+決定ポリシー |
| Campaign | キャンペーン *（基本コンテンツのみ）* |
| プレースメント | サーフェス + チャネル設定 |
| タグ | 統合タグ |
| オファー属性 | パーソナライズされたオファー項目スキーマの`migratedofferattributes` フィールド |
| コンテキスト属性 | 移行中に提供されたデータセットに添付されたスキーマの`migratedcontextattributes` フィールド |

## ワークフローのクリーンアップ {#cleanup}

<!--
Workflow resources can be deleted by service users only. Delete operations require an `If-Match` header with the workflow's `_etag` value.

**Available delete operations:**

* `DELETE /workflows/generate-dependencies/{id}`
* `DELETE /workflows/migration/{id}`
* `DELETE /workflows/rollback/{id}`
-->

ワークフローの削除は公開されていません。 ワークフローリソースを削除する必要がある場合は、システム管理者にお問い合わせください。

## 関連トピック {#related-topics}

* [意思決定管理から決定](migrate-to-decisioning.md)への移行 – Decisioningへの移行のメリットと機能について説明します
* [決定の基本を学ぶ](gs-experience-decisioning.md)
* [決定のガードレールと制限](decisioning-guardrails.md)
* [Decisioning API の基本を学ぶ](api-reference/getting-started.md)

---
title: Decisioning Migration API
description: Decisioning Migration Service API を使用して、自動依存関係解決とロールバックサポートによりサンドボックス間で意思決定管理オブジェクトを移行する方法を説明します。
feature: Decisioning
topic: Integrations
role: Developer
level: Experienced
source-git-commit: 398d4c2ab3a2312a0af5b8ac835f7d1f49a61b5b
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 5%

---


# Decisioning Migration API {#decisioning-migration-api}

Decisioning Migration Service API を使用すると、意思決定管理オブジェクトをサンドボックス間で移行できます。 移行プロセスは、依存関係の分析、実行、オプションのロールバック機能を含む非同期ワークフローとして実行されます。

この API を使用すると、データの整合性と関係を維持しながら、環境間（開発からステージング、ステージングから実稼動へ）で意思決定コンテンツをシームレスに移行できます。

意思決定管理と比較した意思決定のメリットと機能については、[ このページ ](migrate-to-decisioning.md) を参照してください。

## 機能 {#capabilities}

Decisioning 移行サービス API は、次の機能を提供します。

* **依存関係分析** – 属性、セグメント、データセット要件など、ソースサンドボックスとターゲットサンドボックスの間に必要なすべての依存関係を特定します。
* **柔軟な移行範囲** - ニーズに基づいて、サンドボックス、オファーまたは決定レベルで移行を実行します。
* **ロールバックサポート** – 検証中に問題が見つかった場合に、完了した移行を元に戻します。

## 前提条件 {#prerequisites}

### 必要な権限 {#permissions}

移行 API を使用するには、ソースサンドボックスとターゲットサンドボックスの両方で適切な権限が必要です。

**Source sandbox** – 意思決定管理オブジェクトへの読み取りアクセス

**ターゲットサンドボックス** – 決定オブジェクトへのアクセスを作成および編集します

一般的な権限を次に示します。

* 決定の管理/表示
* 決定の管理/表示
* オファーの管理
* ランキング戦略の管理
* キャンペーンの管理（キャンペーン関連アーティファクトを移行する場合）
* データストリームの管理/表示（データストリームを作成する場合）
* スキーマの管理/表示

>[!NOTE]
>
>意思決定権限の割り当て方法については、[ この節 ](gs-experience-decisioning.md#steps) を参照してください。 権限の完全なリストについては、[ 組み込みの権限 ](../administration/ootb-permissions.md#ootb-permissions) ページを参照してください。

### ターゲットサンドボックスの準備 {#target-sandbox-preparation}

移行を実行する前に、ターゲットサンドボックスが適切に設定されていることを確認します。

* **属性** – 必要なプロファイル属性とコンテキスト属性がターゲットサンドボックスに存在することを確認するか、マッピングを準備します。
* **セグメント** - ターゲットサンドボックスに必要なセグメントが存在することを確認するか、名前空間と ID を使用してセグメントをマッピングすることを計画します。
* **データセット** – 移行に使用するデータセット名を特定します（`dependency.datasetName`）。
* **データストリーム** – 移行でデータストリームを作成するかどうかを決定します（`createDataStream`）。

サンドボックス管理について詳しくは、[ サンドボックスの使用と割り当て ](../administration/sandboxes.md) を参照してください。

## API の基本 {#api-basics}

### ベース URL {#base-urls}

環境に応じて次のベース URL を使用します。

* **実稼動**: `https://platform.adobe.io`
* **ステージング**: `https://platform-stage.adobe.io`

### 認証 {#authentication}

すべての API リクエストには次のヘッダーが必要です。

* `Authorization: Bearer <IMS_ACCESS_TOKEN>`
* `x-gw-ims-org-id: <IMS_ORG_ID>`
* `x-api-key: <CLIENT_API_KEY>`
* `Content-Type: application/json`

認証の設定について詳しくは、[Journey Optimizer認証ガイド ](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} を参照してください。

### ワークフローモデル {#workflow-model}

各 API 呼び出しによって、ワークフローリソースが作成または取得されます。 ワークフローは、移行タスクの進捗と結果を追跡する非同期操作です。

ワークフローには次のプロパティがあります。

* `id` - ワークフローの一意の識別子（UUID）
* `status` – 現在のワークフローステータス：`New`、`Running`、`Completed`、`Failed` または `Cancelled`
* `result` – 完了時のワークフロー出力（移行結果および警告を含む）
* `errors` – 失敗したときの構造化エラーの詳細
* `_etag` – 削除操作に使用されるバージョン識別子（サービスユーザーのみ）
* `_links.self` - ステータスを取得するためのワークフロー URL

## 移行ワークフロー {#migration-workflow}

移行プロセスは、依存関係の分析と移行の実行という 2 つの主な手順で構成されます。 移行を正常に完了させるには、次の手順に従います。

### 手順 1：依存関係の分析 {#analyze-dependencies}

移行する前に、依存関係ワークフローを使用して、ターゲットサンドボックスで意思決定管理から決定へのマッピングが必要なものを特定します。 この分析は、オブジェクト間の関係を理解し、必要なマッピングを準備するのに役立ちます。

#### 依存関係ワークフローの作成 {#create-dependency-workflow}

次の API 呼び出しを使用して、依存関係分析ワークフローを作成します。

**API 形式**

```http
POST /migration/service/dependency
```

**サンドボックスレベルの依存関係（最初に推奨）**

サンドボックスレベルの分析から始めて、すべての依存関係を完全に把握します。

```shell
curl --request POST \
  --url "https://platform.adobe.io/migration/service/dependency" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>" \
  --header "Content-Type: application/json" \
  --data '{
    "imsOrgId": "<IMS_ORG_ID>",
    "sourceSandboxDetails": { "sandboxName": "<SOURCE_SANDBOX_NAME>" },
    "targetSandboxDetails": { "sandboxName": "<TARGET_SANDBOX_NAME>" },
    "requestLevel": "sandbox"
  }'
```

**オファーレベルの依存関係**

特定のオファーのみの依存関係を分析するには、`requestLevel: "offer"` を設定し、分析するオファー ID を含む `offersList` 配列を指定します。

**決定レベルの依存関係**

特定の決定のみの依存関係を分析するには、`requestLevel: "decision"` を設定し、分析する決定 ID を含む `decisionsList` 配列を指定します。

#### 依存関係ワークフローステータスの確認 {#poll-dependency-status}

依存関係ワークフローをポーリングして、分析が完了したことを確認します。

**API 形式**

```http
GET /migration/service/dependency/{id}
```

**リクエスト**

```shell
curl --request GET \
  --url "https://platform.adobe.io/migration/service/dependency/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
```

`status` フィールドに「`Completed`」と表示されたら、依存関係分析の準備が整います。 ワークフロー出力を使用して、移行依存関係マッピングを作成します。

* **profileAttributeDependency** - ソースプロファイル属性をターゲットプロファイル属性にマップする
* **contextAttributeDependency** - ソースコンテキスト属性をターゲットコンテキスト属性にマップする
* **segmentsDependency** - ソースセグメントキーをターゲットセグメント識別子にマッピングします（`{segmentNamespace, segmentId}`）
* **datasetName** – 移行のターゲットデータセット名を指定します

### 手順 2：移行を実行する {#execute-migration}

依存関係を分析し、マッピングを準備したら、移行を実行できます。

#### 移行ワークフローの作成 {#create-migration-workflow}

手順 1 の依存関係マッピングを使用して、移行を設定および実行します。

**API 形式**

```http
POST /migration/service/migrations
```

**サンドボックスレベルの移行**

すべての決定オブジェクトをサンドボックス間で移行するには：

```shell
curl --request POST \
  --url "https://platform.adobe.io/migration/service/migrations" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>" \
  --header "Content-Type: application/json" \
  --data '{
    "imsOrgId": "<IMS_ORG_ID>",
    "sourceSandboxDetails": { "sandboxName": "<SOURCE_SANDBOX_NAME>" },
    "targetSandboxDetails": { "sandboxName": "<TARGET_SANDBOX_NAME>" },
    "createDataStream": true,
    "dependency": {
      "profileAttributeDependency": {
        "sourceAttr1": "targetAttr1"
      },
      "segmentsDependency": {
        "sourceSegmentKey1": {
          "segmentNamespace": "<TARGET_SEGMENT_NAMESPACE>",
          "segmentId": "<TARGET_SEGMENT_ID>"
        }
      },
      "contextAttributeDependency": {
        "sourceCtx1": "targetCtx1"
      },
      "datasetName": "<TARGET_DATASET_NAME>"
    },
    "requestLevel": "sandbox"
  }'
```

**オファーレベルの移行**

特定のオファーのみを移行するには、`requestLevel: "offer"` を使用して `offersList` 配列を追加します。

```json
"offersList": ["offer-id-1", "offer-id-2"]
```

**決定レベルの移行**

特定の決定のみを移行するには、`requestLevel: "decision"` を使用して、`decisionsList` の配列を追加します。

```json
"decisionsList": ["decision-id-1", "decision-id-2"]
```

#### 移行ステータスの監視 {#poll-migration-status}

移行ワークフローをポーリングして、進行状況を追跡します。

**API 形式**

```http
GET /migration/service/migrations/{id}
```

**リクエスト**

```shell
curl --request GET \
  --url "https://platform.adobe.io/migration/service/migrations/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
```

**移行の結果**

`status` フィールドに「`Completed`」と表示されたら、移行は成功でした。 ワークフロー `result` には、次のものが含まれます。
* 移行されたオブジェクトのマッピング
* 移行中に発生した警告

`status` フィールドに `Failed` と表示されたら、`errors[]` の配列と `result.error` フィールドで、何が問題だったのかの詳細を確認します。

## 移行の検証 {#validate-migration}

移行が正常に完了したら、すべてのオブジェクトが正しく移行されたことを確認します。

### 検証チェックリスト {#validation-checklist}

1. **セグメント** – 参照されるすべてのセグメントが、マッピングに従ってターゲットサンドボックスで正しく解決されることを確認します。
2. **属性** – すべてのプロファイル属性とコンテキスト属性がターゲットサンドボックスに存在し、正しくマッピングされていることを確認します。
3. **オブジェクトの決定** – 移行されたオブジェクトをJourney Optimizer ユーザーインターフェイスで確認します。
   * オファー（決定項目）
   * 実施要件ルール
   * ランキング式
   * 選択戦略
   * 決定ポリシー
4. **データストリームテスト** - データストリームが作成された場合は、Edge Interact API を使用してランタイム配信をテストします。

### 例 {#test-runtime-delivery}

移行でデータストリームが作成された場合は、次の例を使用してオファー配信をテストできます。

```shell
curl --request POST \
  --url "https://edge.adobedc.net/ee/or2/v1/interact?configId=<DATASTREAM_ID>" \
  --header "Content-Type: application/json" \
  --header "x-request-id: <uuid>" \
  --data '{ "events": [ ... ] }'
```

## 移行をロールバックする {#rollback}

検証中に問題が見つかった場合は、完了した移行をロールバックして、ターゲットサンドボックスを以前の状態に復元できます。

### ロールバックワークフローの作成 {#create-rollback-workflow}

元に戻す移行を参照するロールバックワークフローを作成して、ロールバックを開始します。

**API 形式**

```http
POST /migration/service/rollbacks/{migrationWorkflowId}
```

`{migrationWorkflowId}` を、ロールバックする移行ワークフローの ID に置き換えます。

**リクエスト**

```shell
curl --request POST \
  --url "https://platform.adobe.io/migration/service/rollbacks/<MIGRATION_WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
```

### ロールバックステータスの監視 {#poll-rollback-status}

ロールバックワークフローをポーリングして、進行状況を追跡します。

**API 形式**

```http
GET /migration/service/rollbacks/{rollbackWorkflowId}
```

**リクエスト**

```shell
curl --request GET \
  --url "https://platform.adobe.io/migration/service/rollbacks/<ROLLBACK_WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
```

## 同時ワークフローの処理 {#handle-concurrency}

移行 API では、組織ごとに一度に 1 つのワークフローのみを実行できます。 別のワークフローの処理中に新しいワークフローを作成しようとすると、**409 Conflict** エラー応答（「ワークフローは既に処理中です…」）が表示されます。

この場合、進行中のワークフローが完了するまで待つか、ワークフロー ID を取得して、そのステータスをポーリングします。 現在のワークフローが完了したら、新しいワークフローを作成できます。

## エンティティマッピングリファレンス {#entity-mapping}

意思決定管理から決定に移行する際、エンティティは次のようにマッピングされます。

| 意思決定管理 | 決定 |
|-------------------|-------------|
| オファー | 決定項目 |
| オファーコレクション | 項目の収集 |
| 実施要件ルール | 実施要件ルール |
| ランキング式 | ランキング式 |
| 決定 | 選択戦略+決定ポリシー |
| Campaign | Campaign *（基本コンテンツのみ）* |
| プレースメント | サーフェス + チャネル設定 |
| タグ | 統合タグ |

## ワークフロークリーンアップ {#cleanup}

ワークフローリソースは、サービスユーザーのみが削除できます。 削除操作には、ワークフローの `If-Match` 値を持つ `_etag` ヘッダーが必要です。

**使用可能な削除操作：**

* `DELETE /migration/service/dependency/{id}`
* `DELETE /migration/service/migrations/{id}`
* `DELETE /migration/service/rollbacks/{id}`

>[!NOTE]
>
>ワークフローの削除は、適切な権限を持つサービスアカウントでのみ使用できます。 ワークフローリソースを削除する必要がある場合は、システム管理者に問い合わせてください。

## 関連トピック {#related-topics}

* [ 意思決定管理から意思決定への移行 ](migrate-to-decisioning.md) - Decisioning に移行するメリットと機能を説明します
* [決定の基本を学ぶ](gs-experience-decisioning.md)
* [決定ガードレールと制限](decisioning-guardrails.md)
* [Decisioning API の基本を学ぶ](api-reference/getting-started.md)

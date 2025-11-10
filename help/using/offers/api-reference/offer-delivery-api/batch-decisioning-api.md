---
title: Batch Decisioning API
description: Batch Decisioning API を使用して、事前定義された決定範囲内でオーディエンスのプロファイルに最適なオファーを選択する方法を説明します。
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 1ed01a6b-5e42-47c8-a436-bdb388f50b4e
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 100%

---


# [!DNL Batch Decisioning] API を使用したオファーの配信 {#deliver-offers-batch}

[!DNL Batch Decisioning] API を使用すると、組織は、1 回の呼び出しで特定のオーディエンスのすべてのプロファイルに対して決定支援機能を使用できます。オーディエンス内の各プロファイルに対するオファーコンテンツは、Adobe Experience Platform データセットに配置され、カスタムバッチワークフローで使用できます。

[!DNL Batch Decisioning] API を使用すると、決定範囲の Adobe Experience Platform オーディエンスに含まれるすべてのプロファイルに最適なオファーを、データセットに入力できます。例えば、ある組織が [!DNL Batch Decisioning] を実行して、メッセージ配信ベンダーにオファーを送信できるようにするとします。その場合、これらのオファーは、同じユーザーオーディエンスに対してバッチメッセージ配信用に送信されるコンテンツとして使用されます。

これを実現するため、組織は次の手順を実行します。

* 次の 2 つのリクエストを含む [!DNL Batch Decisioning] API を実行します。

   1. **バッチ POST リクエスト**&#x200B;で、オファーの選択をバッチ処理するワークロードを開始します。

   2. **バッチ GET リクエスト**&#x200B;で、バッチのワークロードステータスを取得します。

* データセットをメッセージ配信ベンダー API にエクスポートします。

<!-- (Refer to the [export jobs endpoint documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=ja) to learn more about exporting audiences.) -->

>[!NOTE]
>
>Batch Decisioning は、Journey Optimizer インターフェイスを使用して実行することもできます。詳しくは、[この節](../../batch-delivery.md)を参照してください。グローバルな前提条件と、Batch Decisioning を使用する際に考慮すべき制限事項に関する情報を示しています。

* **データセットごとの実行中のバッチジョブの数**：データセットごとに一度に最大 5 つのバッチジョブを実行できます。同じ出力データセットを持つその他のバッチリクエストがキューに追加されます。前のジョブの実行が完了したら、キュー内のジョブがピックアップされ処理されます。
* **フリークエンシーキャップ**：1 日に 1 回、プロファイルスナップショットからバッチが実行されます。[!DNL Batch Decisioning] API は頻度をキャップし、常に最新のスナップショットからプロファイルを読み込みます。

## はじめに {#getting-started}

この API を使用する前に、次の前提条件の手順を実行してください。

### 決定の準備 {#prepare-decision}

1 つ以上の決定を準備するには、データセット、オーディエンスおよび決定が作成されていることを確認します。これらの前提条件について詳しくは、[この節](../../batch-delivery.md)を参照してください。

### API の要件 {#api-requirements}

すべての [!DNL Batch Decisioning] リクエストには、[Decision Management API 開発者ガイド](../getting-started.md)で言及されているものに加え、次のヘッダーが必要になります。

* `Content-Type`：`application/json`
* `x-request-id`：リクエストを識別する一意の文字列。
* `x-sandbox-name`：サンドボックス名。

## バッチ処理の開始 {#start-a-batch-process}

ワークロードを開始して決定をバッチ処理するには、`/workloads/decisions` エンドポイントに対して POST リクエストを実行します。

>[!NOTE]
>
>バッチジョブの処理時間について詳しくは、[この節](../../batch-delivery.md)を参照してください。

**API 形式**

```https
POST {ENDPOINT_PATH}/workloads/decisions
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dwm` |

**リクエスト**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dwm/workloads/decisions' \
-H 'x-request-id: f671a589-eb7b-432f-b6b9-23d5b796b4dc' \
-H 'Content-Type: application/json' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-sandbox-id: {SANDBOX_ID}' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-d '{
  "xdm:segmentIds": [
    "609028e4-e66c-4776-b0d9-c782887e2273"
  ],
  "xdm:dataSetId": "6196b4a1a63bd118dafe093c",
  "xdm:propositionRequests": [
        {
            "xdm:activityId": "xcore:offer-activity:1410cdcda196707b",
            "xdm:placementId": "xcore:offer-placement:1410c4117306488a",
            "xdm:itemCount": 1
        }
  ],
  "xdm:includeContent": false
}'
```

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `xdm:activityId` | 決定の一意の ID。 |  |
| `xdm:dataSetId` | 決定イベントを書き込むことができる出力データセット。 | `6196b4a1a63bd118dafe093c` |
| `xdm:includeContent` | これはオプションのフィールドで、デフォルトでは `false` です。`true` の場合、オファーのコンテンツは、データセットの決定イベントに含まれます。 | `false` |
| `xdm:itemCount` | 決定範囲に対してリクエストされたオプションなどの項目数を示すオプションのフィールドです。デフォルトでは、API は範囲ごとに 1 つのオプションを返しますが、このフィールドを指定することで、より多くのオプションを明示的に求めることができます。1 つの範囲につき、最低 1 個、最大 30 個のオプションをリクエストできます。 | `xcore:offer-activity:1410cdcda196707b` |
| `xdm:placementId` | 一意のプレースメント ID。 | `xcore:offer-placement:1410c4117306488a` |
| `xdm:propositionRequests` | `placementId` および `activityId` を含むラッパー |  |
| `xdm:segmentIds` | 値は、オーディエンスの一意の ID を含んだ配列です。値を 1 つだけ含めることができます。 | `609028e4-e66c-4776-b0d9-c782887e2273` |

詳しくは、[意志決定管理ドキュメント](../../get-started/starting-offer-decisioning.md)で、主な概念とプロパティの概要を参照してください。

**応答**

```json
{
    "@id": "47efef25-4bcf-404f-96e2-67c4f784a1f5",
    "xdm:imsOrgId": "9GTO98D5F@AdobeOrg",
    "ode:createDate": 1648078924834,
    "ode:status": "QUEUED"
}
```

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `@id` | 単一のワークロードを識別する意思決定管理によって生成される UUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | 組織 ID。 | `9GTO98D5F@AdobeOrg` |
| `ode:createDate` | 決定ワークロードリクエストが作成された時間。 | `1648078924834` |
| `ode:status` | ワークロードのステータス。 | `ode:status: "QUEUED"` |

## バッチ決定に関する情報の取得 {#retrieve-information-on-a-batch-decision}

特定の決定に関する情報を取得するには、`/workloads/decisions` エンドポイントに対して GET リクエストを実行し、決定に対応するワークロード ID 値を指定します。

**API 形式**

```https
GET {ENDPOINT_PATH}/workloads/decisions/{WORKLOAD_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dwm` |
| `{WORKLOAD_ID}` | 単一のワークロードを識別する意思決定管理によって生成される UUID。 | `47efef25-4bcf-404f-96e2-67c4f784a1f5` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dwm/workloads/decisions/f395ab1f-dfaf-48d4-84c9-199ad6354591' \
-H 'x-request-id: 7832a42a-d4e5-413b-98e8-e49bef056436' \
-H 'Content-Type: application/json' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H'x-sandbox-id: {SANDBOX_ID}' \
-H 'Authorization: Bearer {ACCESS_TOKEN}'
```

**応答**

```json
{
   "@id": "f395ab1f-dfaf-48d4-84c9-199ad6354591",
    "xdm:imsOrgId": "{IMS_ORG}",
    "ode:createDate": 1648076994405,
    "ode:status": "COMPLETED"
}
```

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `@id` | 単一のワークロードを識別する意思決定管理によって生成される UUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | 組織 ID | `9GTO98D5F@AdobeOrg` |
| `ode:createDate` | 決定ワークロードリクエストが作成された時間。 | `1648076994405` |
| `ode:status` | ワークロードのステータスは「待機中」で始まり、「処理中」、「取り込み中」、「完了」または「エラー」に変わります。 | `ode:status: "COMPLETED"` |
| `ode:statusDetail` | ステータスが「処理中」または「取り込み中」の場合は、sparkJobId や batchID などの詳細が表示されます。ステータスが「エラー」の場合は、エラーの詳細が表示されます。 |  |

## 次の手順 {#next-steps}

この API ガイドでは、[!DNL [!DNL Batch Decisioning]] API を使用してワークロードのステータスを確認し、オファーを配信しました。詳しくは、[意思決定管理の概要](../../get-started/starting-offer-decisioning.md)を参照してください。

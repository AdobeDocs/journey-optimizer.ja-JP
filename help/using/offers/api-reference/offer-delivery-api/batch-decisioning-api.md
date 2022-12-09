---
title: Batch Decisioning API
description: ここでは、Batch Decisioning API を使用して、定義済みのデシジョンスコープ内のセグメント化されたプロファイルに最適なオファーを選択する方法について説明します。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 1ed01a6b-5e42-47c8-a436-bdb388f50b4e
source-git-commit: 34ab78408981d2b53736b31c94412da06cb860c4
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 0%

---


# API を使用した提供を提供します [!DNL Batch Decisioning] 。 {#deliver-offers-batch}

この API を使用すると、 [!DNL Batch Decisioning] 1 回の呼び出しで特定のセグメントのすべてのプロファイルに対して decisioning の機能を使用できます。 セグメント内の各プロファイルのオファーコンテンツは、Adobe エクスペリエンスプラットフォームデータセットに配置されます。カスタムバッチワークフローで使用できます。

[!DNL Batch Decisioning]この API を使用すると、デシジョンスコープについて Adobe 体験プラットフォームセグメントのすべてのプロファイルに最適なオファーをデータセットに読み込むことができます。例えば、組織では、メッセージ配信ベンダーにオファーを送信できるように、を実行 [!DNL Batch Decisioning] することができます。 その後、それらのコンテンツは、1つのユーザーセグメントに送信されるバッチメッセージ配信用に送信されるコンテンツとして使用されます。

そのためには、次のように整理します。

* 次の2つの要求を含む API を実行し [!DNL Batch Decisioning] ます。

   1. バッチ処理による作業を開始するための **バッチ POST 要求** 。

   2. バッチのワークロード状態を取得するための **バッチ get 要求** 。

* データセットをメッセージ配信ベンダー API に書き出します。

<!-- (Refer to the [export jobs endpoint documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en) to learn more about exporting segments.) -->

>[!NOTE]
>
>バッチ decisioning は、旅のオプティマイザーインターフェイスを使用して実行することもできます。 詳しくは、ここを [ 参照してください。これは、inbto を使用している場合に、グローバルな前提条件および制限についての情報を提供するセクション ](../../batch-delivery.md) です。

* **1** つのデータセットに対して実行されたバッチジョブの数: 一度に最大5個のバッチジョブを同時に実行することができます。 同じ出力データセットを持つその他のバッチ要求は、キューに追加されます。 前のジョブの実行が完了すると、キューに入れられたジョブが処理されます。
* **周波数上限** : バッチは1日に1回実行されるプロファイルのスナップショットから実行されます。 API に [!DNL Batch Decisioning] よって頻度が高くなり、常に最新のスナップショットからプロファイルが読み込まれます。

## はじめに {#getting-started}

この API を使用する前に、以下の手順を完了していることを確認してください。

### 決定の準備 {#prepare-decision}

1つまたは複数の決定を行うには、データセット、セグメント、および決定を作成したことを確認してください。 この節 ](../../batch-delivery.md) では、これらの前提条件に [ ついて詳しく説明します。

### API の要件 {#api-requirements}

すべて [!DNL Batch Decisioning] の要求には、デシジョン管理 API デベロッパーガイド ](../getting-started.md) で [ 参照されているヘッダーの他に、次のヘッダーも必要です。

* `Content-Type`: `application/json`
* `x-request-id`: 要求を識別する一意のストリング。
* `x-sandbox-name`: サンドボックス名を指定します。
* `x-sandbox-id`: サンドボックス ID。

## バッチ処理の開始 {#start-a-batch-process}

バッチ処理の決定にワークロードを開始するには、その `/workloads/decisions` エンドポイントに POST 要求を行います。

>[!NOTE]
>
>この節 ](../../batch-delivery.md) では、 [ バッチジョブの処理時間に関する詳細情報を提供します。

**API フォーマット**

```https
POST {ENDPOINT_PATH}/{CONTAINER_ID}/workloads/decisions
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/ode` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**要求**

```shell
curl -X POST 'https://platform.adobe.io/data/core/ode/0948b1c5-fff8-3b76-ba17-909c6b93b5a2/workloads/decisions' \
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

| &quot; | つい | 一 |
| -------- | ----------- | ------- |
| `xdm:segmentIds` | 値は、セグメントの一意の識別子が格納されている配列です。 1つの値のみを含めることができます。 | `609028e4-e66c-4776-b0d9-c782887e2273` |
| `xdm:dataSetId` | 意思決定イベントを書き込むことができる出力データセットを指定します。 | `6196b4a1a63bd118dafe093c` |
| `xdm:propositionRequests` | And を含む `placementId` ラッパー `activityId` |  |
| `xdm:activityId` | 決定の一意の識別子。 | `xcore:offer-activity:1410cdcda196707b` |
| `xdm:placementId` | 一意の配置識別子。 | `xcore:offer-placement:1410c4117306488a` |
| `xdm:itemCount` | これは、decisioning スコープに要求されたオプションなどのアイテムの数を示すオプションのフィールドです。 デフォルトでは、API はスコープごとに1つのオプションを返しますが、このフィールドを指定することによって、追加のオプションを明示的に求めることができます。 各スコープには、最低1個のオプションと最大30個のオプションを指定できます。 | `1` |
| `xdm:includeContent` | これはオプションのフィールドで、デフォルトで指定され `false` ています。 この場合 `true` 、offer コンテンツはデータセットの意思決定イベントに含まれます。 | `false` |

主要な概念とプロパティの概要については、 [ デシジョン管理のマニュアル ](../../get-started/starting-offer-decisioning.md) を参照してください。

**対し**

```json
{
    "@id": "47efef25-4bcf-404f-96e2-67c4f784a1f5",
    "xdm:imsOrgId": "9GTO98D5F@AdobeOrg",
    "xdm:containerId": "0948b1c5-fff8-3b76-ba17-909c6b93b5a2",
    "ode:createDate": 1648078924834,
    "ode:status": "QUEUED"
}
```

| &quot; | つい | 一 |
| -------- | ----------- | ------- |
| `@id` | 意思決定管理によって生成された1つのワークロードを識別する UUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | 組織 ID。 | `9GTO98D5F@AdobeOrg` |
| `xdm:containerId` | コンテナ ID。 | `0948b1c5-fff8-3b76-ba17-909c6b93b5a2` |
| `ode:createDate` | 意思決定の作業負荷要求が作成された時刻。 | `1648078924834` |
| `ode:status` | ワークロードの状態。 | `ode:status: "QUEUED"` |

## バッチ処理に関する情報の取得 {#retrieve-information-on-a-batch-decision}

特定の意思決定についての情報を取得するには、その `/workloads/decisions` エンドポイントへの GET 要求を行い、それに対応するワークロード ID の値を指定します。

**API フォーマット**

```https
GET  {ENDPOINT_PATH}/{CONTAINER_ID}/workloads/decisions/{WORKLOAD_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/ode` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{WORKLOAD_ID}` | 意思決定管理によって生成された1つのワークロードを識別する UUID。 | `47efef25-4bcf-404f-96e2-67c4f784a1f5` |

**要求**

```shell
curl -X GET 'https://platform.adobe.io/data/core/ode/0948b1c5-fff8-3b76-ba17-909c6b93b5a2/workloads/decisions/f395ab1f-dfaf-48d4-84c9-199ad6354591' \
-H 'x-request-id: 7832a42a-d4e5-413b-98e8-e49bef056436' \
-H 'Content-Type: application/json' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H'x-sandbox-id: {SANDBOX_ID}' \
-H 'Authorization: Bearer {ACCESS_TOKEN}'
```

**対し**

```json
{
    "@id": "f395ab1f-dfaf-48d4-84c9-199ad6354591",
    "xdm:imsOrgId": "{IMS_ORG}",
    "xdm:containerId": "0948b1c5-fff8-3b76-ba17-909c6b93b5a2",
    "ode:createDate": 1648076994405,
    "ode:status": "COMPLETED"
}
```

| &quot; | つい | 一 |
| -------- | ----------- | ------- |
| `@id` | 意思決定管理によって生成された1つのワークロードを識別する UUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | 組織 ID | `9GTO98D5F@AdobeOrg` |
| `xdm:containerId` | コンテナ ID | `0948b1c5-fff8-3b76-ba17-909c6b93b5a2` |
| `ode:createDate` | 意思決定のワークロード要求が作成された時間。 | `1648076994405` |
| `ode:status` | ワークロードの状態は、「QUEUED」によって開始され、「処理中」、「INGESTING」、「COMPLETED」または「ERROR」に変更されます。 | `ode:status: "COMPLETED"` |
| `ode:statusDetail` | これにより、状態が &quot;PROCESSING&quot; または &quot;INGESTING&quot; の場合は、sparkJobId と batchID などの詳細が表示されます。 ステータスが「エラー」である場合は、エラーの詳細が表示されます。 |  |

## 次の手順 {#next-steps}

この API ガイドに従うことによって、「! [!]DNL [!DNL Batch Decisioning] ] API を行います。 詳細については、「意思決定管理 ](../../get-started/starting-offer-decisioning.md) 」の概要を参照してください [ 。

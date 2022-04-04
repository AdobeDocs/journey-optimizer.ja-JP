---
title: バッチ判定 API
description: バッチ判定 API を使用して、事前定義された決定範囲内のセグメント化されたプロファイルに最適なオファーを選択する方法を説明します。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 1ed01a6b-5e42-47c8-a436-bdb388f50b4e
source-git-commit: 3c40f3b6f76272db32b929a886a0cd63f797a842
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---


# を使用してオファーを配信 [!DNL Batch Decisioning] API {#deliver-offers-batch}

この [!DNL Batch Decisioning] API を使用すると、特定のセグメント内のすべてのプロファイルに対して、offer decisioning機能を 1 回の呼び出しで使用できます。 セグメント内の各プロファイルのオファーコンテンツは、Adobe Experience Platformデータセットに配置され、カスタムバッチワークフローで使用できます。

を使用 [!DNL Batch Decisioning] API を使用すると、決定範囲に関するAdobe Experience Platformセグメント内のすべてのプロファイルに最適なオファーをデータセットに入力できます。 例えば、ある組織が [!DNL Batch Decisioning] したがって、メッセージ配信ベンダーにオファーを送信できます。 その後、これらのオファーは、同じセグメントのユーザーに対するバッチメッセージ配信用に送信されるコンテンツとして使用されます。

これをおこなうには、次の手順を実行します。

* を実行します。 [!DNL Batch Decisioning] 次の 2 つのリクエストを含む API。

   1. A **バッチPOSTリクエスト** ：オファーの選択をバッチ処理するワークロードを開始します。

   2. A **バッチGETリクエスト** ：バッチ・ワークロード・ステータスを取得します。

* データセットをメッセージ配信ベンダー API にエクスポートします。

<!-- (Refer to the [export jobs endpoint documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en) to learn more about exporting segments.) -->

## はじめに {#getting-started}

この API を使用する前に、次の前提条件の手順を実行してください。

### 決定を準備 {#prepare-decision}

次の手順に従って、1 つ以上の決定を準備します。

* 決定結果を書き出すには、「ODE DecisionEvents」スキーマを使用してデータセットを作成します。

* 評価してから更新する Platform セグメントを作成します。 詳しくは、 [セグメント化ドキュメント](http://www.adobe.com/go/segmentation-overview-en) を参照してください。

* Adobe Journey Optimizerで、決定（決定 ID とプレースメント ID で構成される決定範囲を持つ）を作成します。 詳しくは、 [決定範囲の定義に関する節](../../offer-activities/create-offer-activities.md) 」を参照してください。

### API の要件 {#api-requirements}

すべて [!DNL Batch Decisioning] リクエストには、 [決定管理 API 開発者ガイド](../getting-started.md):

* `Content-Type`：`application/json`
* `x-request-id`:リクエストを識別する一意の文字列。
* `x-sandbox-name`:サンドボックス名。
* `x-sandbox-id`:サンドボックス ID。

## バッチ処理の開始 {#start-a-batch-process}

ワークロードを開始して決定をバッチ処理するには、次に対してPOST要求を行います： `/workloads/decisions` endpoint.

**API 形式**

```https
POST {ENDPOINT_PATH}/{CONTAINER_ID}/workloads/decisions
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/ode` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**リクエスト**

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

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `xdm:segmentIds` | 値は、セグメントの一意の識別子を含む配列です。 値を 1 つだけ含めることができます。 | `609028e4-e66c-4776-b0d9-c782887e2273` |
| `xdm:dataSetId` | 判定イベントを書き込むことができる出力 dataSet。 | `6196b4a1a63bd118dafe093c` |
| `xdm:propositionRequests` | 次を含むラッパー `placementId` および `activityId` |  |
| `xdm:activityId` | 決定の一意の ID。 | `xcore:offer-activity:1410cdcda196707b` |
| `xdm:placementId` | 一意のプレースメント ID。 | `xcore:offer-placement:1410c4117306488a` |
| `xdm:itemCount` | これは、判定範囲に対してリクエストされたオプションなどの項目数を示すオプションのフィールドです。 デフォルトでは、API はスコープごとに 1 つのオプションを返しますが、このフィールドを指定することで、追加のオプションを明示的に求めることができます。 1 つのスコープにつき、最低 1 つ、最大 30 個のオプションをリクエストできます。 | `1` |
| `xdm:includeContent` | これはオプションのフィールドで、は `false` デフォルトでは。 If `true`の場合、オファーのコンテンツは、データセットの判定イベントに含まれます。 | `false` |

詳しくは、 [決定管理ドキュメント](../../get-started/starting-offer-decisioning.md) を参照してください。

**応答** 

```json
{
    "@id": "47efef25-4bcf-404f-96e2-67c4f784a1f5",
    "xdm:imsOrgId": "9GTO98D5F@AdobeOrg",
    "xdm:containerId": "0948b1c5-fff8-3b76-ba17-909c6b93b5a2",
    "ode:createDate": 1648078924834,
    "ode:status": "QUEUED"
}
```

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `@id` | 単一のワークロードを識別するOffer decisioningによって生成される UUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | IMS 組織の ID。 | `9GTO98D5F@AdobeOrg` |
| `xdm:containerId` | コンテナ ID。 | `0948b1c5-fff8-3b76-ba17-909c6b93b5a2` |
| `ode:createDate` | 決定ワークロードリクエストが作成された時間。 | `1648078924834` |
| `ode:status` | ワークロードのステータス。 | `ode:status: "QUEUED"` |

## バッチ決定に関する情報の取得 {#retrieve-information-on-a-batch-decision}

特定の決定に関する情報を取得するには、に対してGETリクエストを実行します。 `/workloads/decisions` エンドポイントを使用して、判定に対応するワークロード ID 値を指定します。

**API 形式**

```https
GET  {ENDPOINT_PATH}/{CONTAINER_ID}/workloads/decisions/{WORKLOAD_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/ode` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{WORKLOAD_ID}` | 単一のワークロードを識別するOffer decisioningによって生成される UUID。 | `47efef25-4bcf-404f-96e2-67c4f784a1f5` |

**リクエスト**

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

**応答** 

```json
{
    "@id": "f395ab1f-dfaf-48d4-84c9-199ad6354591",
    "xdm:imsOrgId": "{IMS_ORG}",
    "xdm:containerId": "0948b1c5-fff8-3b76-ba17-909c6b93b5a2",
    "ode:createDate": 1648076994405,
    "ode:status": "COMPLETED"
}
```

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `@id` | 単一のワークロードを識別するOffer decisioningによって生成される UUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | IMS 組織 ID | `9GTO98D5F@AdobeOrg` |
| `xdm:containerId` | コンテナ ID | `0948b1c5-fff8-3b76-ba17-909c6b93b5a2` |
| `ode:createDate` | 決定ワークロードリクエストが作成された時間。 | `1648076994405` |
| `ode:status` | ワークロードのステータスは「QUEUED」で始まり、「PROCESSING」、「INGESTING」、「COMPLETED」または「ERROR」に変わります。 | `ode:status: "COMPLETED"` |
| `ode:statusDetail` | ステータスが「処理中」または「取り込み中」の場合は、sparkJobId や batchID などの詳細が表示されます。 ステータスが「ERROR」の場合は、エラーの詳細が表示されます。 |  |

## サービスレベル {#service-levels}

各バッチ判定の終了時間は、ワークロードが作成されてから出力データセットで判定結果を使用できるまでの期間です。 POSTリクエストペイロードのセグメントサイズが、エンドツーエンドのバッチ判定時間に影響する主な要因です。  次に、異なるセグメントサイズに関する観察を示します。

| セグメントサイズ | エンドツーエンドの処理時間 |
|--------------|----------------------------|
| 1 万人以下のプロファイル | 6 分 |
| 100 万件以下のプロファイル | 10 分 |
| 1,500 万件以下のプロファイル | 75 分 |

## 制限事項 {#limitations}

を使用する場合、 [!DNL Batch Decisioning] API では、次の制限に注意してください。

* **データセットごとの単一のバッチジョブ**:現在、一度に 1 つのバッチジョブのみをデータセットごとに実行できます。 同じ出力データセットを持つ他のリクエストは、前のリクエストが終了する前に HTTP 429（リクエストが多すぎます）で応答します。
* **頻度キャップ**:1 日に 1 回発生するプロファイルスナップショットからバッチが実行されます。 この [!DNL Batch Decisioning] API は頻度を制限し、常に最新のスナップショットからプロファイルを読み込みます。

## 次の手順 {#next-steps}

この API ガイドに従うことで、[!DNL [!DNL Batch Decisioning]] API 詳しくは、[意思決定管理の概要](../../get-started/starting-offer-decisioning.md)をご覧ください。


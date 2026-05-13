---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Batch Decisioning API
description: Batch Decisioning APIを使用して、定義済みの決定範囲内のオーディエンスのプロファイルに最適なオファーを選択する方法を説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 1ed01a6b-5e42-47c8-a436-bdb388f50b4e
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/2FrtFGbl169aXj29ltmUKS23eXFns1cG8TPojw3TwCY
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: c132d929-fa62-4271-803e-b823be07b914
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 749
ht-degree: 0%

---

# [!DNL Batch Decisioning] APIを使用したオファーの配信 {#deliver-offers-batch}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../experience-decisioning/gs-experience-decisioning.md)

[!DNL Batch Decisioning] APIを使用すると、組織は1回の呼び出しで、特定のオーディエンス内のすべてのプロファイルに対して決定機能を使用できます。 オーディエンスの各プロファイルのオファーコンテンツは、カスタムバッチワークフローで使用できるAdobe Experience Platform データセットに配置されます。

[!DNL Batch Decisioning] APIを使用すると、Adobe Experience Platform オーディエンスのすべてのプロファイルに最適なオファーをデータセットに入力して、決定範囲に設定できます。 例えば、組織が[!DNL Batch Decisioning]を実行して、メッセージ配信ベンダーにオファーを送信できるようにすることができます。 これらのオファーは、同じオーディエンスにバッチメッセージを配信するために送信されるコンテンツとして使用されます。

これを実現するために、組織は次のようなことを行います。

* 2つのリクエストを含む[!DNL Batch Decisioning] APIを実行します。

   1. オファーの選択をバッチ処理するためのワークロードを開始するための&#x200B;**Batch POST リクエスト**&#x200B;です。

   2. バッチ ワークロードのステータスを取得するための&#x200B;**バッチ GET リクエスト**。

* データセットをメッセージ配信ベンダーAPIに書き出します。

<!-- (Refer to the [export jobs endpoint documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html) to learn more about exporting audiences.) -->

>[!NOTE]
>
>バッチ判定は、Journey Optimizerインターフェイスを使用して実行することもできます。 詳細については、[このセクション &#x200B;](../../batch-delivery.md)を参照してください。このセクションでは、バッチ決定を使用する際に考慮すべきグローバルな前提条件と制限について説明しています。

* **データセットごとに実行中のバッチジョブの数**：データセットごとに最大5つのバッチジョブを同時に実行できます。 同じ出力データセットを持つ他のバッチリクエストは、キューに追加されます。 前のジョブの実行が完了すると、キューに入れられたジョブが処理されます。
* **頻度の上限**: 1日に1回実行されるプロファイル スナップショットからバッチが実行されます。 [!DNL Batch Decisioning] APIは頻度に上限を設定し、常に最新のスナップショットからプロファイルを読み込みます。

## Adobe Experience Managerの導入方法 {#getting-started}

このAPIを使用する前に、次の前提条件の手順を完了していることを確認してください。

### 決定の準備 {#prepare-decision}

1つ以上の意思決定を準備するには、データセット、オーディエンス、意思決定を作成していることを確認します。 これらの前提条件について詳しくは、[このセクション &#x200B;](../../batch-delivery.md)を参照してください。

### APIの要件 {#api-requirements}

すべての[!DNL Batch Decisioning]要求には、[意思決定管理API開発者ガイド &#x200B;](../getting-started.md)で参照されているものに加えて、次のヘッダーが必要です。

* `Content-Type`: `application/json`
* `x-request-id`：リクエストを識別する一意の文字列。
* `x-sandbox-name`: サンドボックス名。

## バッチプロセスを開始 {#start-a-batch-process}

バッチ処理の決定に対するワークロードを開始するには、`/workloads/decisions` エンドポイントにPOST リクエストを行います。

>[!NOTE]
>
>バッチジョブの処理時間に関する詳細な情報は、[この節](../../batch-delivery.md)で確認できます。

**API形式**

```https
POST {ENDPOINT_PATH}/workloads/decisions
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dwm` |

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

| プロパティ | 効果 | 例 |
| -------- | ----------- | ------- |
| `xdm:activityId` | 決定の一意のID。 |  |
| `xdm:dataSetId` | 決定イベントを書き込むことができる出力データセット。 | `6196b4a1a63bd118dafe093c` |
| `xdm:includeContent` | これはオプションのフィールドで、デフォルトでは`false`です。 `true`の場合、オファーコンテンツはデータセットの決定イベントに含まれます。 | `false` |
| `xdm:itemCount` | これは、決定範囲に対して要求されたオプションなどの項目数を示すオプションのフィールドです。 デフォルトでは、APIはスコープごとに1つのオプションを返しますが、このフィールドを指定することで、より多くのオプションを明示的に要求できます。 スコープごとに、最低1個および最大30個のオプションを要求できます。 | `xcore:offer-activity:1410cdcda196707b` |
| `xdm:placementId` | 一意のプレースメント ID。 | `xcore:offer-placement:1410c4117306488a` |
| `xdm:propositionRequests` | `placementId`と`activityId`を含むラッパー |  |
| `xdm:segmentIds` | 値は、オーディエンスの一意のIDを含む配列です。 1つの値のみを含めることができます。 | `609028e4-e66c-4776-b0d9-c782887e2273` |

主な概念とプロパティの概要については、[意思決定管理ドキュメント &#x200B;](../../get-started/starting-offer-decisioning.md)を参照してください。

**応答**

```json
{
    "@id": "47efef25-4bcf-404f-96e2-67c4f784a1f5",
    "xdm:imsOrgId": "9GTO98D5F@AdobeOrg",
    "ode:createDate": 1648078924834,
    "ode:status": "QUEUED"
}
```

| プロパティ | 効果 | 例 |
| -------- | ----------- | ------- |
| `@id` | 単一のワークロードを識別する意思決定管理によって生成されるUUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | 組織ID。 | `9GTO98D5F@AdobeOrg` |
| `ode:createDate` | 決定ワークロード要求が作成された時間。 | `1648078924834` |
| `ode:status` | ワークロードのステータス。 | `ode:status: "QUEUED"` |

## バッチ決定に関する情報の取得 {#retrieve-information-on-a-batch-decision}

特定の決定に関する情報を取得するには、決定に対応するワークロード ID値を指定しながら、`/workloads/decisions` エンドポイントに対してGET リクエストを行います。

**API形式**

```https
GET {ENDPOINT_PATH}/workloads/decisions/{WORKLOAD_ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dwm` |
| `{WORKLOAD_ID}` | 単一のワークロードを識別する意思決定管理によって生成されるUUID。 | `47efef25-4bcf-404f-96e2-67c4f784a1f5` |

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

| プロパティ | 効果 | 例 |
| -------- | ----------- | ------- |
| `@id` | 単一のワークロードを識別する意思決定管理によって生成されるUUID。 | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | 組織ID | `9GTO98D5F@AdobeOrg` |
| `ode:createDate` | 決定ワークロード要求が作成された時間。 | `1648076994405` |
| `ode:status` | ワークロードのステータスは「キュー済み」で始まり、「処理中」、「取り込み」、「完了」または「エラー」に変わります。 | `ode:status: "COMPLETED"` |
| `ode:statusDetail` | ステータスが「処理中」または「取り込み」の場合、sparkJobIdやbatchIDなどの詳細が表示されます。 ステータスが「ERROR」の場合、エラーの詳細が表示されます。 |  |

## 次のステップ {#next-steps}

このAPI ガイドに従って、[!DNL [!DNL Batch Decisioning]] APIを使用してワークロードのステータスを確認し、オファーを配信しました。 詳しくは、[意思決定管理の概要](../../get-started/starting-offer-decisioning.md)を参照してください。

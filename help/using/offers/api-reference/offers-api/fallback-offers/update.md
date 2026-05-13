---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: フォールバックオファーの更新
description: フォールバックオファーは、他のオファーの対象とならない顧客に送信されます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 7ff69887-620f-4bc0-b8ff-5144ff30696c
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/OA-HssEzGE-lJSnC-GI9BkKmYzIqIT96frG6qtTWjAE
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 178
ht-degree: 100%

---

# フォールバックオファーの更新 {#update-fallback-offer}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


[!DNL Offer Library] API に対して PATCH リクエストを実行することで、コンテナ内のフォールバックオファーを変更または更新できます。

使用可能な操作など、JSON パッチの詳細については、[JSON パッチの公式ドキュメント](https://jsonpatch.com/)を参照してください。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、リクエストヘッダーの *Content-Type* フィールドと *Accept* フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Content-Type | `application/json` |

**API 形式**

```http
PATCH /{ENDPOINT_PATH}/offers/{ID}?offer-type=fallback
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 更新するエンティティの ID。 | `fallbackOffer1234` |

**リクエスト**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offers/fallbackOffer1234?offer-type=fallback' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated fallback offer"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated fallback offer description"
    }
]'
```

| パラメーター | 説明 |
| --------- | ----------- |
| `op` | 接続の更新に必要なアクションを定義するのに使用される操作呼び出し。 操作には、`add`、`replace`、`remove`、`copy` および `test` があります。 |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターの更新に使用する新しい値。 |

**応答**

応答が成功すると、フォールバックオファーの更新された詳細（`id` を含む）が返されます。

```json
{
    "id": "{ID}",
    "datasetId": "{DATASET_ID}",
    "sandboxId": "{SANDBOX_ID}",
    "etag": 2,
    "createdDate": "2023-09-07T12:47:43.012Z",
    "lastModifiedDate": "2023-09-07T12:47:43.012Z",
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

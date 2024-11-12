---
title: 決定項目の更新
description: 決定項目は、コレクションとカタログに作成および整理できるマーケティングオファーです。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: b924b7d0-bbed-409e-8173-0685fc41d7de
source-git-commit: b057d198d3c5b12121ee50d7a97ff4b33b8209b4
workflow-type: ht
source-wordcount: '137'
ht-degree: 100%

---

# 決定項目の更新 {#update-decision-items}

オファーライブラリ API に対して PATCH リクエストを実行することで、決定項目を変更または更新できます。

使用可能な操作など、JSON パッチについて詳しくは、[JSON パッチの公式ドキュメント](https://jsonpatch.com/)を参照してください。

**API 形式**

```http
PATCH /{ENDPOINT_PATH}/offer-items/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 更新するエンティティの ID。 | `offerItem1234` |

**リクエスト**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offer-items/offerItem1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-schema-id: {SCHEMA_ID}' \
-d '[
    {
        "op": "replace",
        "path": "/_experience/decisioning/decisionitem/itemName",
        "value": "Updated offer item"
    },
    {
        "op": "replace",
        "path": "/_experience/decisioning/decisionitem/itemDescription",
        "value": "Updated offer item description"
    }
]'
```

| パラメーター | 説明 |
| --------- | ----------- |
| `value` | パラメーターの更新に使用する新しい値。 |
| `path` | 更新するパラメーターのパス。 |
| `op` | 実行する操作のタイプ。操作には、`add`、`replace`、`remove`、`copy` および `test` があります。 |

**応答**

応答が成功すると、ID を含む更新した項目の詳細が返されます。後の手順で ID を使用して、決定項目を更新または削除できます。

```json
{
    "etag": 2,
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "{ID}",
    "sandboxId": "{SANDBOX_ID}",
    "createdDate": "2023-05-31T15:09:11.771Z",
    "lastModifiedDate": "2023-05-31T15:09:11.771Z",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

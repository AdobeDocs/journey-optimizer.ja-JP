---
title: 項目コレクションの参照
description: コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 60b2990e-e3a6-4d4b-8851-889cf91b0eef
source-git-commit: 7bfbb88c2817d18b7897a7fe1657ebf11be6eb58
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 100%

---

# 項目コレクションの参照 {#lookup-item-collection}

リクエストパスに ID を含む GET リクエストをオファーライブラリ API に対して実行することで、特定の項目コレクションを参照できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/item-collections/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 検索するエンティティの ID。 | `itemCollections1234` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/item-collections/itemCollections1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、項目コレクションの詳細が返されます。

```json
{
    "created": "2024-01-31T18:28:52.888Z",
    "modified": "2024-06-28T19:44:13.112Z",
    "etag": 7,
    "schemas": [
        "https://ns.adobe.com/experience/decisioning/item-collection;version=1.2"
    ],
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "itemCollection1234",
    "name": "Item collection One",
    "description": "Item collection",
    "constraints": [
        {
            "itemCatalogId": "itemCatalog1234",
            "uiModel": "{\"operator\":\"equals\",\"value\":{\"left\":\"_experience.decisioning.decisionitem.itemName\",\"right\":\"Some offer item\"}}"
        }
    ]
}
```

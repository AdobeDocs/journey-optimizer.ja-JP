---
title: コレクション修飾子の検索
description: コレクション修飾子を使用すると、オファーをより適切に整理し並べ替えることができます。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: e2d1f093-c1b8-4c4c-a20f-4bd7c2ea5269
source-git-commit: ba7d065523116c12e22eec300df13c29d92a54fb
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 100%

---

# コレクション修飾子の検索 {#look-up-tag}

特定のコレクション修飾子（旧称「タグ」）を検索するには、リクエストパスにコレクション修飾子 ID を含んだ GET リクエストを Offer Library API に対して実行します。

**API 形式**

```http
GET /{ENDPOINT_PATH}/tags/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 検索するエンティティの ID。 | `tag1234` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/tags/tag1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答では、コレクション修飾子の詳細（コンテナ ID、インスタンス ID、一意のコレクション修飾子 `@id` に関する情報を含む）が返されます。

```json
{
    "created": "2022-09-16T19:00:02.070+00:00",
    "modified": "2022-09-16T19:00:02.070+00:00",
    "etag": 1,
    "schemas": [
        "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
    ],
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "tag1234",
    "name": "Sneakers"
}
```

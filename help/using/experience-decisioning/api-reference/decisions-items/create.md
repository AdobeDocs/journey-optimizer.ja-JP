---
title: 決定項目の作成
description: 決定項目は、コレクションとカタログに作成および整理できるマーケティングオファーです。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: dcff8803404228bbed40e998d802bb6c0f4ac67e
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 16%

---


# 決定項目の作成 {#create-decision-items}

オファーライブラリ API に対して決定リクエストを実行することで、POST項目を作成できます。

**Accept ヘッダーと Content-Type ヘッダー**

次の表に、リクエストヘッダーの Content-Type フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Content-Type | `application/json` |

**API 形式**

```http
POST /{ENDPOINT_PATH}/offer-items
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

**リクエスト**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/offer-items' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-schema-id: {SCHEMA_ID}' \
-d '{
    "_experience": {
        "decisioning": {
            "offeritem": {
                "lifecycleStatus": "approved"
            },
            "decisionitem": {
                "itemCalendarConstraints": {
                    "endDate": "2030-12-31T08:00:00.000Z",
                    "startDate": "2024-06-10T04:00:00.000Z"
                },
                "itemCatalogID": "itemCatalong1234",
                "itemConstraints": {
                    "eligibilityRule": "rule1234",
                    "profileConstraintType": "eligibilityRule"
                },
                "itemDescription": "Offer item description",
                "itemName": "Offer Item One",
                "itemPriority": 1
            }
        }
    },
    "_<imsOrg>": {
        "some_field": "some value"
    }
}'
```

**応答**

応答が成功すると、ID など、新しく作成された決定項目の詳細が返されます。 後の手順で、この ID を使用して決定項目を更新または削除できます。

```json
{
    "etag": 1,
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

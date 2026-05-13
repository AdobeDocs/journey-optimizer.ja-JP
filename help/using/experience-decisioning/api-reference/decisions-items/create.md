---
title: 決定項目の作成
description: オファーライブラリ APIを使用して決定項目を作成する方法を説明します。
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: e60b0eec-29bc-4411-9eab-08eaf738fc79
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/Ts-7IQQx6A4HhWeDl9sci8XSvgYRH7VbwgUgxRrl9uM
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 79
ht-degree: 0%

---

# 決定項目の作成 {#create-decision-items}

オファーライブラリ APIにPOST リクエストを行うことで、決定項目を作成できます。

**API形式**

```http
POST /{ENDPOINT_PATH}/offer-items 
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

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
        "foo": "bar"
    }
}'
```

**応答**

応答が成功すると、IDを含む、新しく作成された決定項目の詳細が返されます。 後の手順でIDを使用して、決定項目を更新または削除できます。

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


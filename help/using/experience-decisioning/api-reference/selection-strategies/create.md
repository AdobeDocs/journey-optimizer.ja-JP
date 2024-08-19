---
title: 選択戦略の作成
description: 選択戦略は、制約に関連付けられたコレクションと、オファーを決定するためのランキングメソッドで構成されます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: eb89bc5205d98a67cd0bb42bebbd9429786e33e7
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 25%

---


# 選択戦略の作成 {#create-selection-strategy}

オファーライブラリ API に対してセレクションリクエストを実行することで、POST戦略を作成できます。

**API 形式**

```http
POST /{ENDPOINT_PATH}/selection-strategies 
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

**リクエスト**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/selection-strategies' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{    
    "name": "Selection Strategy One",
    "description": "Selection Strategy",
    "rank": {
        "priority": 1,
        "order": {
            "orderEvaluationType": "static"
        }
    },
    "profileConstraint": {
        "profileConstraintType": "eligibilityRule",
        "eligibilityRule": "offerRule1234"
    },
    "optionSelection": {
        "filter": "itemCollection1234",
    }
}'
```

**応答**

応答が成功すると、ID など、新しく作成した選択戦略の詳細が返されます。 後の手順で、この ID を使用して選択戦略を更新または削除できます。

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

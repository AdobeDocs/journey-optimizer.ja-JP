---
title: 実施要件ルールの作成
description: 実施要件ルールを使用すると、プロファイル属性やオーディエンスなど、ターゲットにしたい項目に基づいて実施要件を満たす候補を定義できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 14%

---

# 実施要件ルールの作成 {#create-eligibility-rule}

オファーライブラリ API に対して POST リクエストを実行することで、実施要件ルールを作成できます。

**API 形式**

```http
POST /{ENDPOINT_PATH}/eligibility-rules 
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

**リクエスト**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/offer-rules' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '
{
    "name": "test dule",
    "description": "xxxxxx",
    "exdRule": true,
    "condition": {
        "type": "PQL",
        "format": "pql/text",
        "value": "inSegment(\"849807b6-0a76-4895-96d9-89996477f23b\") and billingAddress.city.equals(\"san jose\", false)"
    }
}'
```

**応答**

応答が成功すると、ID など、新しく作成された実施要件ルールの詳細が返されます。 後の手順で、この ID を使用して実施要件ルールを更新または削除できます。

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

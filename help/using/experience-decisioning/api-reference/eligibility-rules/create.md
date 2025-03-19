---
title: 実施要件ルールの作成
description: 実施要件ルールを使用すると、プロファイル属性やオーディエンスなど、ターゲットにする項目に基づいて実施要件を満たす候補を定義できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 39c6e82e-c1b1-4dda-a941-3db6324cef37
source-git-commit: 6378c4a8cb911088c685166b9c1b29a1773d47b7
workflow-type: ht
source-wordcount: '89'
ht-degree: 100%

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

応答が成功すると、ID を含む新規作成した実施要件ルールの詳細が返されます。後の手順で ID を使用して、実施要件ルールを更新または削除できます。

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

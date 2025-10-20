---
title: 決定の検索
description: 決定には、オファーの選択を通知するロジックが含まれています。
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: ee242f0f-f331-4f41-9418-938b4ca1dda3
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 100%

---

# 決定の検索 {#look-up-decision}

[!DNL Offer Library] API に対してリクエストパスに決定 `id` を含む GET リクエストを実行することで、特定の決定を検索できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/offer-decisions/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 参照するエンティティの ID。 | `offerDecision1234` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-decisions/offerDecision1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、一意の決定 `id` に関する情報を含む決定の詳細が返されます。

```json
{
    "created": "2022-11-15T16:35:06.873+00:00",
    "modified": "2023-05-15T15:00:27.641+00:00",
    "etag": 3,
    "schemas": [
        "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.8"
    ],
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "offerDecision1234",
    "name": "Test Decision One",
    "status": "draft",
    "startDate": "2021-08-23T07:00:00.000+00:00",
    "endDate": "2021-08-25T07:00:00.000+00:00",
    "fallback": "fallbackOffer1234",
    "criteria": [
        {
            "placements": [
                "offerPlacement1234",
                "offerPlacement5678"
            ],
            "rank": {
                "priority": 0,
                "order": {
                    "orderEvaluationType": "ranking-strategy",
                    "rankingStrategy": "123456789123"
                }
            },
            "profileConstraint": {
                "profileConstraintType": "none"
            },
            "optionSelection": {
                "filter": "offerCollection1234"
            }
        }
    ]
}
```

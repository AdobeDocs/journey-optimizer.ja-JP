---
title: 実施要件ルールの参照
description: 実施要件ルールを使用すると、プロファイル属性やオーディエンスなど、ターゲットにしたい項目に基づいて実施要件を満たす候補を定義できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 14%

---

# 実施要件ルールの参照 {#list-eligibility-rule}

リクエストパスに ID を含むオファーライブラリ API に対してGET リクエストを実行することで、特定の実施要件ルールを検索できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/offer-rules/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 検索するエンティティの ID。 | `rule1234` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-rules/rule1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、実施要件ルールの詳細が返されます。

```json
{
    "created": "2024-10-28T01:18:08.506Z",
    "modified": "2024-10-28T01:18:08.506Z",
    "etag": 1,
    "schemas": [
        "https://ns.adobe.com/experience/offer-management/eligibility-rule"
    ],
    "createdBy": "3254197F65569E890A49422F@658557135fa10b860a494019",
    "lastModifiedBy": "3254197F65569E890A49422F@658557135fa10b860a494019",
    "id": "dps:eligibility-rule:19af09a9ae45a8d3",
    "name": "dasdsa",
    "description": "",
    "exdRule": false,
    "condition": {
        "type": "PQL",
        "format": "pql/text",
        "value": "personalEmail.address.equals(\"youz@adobe.com\", false)"
    },
    "segmentModel": {
        "lifecycleState": "published",
        "expression": {
            "isValid": true,
            "logicalOperator": "and",
            "profileAttributesContainer": {
                "exclude": false,
                "items": [
                    {
                        "comparisonType": "equals",
                        "component": {
                            "id": "profile.personalEmail.address",
                            "__entity__": true,
                            "type": "Sz"
                        },
                        "isCaseSensitive": false,
                        "isPlaceholder": false,
                        "originalLocation": [],
                        "value": [
                            "youz@adobe.com"
                        ],
                        "itemType": "segmentRule"
                    }
                ],
                "logicalOperator": "and",
                "itemType": "segmentContainer"
            },
            "xEventAttributesContainer": {
                "exclude": false,
                "items": [],
                "logicalOperator": "then",
                "itemType": "eventTypeCardContainer"
            },
            "itemType": "segmentDefinition"
        },
        "isMissingAnsibleModel": false,
        "relationalExpression": false,
        "deprecated": {
            "status": false,
            "reason": ""
        },
        "description": "",
        "evaluationInfo": {
            "batch": {
                "enabled": true
            },
            "continuous": {
                "enabled": false
            },
            "synchronous": {
                "enabled": false
            }
        },
        "labels": [],
        "tags": [],
        "canHaveFolder": true,
        "mergePolicyId": "24526dbe-d615-4d41-9ebb-fd7f2b3dcdc2",
        "name": "dasdsa",
        "namespace": "ups"
    }
}
```

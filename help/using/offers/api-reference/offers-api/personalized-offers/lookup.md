---
title: パーソナライズされたオファーの検索
description: パーソナライズされたオファーは、実施要件ルールおよび制約に基づいてカスタマイズできるマーケティングメッセージです。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 2e30b155-688b-432b-a703-d09de12ebdfd
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 100%

---

# パーソナライズされたオファーの検索 {#look-up-personalized-offer}

パーソナライズされたオファーは、実施要件ルールおよび制約に基づいてカスタマイズできるマーケティングメッセージです。

リクエストパスにパーソナライズされたオファー ID を含む [!DNL Offer Library] API に対して GET リクエストを実行することで、パーソナライズされた特定のオファーを検索できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/offers/{ID}?offer-type=personalized
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 参照するエンティティの ID。 | `personalizedOffer1234` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offers/personalizedOffer1234?offer-type=personalized' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、一意のパーソナライズされたオファー `id` に関する情報を含むパーソナライズされたオファーの詳細が返されます。

```json
{
    "created": "2023-05-15T14:35:16.781+00:00",
    "modified": "2023-05-15T14:38:26.691+00:00",
    "etag": 2,
    "schemas": [
        "https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.15"
    ],
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "personalizedOffer1234",
    "name": "Test personalized offer with frequency constraint",
    "status": "draft",
    "representations": [
        {
            "channel": "https://ns.adobe.com/xdm/channel-types/web",
            "placement": "offerPlacement1234",
            "components": [
                {
                    "type": "html",
                    "format": "text/html",
                    "language": [
                        "en-us"
                    ],
                    "content": "Hello You qualify for our Discount of 60%"
                }
            ]
        }
    ],
    "selectionConstraint": {
        "startDate": "2022-07-27T05:00:00.000+00:00",
        "endDate": "2023-07-29T05:00:00.000+00:00",
        "profileConstraintType": "none"
    },
    "rank": {
        "priority": 0
    },
    "cappingConstraint": {},
    "frequencyCappingConstraints": [
        {
            "enabled": false,
            "limit": 1,
            "startDate": "2023-05-15T14:25:49.622+00:00",
            "endDate": "2023-05-25T14:25:49.622+00:00",
            "scope": "global",
            "entity": "offer",
            "repeat": {
                "enabled": false,
                "unit": "month",
                "unitCount": 1
            }
        }
    ]
}
```

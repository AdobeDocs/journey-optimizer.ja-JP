---
title: プレースメントの検索
description: プレースメントは、オファーの表示に使用するコンテナです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: db337b5c-426a-4695-81e8-3a1b041791f2
source-git-commit: a6ba9632f6de91ed7911012ec4174cb7a01f5f12
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 33%

---

# プレースメントの検索 {#look-up-placement}

特定の配置を検索するには、 [!DNL Offer Library] 配置を含む API `id`.

**API 形式**

```http
GET /{ENDPOINT_PATH}/placements/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 検索するエンティティの ID。 | `offerPlacement1234` |

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/placements/offerPlacement1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答は、一意の配置に関する情報を含む配置の詳細を返します `id`.

```json
{
     "created": "2023-05-15T11:22:50.031+00:00",
    "modified": "2023-05-15T11:22:50.031+00:00",
    "etag": 1,
    "schemas": [
        "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.5"
    ],
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "offerPlacement1234",
    "name": "Placement",
    "description": "Placement description",
    "componentType": "html",
    "channel": "https://ns.adobe.com/xdm/channel-types/web",
    "itemCount": 1,
    "allowDuplicatePlacements": false,
    "returnContent": false,
    "returnMetaData": {
        "decisionName": true,
        "offerName": true,
        "offerAttributes": true,
        "offerPriority": true,
        "placementName": true,
        "channelType": true,
        "contentType": true
    }
}
```

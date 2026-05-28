---
title: ExD プレースメントの参照
description: ExD プレースメントは、オファーを決定するための制約とランキング方法に関連付けられたコレクションで構成されます。
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
version: Journey Orchestration
exl-id: cc8ae245-a96a-401e-9157-e7d4b8982081
TQID: https://experienceleague.adobe.com/0vmTC00aXOb5CDyz77rupZZSnywE1n7eOx6czrtJZIU
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 79
ht-degree: 100%

---

# ExD プレースメントの参照 {#list-exd-placement}

リクエストパスに ID を含む GET リクエストを Offer Library API に対して実行することで、特定の ExD プレースメントを参照できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/exd-placements/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 参照するエンティティの ID。 | `placement1234` |

**リクエスト**

```shell
curl --location 'https://platform-stage.adobe.io/data/core/dps/exd-placements/dps:exd-placement:19c5fa7448c6fcab' \
--header 'Content-Type: application/json' \
--header 'x-gw-ims-org-id: {IMS_ORG}' \
--header 'x-sandbox-name: {SANDBOX_NAME}' \
--header 'x-api-key: {API_KEY}' \
--header 'Authorization: Bearer {ACCESS_TOKEN}'
```

**応答**

応答が成功すると、ExD プレースメントの詳細が返されます。

```json
{
    "created": "2024-11-14T20:56:45.540Z",
    "modified": "2024-11-14T20:56:45.540Z",
    "etag": 1,
    "schemas": [
        "exd-placement"
    ],
    "createdBy": "71486D7B5F4011980A494030@AdobeID",
    "lastModifiedBy": "71486D7B5F4011980A494030@AdobeID",
    "id": "dps:exd-placement:19c5fa7448c6fcab",
    "name": "Test Exd Placement1 Car",
    "description": "brand panel",
    "tags": [
        "3d75b849-b344-402b-9d9e-5d750bd46884"
    ],
    "channel": "https://ns.adobe.com/xdm/channel-types/email",
    "channelConfiguration": "530b76f9-dcd6-4fd5-8c52-38e29b04a60a",
    "status": "active"
}            
```

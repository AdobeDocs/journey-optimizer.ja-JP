---
title: ExD プレースメントの更新
description: ExD プレースメントは、オファーを決定するための制約とランキング方法に関連付けられたコレクションで構成されます。
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
version: Journey Orchestration
exl-id: 74e090e1-4dbe-484b-a482-ef43e082e7b1
TQID: https://experienceleague.adobe.com/6RpNeMQUn2qEfAzQ-Q7f7PgBRJCLqp7WnsoKx0xr12s
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 100%

---

# ExD プレースメントの更新 {#update-exd-placement}

Offer Library API に対して PUT リクエストを実行することで、プレースメントを変更または更新できます。

使用可能な操作など、JSON PUT について詳しくは、JSON PUT の公式ドキュメントを参照してください。

**Accept ヘッダーと Content-Type ヘッダー**

リクエストヘッダーの Content-Type フィールドを構成する有効な値を次の表に示します。

| パラメーター | 説明 |
| --------- | ----------- |
| Content-Type | `application/json` |

**API 形式**

```http
PUT /{ENDPOINT_PATH}/exd-placements/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 更新するエンティティの ID。 | `placement1234` |

**リクエスト**

```shell
curl --location --request PUT 'https://platform-stage.adobe.io/data/core/dps/exd-placements/dps:exd-placement:19aca09b0a456e57' \
--H 'Content-Type: application/json' \
--H 'x-gw-ims-org-id: {IMS_ORG}' \
--H 'x-sandbox-name: {SANDBOX_NAME}' \
--H 'x-api-key: {API_KEY}' \
--H 'Authorization: Bearer {ACCESS_TOKEN}' \
--X '{
  "id":"dps:exd-placement:19aca09b0a456e57",
  "description": "Keyboard application",
  "status":"archived"
}'
```

| パラメーター | 説明 |
| --------- | ----------- |
| `value` | パラメーターの更新に使用する新しい値。 |
| `path` | 更新するパラメーターのパス。 |
| `op` | 接続の更新に必要なアクションを定義するのに使用される操作呼び出し。 操作には、`add`、`replace`、`remove`、`copy` および `test` があります。 |

**応答**

正常な応答では、ID など、ExD プレースメントの更新された詳細が返されます。

```json
{
    "etag": 2,
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

---
title: 拡張プレースメントを更新
description: 拡張プレースメントは、オファーを決定するための制約とランキングメソッドに関連付けられたコレクションで構成されます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 39%

---

# 拡張プレースメントの更新 {#update-exd-placement}

オファーライブラリ API に対してPUT リクエストを実行することで、プレースメントを変更または更新できます。

使用可能な操作など、JSON PUTについて詳しくは、公式の JSON PUT ドキュメントを参照してください。

**Accept ヘッダーと Content-Type ヘッダー**

次の表に、リクエストヘッダーの Content-Type フィールドを構成する有効な値を示します。

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
| `op` | 接続の更新に必要なアクションを定義するのに使用される操作呼び出し。操作には、`add`、`replace`、`remove`、`copy`、`test` があります。 |

**応答**

応答が成功すると、ID を含む、拡張プレースメントの更新された詳細が返されます。

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

---
title: Exd プレースメントの作成
description: Exd 戦略は、オファーを決定するための制約とランキングメソッドに関連付けられたコレクションで構成されます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 15%

---

# Exd プレースメントの作成 {#create-exd-placement}

オファーライブラリ API に対して POST リクエストを実行することで、拡張プレースメントを作成できます。

**Accept ヘッダーと Content-Type ヘッダー**

次の表に、リクエストヘッダーの Content-Type フィールドを構成する有効な値を示します。

| パラメーター | 説明 |
| --------- | ----------- |
| Content-Type | `application/json` |

**API 形式**

```http
POST /{ENDPOINT_PATH}/exd-placements
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

**リクエスト**

```shell
curl --location 'https://platform-stage.adobe.io/data/core/dps/exd-placements' \
--header 'Content-Type: application/json' \
--header 'x-gw-ims-org-id: {IMS_ORG}' \
--header 'x-sandbox-name: {SANDBOX_NAME}' \
--header 'x-api-key: {API_KEY}' \
--header 'Authorization: Bearer {ACCESS_TOKEN}' \
--data '{
  "name": "Test Exd Placement1 Pants",
  "channel": "https://ns.adobe.com/xdm/channel-types/email",
  "tags":["3d75b849-b344-402b-9d9e-5d750bd46884"],
  "channelConfiguration":"530b76f9-dcd6-4fd5-8c52-38e29b04a60a",
  "description": "compressing alarm",
  "status":"active"
}'
```

**応答**

正常な応答では、ID を含む新しく作成された exd プレースメントの詳細が返されます。 後の手順で、この ID を使用して拡張プレースメントを更新または削除できます。

```json
{
    "id": "dps:exd-placement:19cb038eca47bead",
    "sandboxId": "068abf40-575e-11ea-8512-9b1bfdb82603",
    "etag": 2,
    "createdDate": "2024-11-18T18:48:56.298Z",
    "lastModifiedDate": "2024-11-18T18:57:27.457Z",
    "createdBy": "71486D7B5F4011980A494030@AdobeID",
    "lastModifiedBy": "71486D7B5F4011980A494030@AdobeID",
    "lastModifiedByClientId": "CJMTestClientACP"
}
```

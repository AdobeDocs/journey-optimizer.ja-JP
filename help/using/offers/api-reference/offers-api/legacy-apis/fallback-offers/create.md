---
title: フォールバックオファーの作成
description: フォールバックオファーは、他のオファーの対象とならない顧客に送信されます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 6156689d9e5d7abedcd612389c5e332c695601f0
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---


# フォールバックオファーの作成 {#create-fallback-offer}

コンテナ ID を提供しながら [!DNL Offer Library] API に POST リクエストを実行することで、フォールバックオファーを作成できます。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、リクエストヘッダーの *Content-Type* フィールドと *Accept* フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Accept | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1"` |

**API 形式**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | フォールバックオファーが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**リクエスト**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/offers?offer-type=fallback' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{
    "name": "Test Fallback Offer DPS",
    "description": "Fallback Offer description",
    "status": "approved",
    "selectionConstraint": {
        "startDate": "2022-06-10T00:30:00.000+00:00",
        "endDate": "2032-06-06T23:29:21.402+00:00",
        "profileConstraintType": "none"
    },
    "representations": [
    {
            "components": [
    {
                    "deliveryURL": "https://mysite.com",
                    "type": "imagelink",
                    "format": "image/png"
                }
            ],
            "channel": "https://ns.adobe.com/xdm/channel-types/web",
            "placement": "offerPlacement1234"
        }
    ],
    "rank": {
        "priority": 1
    }
}'
```

**応答**

正常な応答では、新たに作成されたフォールバックオファーに関する情報（一意のインスタンス ID とプレースメント `@id` を含む）が返されます。後の手順で、このインスタンス ID を使用してフォールバックオファーを更新または削除できます。後のチュートリアルでは、一意のフォールバックオファー `@id` を使用して決定を作成できます。


```json
{
    "instanceId": "b3966680-13ec-11eb-9c20-8323709cfc65",
    "@id": "xcore:fallback-offer:124e2e764b1ac1b9",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-21T22:28:11.111732Z",
    "repo:lastModifiedDate": "2020-10-21T22:28:11.111732Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

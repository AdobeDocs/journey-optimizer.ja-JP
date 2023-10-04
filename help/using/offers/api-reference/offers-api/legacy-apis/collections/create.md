---
title: コレクションの作成
description: コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 6156689d9e5d7abedcd612389c5e332c695601f0
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 70%

---

# コレクションの作成 {#create-collection}

コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。

コンテナ ID を提供しながら [!DNL Offer Library] API に対して POST リクエストを実行して、コレクションを作成できます。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、リクエストヘッダーの *Content-Type* フィールドと *Accept* フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Accept | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"` |

**API 形式**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |

**リクエスト**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
        "xdm:name": "Offer Collection 1",
        "xdm:filterType": "anyTags",
        "xdm:ids": [
            "xcore:tag:124e147572cd7866"
        ]
    }'
```

**応答**

正常な応答は、新しく作成されたコレクションに関する情報 ( コレクションの `id`. 以下を使用すると、 `id` 後の手順で、コレクションを更新または削除するか、後のチュートリアルで、決定を作成します。

```json
{
   "@id": "xcore:offer-filter:124e3594ce8b4930",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-21T22:59:17.345797Z",
    "repo:lastModifiedDate": "2020-10-21T22:59:17.345797Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

---
title: コレクションの作成
description: コレクションは、オファーのカテゴリなど、marketer によって定義されている事前に定義された条件に基づいて作成されたオファーのサブセットです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 683f8b86-8545-46d0-a4a8-25c5b3c7b9c3
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# コレクションの作成 {#create-collection}

コレクションは、オファーのカテゴリなど、marketer によって定義されている事前に定義された条件に基づいて作成されたオファーのサブセットです。

コレクションを作成するには、API に対し [!DNL Offer Library] て POST 要求を行い、コンテナ ID を指定します。

## Accept ヘッダーと Content-type ヘッダー {#accept-and-content-type-headers}

次の表は、要求ヘッダー内の Content-type *および* Accept *フィールドを構成* する有効な値を示しています。

| ヘッダー名 | 数値 |
| ----------- | ----- |
| よう | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| コンテンツタイプ | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"` |

**API フォーマット**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクションが格納されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**要求**

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

**対し**

応答が成功した場合は、一意のインスタンス ID や配置 `@id` など、新しく作成されたコレクションについての情報が返されます。 後のステップで、インスタンス ID を使用してコレクションを更新または削除することができます。 以降のチュートリアルでは、一意のコレクション `@id` を使用して、決定を行うことができます。

```json
{
    "instanceId": "0bf31c20-13f1-11eb-a752-e58fd7dc4cb3",
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

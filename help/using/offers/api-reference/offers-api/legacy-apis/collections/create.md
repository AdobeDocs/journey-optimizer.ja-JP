---
title: コレクションの作成
description: コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: ea79add2-1ea7-4c5c-ba67-f99d10975c4f
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 56%

---

# コレクションの作成 {#create-collection}

コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。

に対してコレクションリクエストを実行することで、POSTを作成できます。 [!DNL Offer Library] API、コンテナ ID を提供している間。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、を構成する有効な値を示します *Content-Type* および *承諾* リクエストヘッダーのフィールド :

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
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクションが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

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

正常な応答では、新たに作成されたコレクションに関する情報（一意のインスタンス ID とプレースメントを含む）が返されます `@id`. 後の手順で、このインスタンス ID を使用してコレクションを更新または削除できます。 後のチュートリアルで、独自のコレクション`@id` を使用して決定を作成できます。

```json
{
   "@id": "xcore:offer-filter:124e3594ce8b4930",
    "repo:etag": 1,
    "repo:createdDate": "2023-10-21T22:59:17.345797Z",
    "repo:lastModifiedDate": "2023-10-21T22:59:17.345797Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

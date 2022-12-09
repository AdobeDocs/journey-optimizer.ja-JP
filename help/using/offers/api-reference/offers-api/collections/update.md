---
title: コレクションの更新
description: コレクションは、オファーのカテゴリなど、marketer によって定義されている事前に定義された条件に基づいて作成されたオファーのサブセットです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7d766f0a-4fcb-434a-bbfd-e18ade71ae56
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# コレクションの更新 {#update-collection}

API に対する [!DNL Offer Library] 修正プログラム要求を作成することによって、コレクションを変更または更新することができます。

使用可能な操作を含む JSON 修正プログラムについて詳しくは、オフィシャル [ Json 修正プログラムのマニュアル ](http://jsonpatch.com/) を参照してください。

## Accept ヘッダーと Content-type ヘッダー {#accept-and-content-type-headers}

次の表は、要求ヘッダー内の Content-type *および* Accept *フィールドを構成* する有効な値を示しています。

| ヘッダー名 | 数値 |
| ----------- | ----- |
| よう | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| コンテンツタイプ | `application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"` |

**API フォーマット**

```http
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクションが格納されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するコレクションのインスタンス id です。 | `0bf31c20-13f1-11eb-a752-e58fd7dc4cb3` |

**要求**

```shell
curl -X PATCH \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0bf31c20-13f1-11eb-a752-e58fd7dc4cb3' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        {
            "op": "add",
            "path": "/_instance/xdm:filterType",
            "value": "anyTags"
        },
        {
            "op": "add",
            "path": "/_instance/xdm:ids",
            "value": ["xcore:tag:124e147572cd7866"]
        }
    ]'
```

| 指定 | つい |
| --------- | ----------- |
| `op` | 接続を更新するために必要なアクションを定義するために使用される操作呼び出し。 次のような操作を `remove` `replace` 実行できます。 `add` |
| `path` | 更新するパラメーターのパスを指定します。 |
| `value` | パラメーターを更新する新しい値を指定します。 |

**対し**

応答が成功した場合は、一意のインスタンス ID とコレクション `@id` を含むコレクションの更新された詳細が返されます。

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

---
title: 配置の更新
description: 配置は、オファーを示すために使用されるコンテナです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 6990918c-e736-4f28-9ac6-9ac3101b069f
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# 配置の更新 {#update-placement}

API に [!DNL Offer Library] 修正プログラムを適用することによって、コンテナ内の位置を変更または更新することができます。

使用可能な操作を含む JSON 修正プログラムについて詳しくは、オフィシャル [ Json 修正プログラムのマニュアル ](http://jsonpatch.com/) を参照してください。

## Accept ヘッダーと Content-type ヘッダー {#accept-and-content-type-headers}

次の表は、要求ヘッダー内の Content-type *および* Accept *フィールドを構成* する有効な値を示しています。

| ヘッダー名 | 数値 |
| ----------- | ----- |
| よう | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| コンテンツタイプ | `application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"` |

**API フォーマット**

```http
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | 配置が配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新する位置のインスタンス id です。 | `9aa58fd0-13d7-11eb-928b-576735ea4db8` |

**要求**

```shell
curl -X PATCH \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/9aa58fd0-13d7-11eb-928b-576735ea4db8' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'\
  -d '[
        {
            "op": "replace",
            "path": "/_instance/xdm:name",
            "value": "Sales and Promotions Placement"
        },
        {
            "op": "replace",
            "path": "/_instance/xdm:description",
            "value": "A test placement to contain offers of sales and discounts"
        }
    ]'
```

| 指定 | つい |
| --------- | ----------- |
| `op` | 接続を更新するために必要なアクションを定義するために使用される操作呼び出し。 次のような操作を `remove` `replace` 実行できます。 `add` |
| `path` | 更新するパラメーターのパスを指定します。 |
| `value` | パラメーターを更新する新しい値を指定します。 |

**対し**

応答が成功すると、配置の更新された詳細が返されます。これは、一意のインスタンス ID と配置 `@id` を含みます。

```json
{
    "instanceId": "9aa58fd0-13d7-11eb-928b-576735ea4db8",
    "@id": "xcore:offer-placement:124e0be5699743d3",
    "repo:etag": 2,
    "repo:createdDate": "2020-10-21T19:57:09.837456Z",
    "repo:lastModifiedDate": "2020-10-21T19:59:10.700149Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

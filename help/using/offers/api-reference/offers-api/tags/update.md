---
title: タグの更新
description: タグを使用すると、キャンペーンをより簡単に整理し、並べ替えることができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 918927e1-ad7a-4937-b652-2a0932e9efa1
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# タグの更新 {#update-tag}

API に対する [!DNL Offer Library] 修正プログラム要求を行うことにより、コンテナのタグを変更または更新することができます。

使用可能な操作を含む JSON 修正プログラムについて詳しくは、オフィシャル [ Json 修正プログラムのマニュアル ](http://jsonpatch.com/) を参照してください。

## Accept ヘッダーと Content-type ヘッダー {#accept-and-content-type-headers}

次の表は、要求ヘッダー内の Content-type *および* Accept *フィールドを構成* する有効な値を示しています。

| ヘッダー名 | 数値 |
| ----------- | ----- |
| よう | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| コンテンツタイプ | `application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/tag;version=0.1"` |

**API フォーマット**

```http
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | タグが配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するタグのインスタンス id。 | `d48fd160-13dc-11eb-bc55-c11be7252432` |

**要求**

```shell
curl -X PATCH \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/d48fd160-13dc-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/tag;version=0.1"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'\
  -d '[
        {
          "op": "replace",
          "path": "/_instance/xdm:name",
          "value": "Sales and promotions for the holidays"
        }
    ]'
```

| 指定 | つい |
| --------- | ----------- |
| `op` | 接続を更新するために必要なアクションを定義するために使用される操作呼び出し。 次のような操作を `remove` `replace` 実行できます。 `add` |
| `path` | 更新するパラメーターのパスを指定します。 |
| `value` | パラメーターを更新する新しい値を指定します。 |

**対し**

応答が成功した場合は、一意のインスタンス ID およびタグ `@id` を含む、タグの更新された詳細が返されます。

```json
{
    "instanceId": "d48fd160-13dc-11eb-bc55-c11be7252432",
    "@id": "xcore:tag:124e147572cd7866",
    "repo:etag": 2,
    "repo:createdDate": "2020-10-21T20:34:34.486296Z",
    "repo:lastModifiedDate": "2020-10-21T20:36:31.782607Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

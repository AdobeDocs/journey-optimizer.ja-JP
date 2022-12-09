---
title: フォールバックオファーのリスト
description: 代替オファーが他の特典に適合しない場合は、お客様に送信されます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: dd95c040-d905-4f5a-8cc5-58e39082e57e
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# フォールバックオファーのリスト {#list-fallback-offers}

予備機能が他の特典に適合しない場合は、お客様に送信されます。 フォールバックオファーを作成する手順は、オファーを作成する場合と同様に、1つまたは複数の表現を作成することによって構成されます。

API に対し [!DNL Offer Library] て1つの GET 要求を実行することによって、コンテナ内のすべてのフォールバックオファーのリストを表示することができます。

**API フォーマット**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_FALLBACK_OFFER}&{QUERY_PARAMS}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | フォールバックが提供されているコンテナーが格納されています。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_FALLBACK_OFFER}` | フォールバックオファーに関連付けられたスキーマを定義します。 | `https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1` |
| `{QUERY_PARAMS}` | 結果をフィルター処理するためのオプションのクエリパラメーターです。 | `limit=1` |

**要求**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1&limit=1' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリーパラメーターの使用 {#using-query-parameters}

クエリーパラメーターを使用して、リソースをリスト表示するときに結果をページに表示し、フィルターをかけることができます。

### ページャー {#paging}

ページングの最も一般的なクエリーパラメーターは、次のとおりです。

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `q` | 選択されているフィールドで検索するオプションのクエリストリングです。 クエリーストリングは、小文字にする必要があります。また、二重引用符で囲むことによって、トークン化したり、エスケープ特殊文字を使用しないようにすることができます。 この文字 `+ - = && || > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` は特殊な意味を持っており、クエリーストリングに表示されるときに、バックスラッシュでエスケープする必要があります。 | `default` |
| `qop` | は、q クエリ文字列パラメーターの値に AND または OR 演算子を適用します。 | `AND` / `OR` |
| `field` | 検索対象を限定するオプションのリストです。 このパラメーターは、次のように反復することもできます。フィールド = field1 [ 、フィールド = field2,... ] および (パス式は、_instance のようなドット区切りパスの形式で記述されています。 xdm: name) | `_instance.xdm:name` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。 「の `-` 前にタイトルを追加」 ( `orderby=-title` ) を指定すると、アイテムは見出し順 (z-index) にソートされます。 | `-repo:createdDate` |
| `limit` | 返されるフォールバックオファーの数を制限します。 | `limit=5` |

**対し**

応答が成功した場合は、アクセス権を持っているコンテナ内に存在するフォールバックオファーのリストが返されます。

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1",
    "requestTime": "2020-10-22T07:12:30.923768Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "053bc610-f8f9-11ea-ad6e-775ad2c9b1a1",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.5"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 3,
                "repo:createdDate": "2020-09-17T15:18:20.657299Z",
                "repo:lastModifiedDate": "2020-10-02T02:34:48.034583Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:name": "F1: Web fallback ",
                    "xdm:representations": [
                        {
                            "xdm:components": [
                                {
                                    "xdm:content": "aaa",
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-json",
                                    "dc:format": "application/json",
                                    "repo:name": "aa"
                                }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                            "xdm:placement": "xcore:offer-placement:122201b2150d98c2"
                        },
                        {
                            "xdm:components": [
                                {
                                    "xdm:content": "bb",
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-html",
                                    "dc:format": "text/html",
                                    "repo:name": "bb"
                                }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                            "xdm:placement": "xcore:offer-placement:122201c34354a2b4"
                        },
                        {
                            "xdm:components": [
                                {
                                    "xdm:deliveryURL": "https://mysite.com",
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-imagelink",
                                    "dc:format": "image/png",
                                    "repo:name": "ll"
                                }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                            "xdm:placement": "xcore:offer-placement:122207eddb05205a"
                        }
                    ],
                    "xdm:status": "approved",
                    "xdm:tags": [],
                    "@id": "xcore:fallback-offer:122206064e0d98df"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.5#053bc610-f8f9-11ea-ad6e-775ad2c9b1a1",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/053bc610-f8f9-11ea-ad6e-775ad2c9b1a1",
                        "@type": "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.5"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            }
        ],
        "total": 5,
        "count": 1
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1&limit=1",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=053bc610-f8f9-11ea-ad6e-775ad2c9b1a1&orderby=instanceId&schema=https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1&limit=1",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```

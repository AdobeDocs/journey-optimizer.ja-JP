---
title: コレクションのリスト
description: コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: ce39d77d-6d81-48d7-9e73-e1d537874018
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 38%

---

# コレクションのリスト {#list-collections}

コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。

に対して 1 回のGETリクエストを実行すると、コンテナ内のすべてのコレクションのリストを表示できます [!DNL Offer Library] API です。

**API 形式**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_FILTER}&{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{QUERY_PARAMS}` | 結果をフィルタリングする条件となるクエリパラメーター（オプション）。 | `limit=2` |
| `{CONTAINER_ID}` | コレクションが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_FILTER}` | コレクションに関連付けられたスキーマを定義します。<https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1> |
| `{QUERY_PARAMS}` | 結果をフィルタリングする条件となるクエリパラメーター（オプション）。 | `limit=1` |

**リクエスト**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1&limit=2' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリパラメーターの使用 {#using-query-parameters}

クエリパラメーターを使用して、リソースをリストする際に結果をページ化およびフィルタリングできます。

### ページング {#paging}

ページングで最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `q` | 選択したフィールドで検索するオプションのクエリ文字列。 クエリ文字列は小文字にする必要があり、トークン化を防ぎ、特殊文字をエスケープするために、二重引用符で囲むことができます。 文字 `+ - = && \|\| > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` 特別な意味を持ち、クエリ文字列に含める場合は、バックスラッシュでエスケープする必要があります。 | `demo collection` |
| `qop` | AND または OR 演算子を q クエリ文字列パラメーターの値に適用します。 | `AND` または `OR` |
| `field` | オプション検索を制限するフィールドのリスト。 このパラメーターは、次のように繰り返すことができます。field=field1[,field=field2,...] および（パス式は、_instance.xdm:name などのドット区切りパスの形式です） | `_instance.xdm:name` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。タイトルの前に `-` を追加すると（`orderby=-title`）、アイテムがタイトルの降順（Z-A）に並べ替えられます。 | `-repo:createdDate` |
| `limit` | 返されるコレクションの数を制限します。 | `limit=5` |

**応答**

応答が成功すると、アクセス権を持つコンテナ内に存在するコレクションのリストが返されます。

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1",
    "requestTime": "2023-10-21T21:14:19.282175Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "27c92e00-127d-11eb-b9fe-5bcfb5d7ef36",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2023-10-20T02:37:11.263718Z",
                "repo:lastModifiedDate": "2023-10-20T02:37:11.263718Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:ids": [
                        "xcore:tag:124bd3de7f598dd8"
                    ],
                    "xdm:name": "Mobile Demo",
                    "xdm:filterType": "anyTags",
                    "@id": "xcore:offer-filter:124bd44648f17ec1"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3#27c92e00-127d-11eb-b9fe-5bcfb5d7ef36",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/27c92e00-127d-11eb-b9fe-5bcfb5d7ef36",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            },
            {
                "instanceId": "2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2023-09-17T14:36:29.272451Z",
                "repo:lastModifiedDate": "2023-09-17T14:36:29.272451Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:ids": [
                        "xcore:personalized-offer:1221fbedfa4d98b0"
                    ],
                    "xdm:name": "demo collection",
                    "xdm:filterType": "offers",
                    "@id": "xcore:offer-filter:1221fc71c74d98b4"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3#2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            }
        ],
        "total": 8,
        "count": 2
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1&orderby=instanceId&schema=https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```

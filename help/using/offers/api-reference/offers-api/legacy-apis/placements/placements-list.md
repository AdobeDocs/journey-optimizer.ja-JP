---
title: プレースメントのリスト
description: プレースメントは、オファーの表示に使用するコンテナです。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 52fbf683-d86f-43c6-be1a-c06141b64b16
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 32%

---

# プレースメントのリスト {#list-placements}

プレースメントは、オファーの表示に使用するコンテナです。プレースメントは、適切なオファーコンテンツがメッセージ内の適切な場所に表示されるようにするのに役立ちます。 オファーにコンテンツを追加すると、そのコンテンツを表示できるプレースメントを選択するように求められます。

に対して 1 つのGETリクエストを実行すると、コンテナ内のすべてのプレースメントのリストを表示できます [!DNL Offer Library] API です。

**API 形式**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_PLACEMENT}&{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | プレースメントが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `SCHEMA_PLACEMENT}` | プレースメントに関連付けられたスキーマを定義します。 | `https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4` |
| `{QUERY_PARAMS}` | 結果をフィルタリングする条件となるクエリパラメーター（オプション）。 | `limit=2` |

## クエリパラメーターの使用 {#using-query-parameters}

クエリパラメーターを使用して、リソースをリストする際に結果をページ化およびフィルタリングできます。

### ページング {#paging}

ページングで最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `q` | 選択したフィールドで検索するオプションのクエリ文字列。 クエリ文字列は小文字にする必要があり、トークン化を防ぎ、特殊文字をエスケープするために、二重引用符で囲むことができます。 文字 `+ - = && \|\| > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` 特別な意味を持ち、クエリ文字列に含める場合は、バックスラッシュでエスケープする必要があります。 | Web サイトの JSON |
| `qop` | AND または OR 演算子を q クエリ文字列パラメーターの値に適用します。 | `AND` または `OR` |
| `field` | オプション検索を制限するフィールドのリスト。 このパラメーターは、次のように繰り返すことができます。field=field1[,field=field2,...] および（パス式は、_instance.xdm:name などのドット区切りパスの形式です） | `_instance.xdm:name` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。タイトルの前に `-` を追加すると（`orderby=-title`）、アイテムがタイトルの降順（Z-A）に並べ替えられます。 | `-repo:createdDate` |
| `limit` | 返されるプレースメントの数を制限します。 | `limit=5` |

**リクエスト**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4&limit=2' \
  -H 'Accept: *,application/json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、アクセス権を持つコンテナ内に存在するプレースメントのリストが返されます。

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4",
    "requestTime": "2023-10-21T19:48:51.843067Z",
    "_embedded": {
    "results": [
        {
                "instanceId": "0feb6a80-0f32-11eb-8110-e17787c335b5",
            "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"
            ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 2,
                "repo:createdDate": "2023-10-15T22:02:05.480449Z",
                "repo:lastModifiedDate": "2023-10-15T22:13:00.278175Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:name": "New placement name",
                    "xdm:componentType": "https://ns.adobe.com/experience/offer-management/content-component-html",
                    "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                    "xdm:description": "Updated placement description",
                    "@id": "xcore:offer-placement:12466ef35fc5baa0"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4#0feb6a80-0f32-11eb-8110-e17787c335b5",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0feb6a80-0f32-11eb-8110-e17787c335b5",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"
                    }
            }
        },
        {
                "instanceId": "269192b0-f8f2-11ea-8723-916b9fbadc53",
            "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"
                ],
                "productContexts": [
                    "acp"
            ],
                "repo:etag": 1,
                "repo:createdDate": "2023-09-17T14:29:10.107121Z",
                "repo:lastModifiedDate": "2023-09-17T14:29:10.107121Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:componentType": "https://ns.adobe.com/experience/offer-management/content-component-html",
                    "xdm:name": "demo placement",
                    "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                    "@id": "xcore:offer-placement:1221fac4e7340521"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4#269192b0-f8f2-11ea-8723-916b9fbadc53",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/269192b0-f8f2-11ea-8723-916b9fbadc53",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"
            }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
        }
    ],
        "total": 17,
        "count": 2
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=269192b0-f8f2-11ea-8723-916b9fbadc53&orderby=instanceId&schema=https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```

---
title: リスト決定
description: 決定には、オファーを選択に通知するロジックが含まれます。
translation-type: tm+mt
source-git-commit: 4ff255b6b57823a1a4622dbc62b4b8886fd956a0
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 64%

---

# リスト決定

決定(旧称「オファーアクティビティ」)には、オファーを選択に通知するロジックが含まれます。

[!DNL Offer Library] APIに対して1回のGETリクエストを実行することで、コンテナ内のすべての決定のリストを表示できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_ACTIVITIES}&{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | 決定が配置されるコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_ACTIVITIES}` | 決定に関連するスキーマを定義します。 | `https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5` |
| `{QUERY_PARAMS}` | 結果をフィルターするオプションのクエリパラメーター。 | `limit=2` |

**リクエスト**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5&limit=2' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリパラメーターの使用

リソースのリストを表示する際に、クエリパラメーターを使用してページを作成し、結果をフィルターできます。

### ページング

ページングに最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `q` | 選択したフィールドで検索するオプションのクエリ文字列。クエリ文字列は小文字にする必要があり、二重引用符で囲むことで、トークン化を防ぎ、特殊文字をエスケープできます。次の文字 `+ - = && || > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` は特別な意味を持ち、クエリ文字列に出現する場合はバックスラッシュでエスケープする必要があります。 | `default` |
| `qop` | 「q」クエリ文字列パラメーターの値に AND または OR 演算子を適用します。 | `AND` または `OR` |
| `field` | 検索を制限するフィールドのリスト（オプション）。このパラメーターは、field=field1[,field=field2,...] のように繰り返すことができます（パス式は「_instance.xdm:name」などのドット区切りパスの形式です）。 | `_instance.xdm:name` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。タイトルの前に `-` を追加すると（`orderby=-title`）、アイテムがタイトルの降順（Z-A）に並べ替えられます。 | `-repo:createdDate` |
| `limit` | 返される決定の数を制限する。 | `limit=5` |

**応答**

成功した場合は、アクセス権のあるコンテナ内に存在する決定のリストが返されます。

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5",
    "requestTime": "2020-10-21T22:38:32.838180Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "286f6f80-026b-11eb-9439-ad36e372cbf1",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 5,
                "repo:createdDate": "2020-09-29T15:48:02.808677Z",
                "repo:lastModifiedDate": "2020-10-15T15:49:26.673560Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:fallback": "xcore:fallback-offer:1233160780eaa2ef",
                    "xdm:name": "A2: Cross Channel Activity",
                    "xdm:endDate": "2020-10-09T07:00:00.000Z",
                    "xdm:startDate": "2020-09-29T07:00:00.000Z",
                    "xdm:status": "live",
                    "xdm:criteria": [
                        {
                            "xdm:placements": [
                                "xcore:offer-placement:122204529514a2c0"
                            ],
                            "xdm:optionSelection": {
                                "xdm:filter": "xcore:offer-filter:122a120f234dac7f"
                            }
                        },
                        {
                            "xdm:placements": [
                                "xcore:offer-placement:122201b2150d98c2"
                            ],
                            "xdm:optionSelection": {
                                "xdm:filter": "xcore:offer-filter:1222058c3f0d98de"
                            }
                        }
                    ],
                    "@id": "xcore:offer-activity:12317fe6aeec9330"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5#286f6f80-026b-11eb-9439-ad36e372cbf1",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/286f6f80-026b-11eb-9439-ad36e372cbf1",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            },
            {
                "instanceId": "4e0206d0-0e6a-11eb-884a-c1a1104e3d7d",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2020-10-14T22:12:10.300775Z",
                "repo:lastModifiedDate": "2020-10-14T22:12:10.300775Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:fallback": "xcore:fallback-offer:1233160780eaa2ef",
                    "xdm:name": "LBAR",
                    "xdm:endDate": "2021-02-28T08:00:00.000Z",
                    "xdm:startDate": "2020-10-14T07:00:00.000Z",
                    "xdm:status": "live",
                    "xdm:criteria": [
                        {
                            "xdm:placements": [
                                "xcore:offer-placement:122204529514a2c0"
                            ],
                            "xdm:optionSelection": {
                                "xdm:filter": "xcore:offer-filter:122a120f234dac7f"
                            }
                        }
                    ],
                    "@id": "xcore:offer-activity:124527ab00b2ebbc"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5#4e0206d0-0e6a-11eb-884a-c1a1104e3d7d",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/4e0206d0-0e6a-11eb-884a-c1a1104e3d7d",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            }
        ],
        "total": 7,
        "count": 2
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=4e0206d0-0e6a-11eb-884a-c1a1104e3d7d&orderby=instanceId&schema=https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```

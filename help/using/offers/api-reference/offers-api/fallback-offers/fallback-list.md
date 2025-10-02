---
title: フォールバックオファーのリスト
description: フォールバックオファーは、他のオファーの対象とならない顧客に送信されます。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: dd95c040-d905-4f5a-8cc5-58e39082e57e
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 95%

---

# フォールバックオファーのリスト {#list-fallback-offers}

フォールバックオファーは、他のオファーに対する資格がない場合に顧客に送信されます。フォールバックオファーの作成手順は、オファーを作成する際のように、1 つまたは複数の表示域を作成することで構成されます。

[!DNL Offer Library] API に対して単一の GET リクエストを実行することで、すべてのフォールバックオファーのリストを表示できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/offers?offer-type=fallback&{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | 結果をフィルタリングする条件となるクエリパラメーター（オプション）。 | `limit=2` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offers?offer-type=fallback&limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリパラメーターの使用 {#using-query-parameters}

リソースを一覧表示する際に、クエリパラメーターを使用して結果をページングおよびフィルタリングできます。

### ページング {#paging}

ページングに最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルターは次のとおりです。 <ul><li>プロパティは AND 演算でグループ化されます。</li><li>パラメーターは、property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...] または property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...] のように繰り返すことができます。</li><li>プロパティ式は `[!]field[op]value` の形式を使用（`[==,!=,<=,>=,<,>,~]` に `op`）し、正規表現をサポートします。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。名前の前に - を追加すると（orderby=-name）、名前の降順（Z ～ A）で項目が並べ替えられます。パス式は、ドット区切りのパスの形式です。このパラメーターは、`orderby=field1[,-fields2,field3,...]` のように繰り返すことができます。 | `orderby=id`、`-name` |
| `limit` | 返されるエンティティの数を制限します。 | `limit=5` |

**応答**

応答が成功すると、アクセスできるフォールバックオファーのリストが返されます。

```json
{
      "results": [
        {
            "created": "2023-06-08T14:04:41.011+00:00",
            "modified": "2023-06-08T14:04:41.011+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.8"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "fallbackOffer1234",
            "name": "Fallback Offer Web",
            "description": "Fallback Offer Web Description",
            "status": "draft",
            "representations": [
                {
                    "channel": "https://ns.adobe.com/xdm/channel-types/web",
                    "placement": "offerPlacement5678",
                    "components": [
                        {
                            "type": "imagelink",
                            "format": "image/png",
                            "deliveryURL": "https://mysite.com"
                        }
                    ]
                }
            ]
        },
        {
            "created": "2022-10-07T11:23:55.885+00:00",
            "modified": "2022-10-07T11:23:55.885+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.7"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "fallbackOffer5678",
            "name": "Fallback Offer email",
            "status": "approved",
            "representations": [
                {
                    "channel": "https://ns.adobe.com/xdm/channel-types/email",
                    "placement": "offerPlacement1234",
                    "components": [
                        {
                            "type": "component-text",
                            "format": "text/template",
                            "content": "Get free shipping!"
                        }
                    ]
                }
            ],
            "labels": [
                "core/C1"
            ]
        }
    ],
    "count": 2,
    "total": 3,
    "_links": {
        "self": {
            "href": "/offers?offer-type=fallback&href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/offers?offer-type=fallback&href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```

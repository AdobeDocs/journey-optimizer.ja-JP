---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: パーソナライズされたオファーのリスト
description: パーソナライズされたオファーとは、適格性ルールと制約にもとづいてカスタマイズ可能なマーケティングメッセージです。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 45d51918-1106-4b6b-b383-8ab4d9a4f7af
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/C-mqINvpBXkibO7Tl8VNg0iuufoXlpqEdij4kPkpQmo
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: c132d929-fa62-4271-803e-b823be07b914
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 0%

---

# パーソナライズされたオファーのリスト {#list-personalized-offers}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


パーソナライズされたオファーとは、適格性ルールと制約にもとづいてカスタマイズ可能なマーケティングメッセージです。

[!DNL Offer Library] APIに対して1回のGET リクエストを実行すると、すべてのパーソナライズされたオファーのリストを表示できます。

**API形式**

```http
GET /{ENDPOINT_PATH}/offers?offer-type=personalized&{QUERY_PARAMS}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | 結果をフィルタリングするオプションのクエリパラメーター。 | `limit=2` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offers?offer-type=personalized&limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリパラメーターの使用 {#using-query-parameters}

クエリパラメーターを使用すると、リソースのリスト時に結果をページ化およびフィルタリングできます。

### ページング {#paging}

ページングの最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルター： <ul><li>プロパティはAND操作でグループ化されます。</li><li>パラメーターは、次のように繰り返すことができます。property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...]、property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...]</li><li>プロパティ式の形式は`[ !]field[op]value`で、正規表現をサポートする`[==,!=,<=,>=,<,>,~]`の`op`です。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。 名前の前に – を追加すると（orderby=-name）、項目が名前で降順に並べ替えられます（Z-A）。 パス式は、ドット区切りのパスの形式です。 このパラメーターは次のように繰り返すことができます。`orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | 返されるプレースメントの数を制限します。 | `limit=5` |

**応答**

応答が成功すると、現在のパーソナライズされたオファーと、アクセス可能なオファーのリストが返されます。

```json
{
    "results": [
        {
            "created": "2023-05-15T14:35:16.781+00:00",
            "modified": "2023-05-15T14:38:26.691+00:00",
            "etag": 2,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.15"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "personalizedOffer1234",
            "name": "Test personalized offer with frequency constraint",
            "status": "draft",
            "representations": [
                {
                    "channel": "https://ns.adobe.com/xdm/channel-types/web",
                    "placement": "offerPlacement1234",
                    "components": [
                        {
                            "type": "html",
                            "format": "text/html",
                            "language": [
                                "en-us"
                            ],
                            "content": "Hello You qualify for our Discount of 60%"
                        }
                    ]
                }
            ],
            "selectionConstraint": {
                "startDate": "2022-07-27T05:00:00.000+00:00",
                "endDate": "2023-07-29T05:00:00.000+00:00",
                "profileConstraintType": "none"
            },
            "rank": {
                "priority": 0
            },
            "cappingConstraint": {},
            "frequencyCappingConstraints": [
                {
                    "enabled": false,
                    "limit": 1,
                    "startDate": "2023-05-15T14:25:49.622+00:00",
                    "endDate": "2023-05-25T14:25:49.622+00:00",
                    "scope": "global",
                    "entity": "offer",
                    "repeat": {
                        "enabled": false,
                        "unit": "month",
                        "unitCount": 1
                    }
                }
            ]
        }
    ],
    "count": 1,
    "total": 1,
    "_links": {
        "self": {
            "href": "/offers?offer-type=personalized&href={SELF_HREF}",
            "type": "application/json"
        }
    }
}
```

複数のパーソナライズされたオファーが応答に含まれていない場合は、ページ分割を実行します。

**応答**

```json
{
    "results": [...],
    "count": 2,
    "total": 43,
    "_links": {
        "self": {
        "href": "/offers?orderby=-modified&limit=2&offer-type=PERSONALIZED",
        "type": "application/json"
        },
        "next": {
        "href": "/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED",
        "type": "application/json"
        }
    }
    }
```

| 指標 | 効果 |
|---------|-------------|
| `total` | パーソナライズされたオファーの数。 |
| `count` | この応答で返されるオファーの数。 |

`/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED`など`_links.next.href`からエンドポイントを取得し、APIに追加します。

**API形式**

```http
GET /{ENDPOINT_PATH}/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED
```

```json
{
    "results": [...],
    "count": 2,
    "total": 43,
    "_links": {
        "self": {...},
        "next": {
        "href": "/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED",
        "type": "application/json"
        }
    }
}
```

同様に、最初のページにアクセスしておらず、パーソナライズされたオファーの前のページを取得する必要がある場合は、`_links.prev`から`href`値を使用します。 次の例に示すように、URLにリクエストを実行して、以前の結果セットを取得します。

**応答**

```json
{
    "results": [...],
    "count": 2,
    "total": 43,
    "_links": {
        "self": {...},
        "next": {...},
        "prev": {
        "href": "/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED",
        "type": "application/json"
        }
    }
}
```

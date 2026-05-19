---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定のリスト
description: 決定には、オファーの選択に役立つロジックが含まれます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 123ed057-e15f-4110-9fc6-df0e9cb5b038
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/w7cNTwAv0pEDx5Z-KgGl4fCYFhlToIhzgajla6YedQ0
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: c132d929-fa62-4271-803e-b823be07b914
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 0%

---

# 決定のリスト {#list-decisions}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


決定には、オファーの選択に役立つロジックが含まれます。

[!DNL Offer Library] APIに対して1回のGET リクエストを実行すると、すべての決定のリストを表示できます。

**API形式**

```http
GET /{ENDPOINT_PATH}/offer-decisions?{QUERY_PARAMS}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | 結果をフィルタリングするオプションのクエリパラメーター。 | `limit=2` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-decisions?limit=2' \
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
| `limit` | 返されるエンティティの数を制限します。 | `limit=5` |


**応答**

応答が成功すると、アクセス可能な決定のリストが返されます。

```json
{
    "results": [
        {
            "created": "2022-07-05T09:02:02.835+00:00",
            "modified": "2022-08-16T21:40:58.573+00:00",
            "etag": 12,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.8"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerDecision1234",
            "name": "Test Decision One",
            "status": "live",
            "startDate": "2022-05-18T00:09:57.706+00:00",
            "endDate": "2032-08-13T21:40:58.235+00:00",
            "fallback": "fallbackOffer1234",
            "criteria": [
                {
                    "placements": [
                        "offerPlacement1234",
                        "offerPlacement5678"
                    ],
                    "rank": {
                        "priority": 0,
                        "order": {
                            "orderEvaluationType": "ranking-strategy",
                            "rankingStrategy": "123456789123"
                        }
                    },
                    "profileConstraint": {
                        "profileConstraintType": "none"
                    },
                    "optionSelection": {
                        "filter": "offerCollection1234"
                    }
                }
            ]
        },
        {
            "created": "2022-09-05T14:12:13.773+00:00",
            "modified": "2022-09-05T14:12:13.773+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.8"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerDecision5678",
            "name": "Test Decision Two",
            "status": "live",
            "startDate": "2022-08-31T21:00:00.000+00:00",
            "endDate": "2023-02-03T22:00:00.000+00:00",
            "fallback": "fallbackOffer5678",
            "criteria": [
                {
                    "placements": [
                        "offerPlacement1234"
                    ],
                    "rank": {
                        "priority": 2
                    },
                    "optionSelection": {
                        "filter": "offerCollection5678"
                    }
                },
                {
                    "placements": [
                        "offerPlacement5678"
                    ],
                    "rank": {
                        "priority": 1
                    },
                    "optionSelection": {
                        "filter": "offerCollection1234"
                    }
                }          
            ]
        }
    ],
    "count": 2,
    "total": 21,
    "_links": {
        "self": {
            "href": "/offer-decisions?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/offer-decisions?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```

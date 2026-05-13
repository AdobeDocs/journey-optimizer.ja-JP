---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクションのリスト
description: コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: f27ffbe0-a61a-428a-bc37-db6b56e38a83
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/y9aw8mixba3Vc2CW-3WYrDvkB3TrX8ynmbVDBjGlzEI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 220
ht-degree: 0%

---

# コレクションのリスト {#list-collections}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。

[!DNL Offer Library] APIに対して1回のGET リクエストを実行すると、すべてのコレクションのリストを表示できます。

**API形式**

```http
GET /{ENDPOINT_PATH}/offer-collections?{QUERY_PARAMS}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | 結果をフィルタリングするオプションのクエリパラメーター。 | `limit=2` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-collections?limit=2' \
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
| `property` | オプションのプロパティフィルター： <ul><li>プロパティはAND操作でグループ化されます。</li><li>パラメーターは、次のように繰り返すことができます。property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...]、property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...]</li><li>プロパティ式の形式は`[!]field[op]value`で、正規表現をサポートする`[==,!=,<=,>=,<,>,~]`の`op`です。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。 名前の前に – を追加すると（orderby=-name）、項目が名前で降順に並べ替えられます（Z-A）。 パス式は、ドット区切りのパスの形式です。 このパラメーターは次のように繰り返すことができます。`orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | 返されるエンティティの数を制限します。 | `limit=5` |

**応答**

応答が成功すると、アクセス権のあるコンテナ内に存在するコレクションのリストが返されます。

```json
{
    "results": [
        {
            "created": "2022-09-16T18:59:23.063+00:00",
            "modified": "2022-09-16T18:59:23.063+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.4"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerCollection1234",
            "name": "Test Collection with tags",
            "filterType": "any-tags",
            "ids": [
                "tag1234"
            ],
            "labels": [
                "core/C5",
                "custom/myLabel"
            ]
        },
        {
            "created": "2023-05-15T12:50:49.887+00:00",
            "modified": "2023-05-15T12:50:49.887+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.4"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerCollection5678",
            "name": "Test Collection with offers",
            "filterType": "offers",
            "ids": [
                "personalizedOffer1234",
                "personalizedOffer5678"
            ]
        }
    ],
    "count": 2,
    "total": 9,
    "_links": {
        "self": {
            "href": "/offer-collections?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/offer-collections?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```

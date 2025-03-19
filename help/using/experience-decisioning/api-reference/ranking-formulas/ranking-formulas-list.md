---
title: ランキング式のリスト
description: ランキング式を使用すると、項目のランク付けに使用されるスコアリングの関数を定義できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 8b07be08-b37c-4535-82d8-3304340cbcad
source-git-commit: 6378c4a8cb911088c685166b9c1b29a1773d47b7
workflow-type: ht
source-wordcount: '191'
ht-degree: 100%

---

# ランキング式のリスト {#list-ranking-formulas}

ランキング式は、ランク付け方法を定義するランキング関数で構成されています。

Offer Library API に対して GET リクエストを 1 回実行することで、すべてのランキング式のリストを表示できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/ranking-formulas?{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | exdFunction。 | `property=exdFunction%3D%3Dtrue` |

## クエリパラメーターの使用 {#using-query-parameters}

リソースを一覧表示する際に、クエリパラメーターを使用して結果をページングおよびフィルタリングできます。

### ページング {#paging}

ページングに最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルターは次のとおりです。 <ul><li>プロパティは AND 演算でグループ化されます。</li><li>パラメーターは、property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...] または property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...] のように繰り返すことができます。</li><li>プロパティ式は `[!]field[op]value` の形式を使用（`[==,!=,<=,>=,<,>,~]` に `op`）し、正規表現をサポートします。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。名前の前に - を追加すると（orderby=-name）、名前の降順（Z ～ A）で項目が並べ替えられます。パス式は、ドット区切りのパスの形式です。このパラメーターは、`orderby=field1[,-fields2,field3,...]` のように繰り返すことができます。 | `orderby=id`、`-name` |
| `limit` | 返されるエンティティの数を制限します。 | `limit=5` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/ranking-formulas?property=exdFunction%3D%3Dtrue&limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、自身がアクセス権を持っているランキング式のリストが返されます。

```json
{
    "results": [
        {
            "created": "2024-08-08T23:45:15.380Z",
            "modified": "2024-10-22T18:15:05.909Z",
            "etag": 36,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/ranking-function"
            ],
            "createdBy": "71486D7B5F4011980A494030@AdobeID",
            "lastModifiedBy": "71486D7B5F4011980A494030@AdobeID",
            "id": "dps:ranking-function:1947f5372cc4ed74",
            "name": "[Do not delete] - Cypress e2e - edit",
            "description": "some description",
            "returnType": {
                "type": "INTEGER"
            },
            "exdFunction": true,
            "expression": {
                "type": "PQL",
                "format": "pql/text",
                "value": "42 = 11"
            }
        },
        {
            "created": "2024-05-03T13:06:22.361Z",
            "modified": "2024-10-18T22:47:35.396Z",
            "etag": 2,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/ranking-function;version=0.3"
            ],
            "createdBy": "FD62391F5B44DF970A494124@AdobeID",
            "lastModifiedBy": "6F8A6FF05F4011C40A494005@AdobeID",
            "id": "xcore:ranking-function:18ca80c5b15c5e11",
            "name": "doc test exd",
            "description": "",
            "returnType": {
                "type": "INTEGER"
            },
            "exdFunction": true,
            "expression": {
                "type": "PQL",
                "format": "pql/text",
                "value": "false"
            }
        }
    ],
    "count": 2,
    "total": 50,
    "_links": {
        "self": {
            "href": "/ranking-formulas?orderby=-modified&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/ranking-formulas?orderby=-modified&limit=2&start=2024-10-18T22:22:35.048Z",
            "type": "application/json"
        }
    }
}
```

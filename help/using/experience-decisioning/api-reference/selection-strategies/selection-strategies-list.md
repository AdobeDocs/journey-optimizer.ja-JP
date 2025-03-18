---
title: 選択戦略のリスト
description: 選択戦略は、オファーを決定するための制約とランキング方法に関連付けられたコレクションで構成されます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: be0f683d-1d39-47f6-b565-1cc7ee06ee71
source-git-commit: 7bfbb88c2817d18b7897a7fe1657ebf11be6eb58
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 100%

---

# 選択戦略のリスト {#list-selection-strategies}

選択戦略は、実施要件の制約およびランキング方法に関連付けられたコレクションで構成され、[決定ポリシー](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/experience-decisioning/create-decision)が選択されている場合に表示されるオファーを決定します。

オファーライブラリ API に対して単一の GET リクエストを実行することで、すべての選択戦略のリストを表示できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/selection-strategies?{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | 結果をフィルタリングする条件となるクエリパラメーター（オプション）。 | `limit=2` |

## クエリパラメーターの使用 {#using-query-parameters}

リソースのリストを表示する際に、クエリパラメーターを使用してページを作成し、結果をフィルターできます。

### ページング {#paging}

ページングに最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルターは次のとおりです。 <ul><li>プロパティは AND 演算でグループ化されます。</li><li>パラメーターは、property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...] または property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...] のように繰り返すことができます。</li><li>プロパティ式は `[!]field[op]value` の形式を使用（`[==,!=,<=,>=,<,>,~]` に `op`）し、正規表現をサポートします。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。名前の前に - を追加すると（orderby=-name）、名前の降順（Z ～ A）で項目が並べ替えられます。パス式は、ドット区切りのパスの形式です。このパラメーターは、`orderby=field1[,-fields2,field3,...]` のように繰り返すことができます。 | `orderby=id`、`-name` |
| `limit` | 返されるエンティティの数を制限します。 | `limit=5` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/selection-strategies?limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、自身がアクセス権を持っている選択戦略のリストが返されます。

```json
{
    "results": [
        {
            "created": "2024-02-08T03:01:50.924Z",
            "modified": "2024-02-16T23:03:03.019Z",
            "etag": 4,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/selection-strategy;version=0.2"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "selectionStrategy1234",
            "name": "Selection Strategy One",
            "description": "Selection Strategy",
            "rank": {
                "priority": 1,
                "order": {
                    "orderEvaluationType": "static"
                }
            },
            "profileConstraint": {
                "profileConstraintType": "eligibilityRule",
                "eligibilityRule": "offerRule1234"
            },
            "optionSelection": {
                "filter": "itemCollection1234",
            }
        },
        {
            "created": "2024-01-11T11:12:06.775Z",
            "modified": "2024-01-15T14:36:02.994Z",
            "etag": 2,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/selection-strategy;version=0.1"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "selectionStrategy5678",
            "name": "Selection Strategy Two",
            "rank": {
                "priority": 1,
                "order": {
                    "orderEvaluationType": "scoringFunction",
                    "function": "rankingFormula5678"
                }
            },
            "profileConstraint": {
                "profileConstraintType": "none"
            "optionSelection": {
                "filter": "itemCollection5678"
            }
        }
    ],
    "count": 2,
    "total": 166,
    "_links": {
        "self": {
            "href": "/selection-strategies?orderby=-modified&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/selection-strategies?orderby=-modified&limit=2&start=2024-06-04T23:37:33.980Z",
            "type": "application/json"
        }
    }
}
```

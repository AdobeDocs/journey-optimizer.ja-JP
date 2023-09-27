---
title: コレクション修飾子のリスト
description: コレクション修飾子を使用すると、オファーをより適切に整理し並べ替えることができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 8cee44ed-5569-416c-b463-e75fb20d4c9c
source-git-commit: 57671f18d216209fb738fed34bc6b03051893b9f
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 54%

---

# コレクション修飾子のリスト {#list-tags}

コレクション修飾子（旧称「タグ」）を使用すると、オファーをより適切に整理し並べ替えることができます。例えば、ブラックフライデーのオファーに「ブラックフライデー」コレクション修飾子のラベルを付けることができます。オファーライブラリの検索機能を使用すると、そのコレクション修飾子を持つすべてのオファーを簡単に見つけることができます。

また、コレクション修飾子を使用して、オファーをコレクションにグループ化することもできます。詳しくは、[コレクションの作成](../../../offer-library/creating-collections.md)のチュートリアルを参照してください。

すべての収集修飾子のリストを表示するには、 [!DNL Offer Library] API.

**API 形式**

```http
GET /{ENDPOINT_PATH}/tags?{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/tags?limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリパラメーターの使用 {#using-query-parameters}

リソースのリストを表示する際に、クエリパラメーターを使用してページを作成し、結果をフィルターできます。

### ページング {#paging}

ページングに最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルターは次のとおりです。 <ul><li>プロパティは AND 演算でグループ化されます。</li><li>次のようにパラメーターを繰り返すことができます。 property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...] またはプロパティ={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...]</li><li>プロパティの式は形式です `[!]field[op]value`、を `op` in `[==,!=,<=,>=,<,>,~]`、正規表現をサポートします。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。名前の前に — を追加すると (orderby=-name)、降順 (Z ～ A) で項目が名前で並べ替えられます。 パス式は、ドット区切りのパスの形式です。 このパラメーターは、次のように繰り返すことができます。 `orderby=field1[,-fields2,field3,...]` | `orderby=id`、`-name` |
| `limit` | 返されるエンティティの数を制限します。 | `limit=5` |

**応答**

正常な応答は、存在するコレクション修飾子のリストを返します。

```json
{
                "created": "2022-09-16T19:00:02.070+00:00",
            "modified": "2022-09-16T19:00:02.070+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "tag1234",
            "name": "Sneakers"
        },
        {
            "created": "2022-09-16T19:55:02.168+00:00",
            "modified": "2022-09-16T19:55:02.168+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "tag5678",
            "name": "Black Friday"
        }
    ],
    "count": 2,
    "total": 5,
    "_links": {
        "self": {
            "href": "/tags?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/tags?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```

---
title: プレースメントのリスト
description: プレースメントは、オファーの表示に使用するコンテナです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 36030ffe-eb7a-4487-914d-84ccb0a6bf6e
source-git-commit: f7d2666c88dd2cfb1237fbab34c1ec3b141260b4
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 51%

---

# プレースメントのリスト {#list-placements}

プレースメントは、オファーの表示に使用するコンテナです。プレースメントを使用すると、メッセージ内の適切な場所に適切なオファーコンテンツが表示されます。オファーにコンテンツを追加すると、そのコンテンツを表示できるプレースメントを選択するように求められます。

すべての配置のリストを表示するには、 [!DNL Offer Library] API.

**API 形式**

```http
GET /{ENDPOINT_PATH}/placements?{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

## クエリパラメーターの使用 {#using-query-parameters}

リソースのリストを表示する際に、クエリパラメーターを使用してページを作成し、結果をフィルターできます。

### ページング {#paging}

ページングに最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルターは次のとおりです。 <ul><li>プロパティは AND 演算でグループ化されます。</li><li>次のようにパラメーターを繰り返すことができます。 property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...] またはプロパティ={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...]</li><li>プロパティの式は形式です `[!]field[op]value`、を `op` in `[==,!=,<=,>=,<,>,~]`、正規表現をサポートします。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。名前の前に — を追加すると (orderby=-name)、降順 (Z ～ A) で項目が名前で並べ替えられます。 パス式は、ドット区切りのパスの形式です。 このパラメーターは、次のように繰り返すことができます。 `orderby=field1[,-fields2,field3,...]` | `orderby=id`、`-name` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/placements?limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答は、存在する配置とアクセス可能な配置のリストを返します。

```json
{
    "results": [
        {
            "created": "2023-05-15T11:22:50.031+00:00",
            "modified": "2023-05-15T11:22:50.031+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.5"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerPlacement5678",
            "name": "Placement one",
            "description": "Placement description",
            "componentType": "html",
            "channel": "https://ns.adobe.com/xdm/channel-types/web",
            "itemCount": 1,
            "allowDuplicatePlacements": false,
            "returnContent": false,
            "returnMetaData": {
                "decisionName": true,
                "offerName": true,
                "offerAttributes": true,
                "offerPriority": true,
                "placementName": true,
                "channelType": true,
                "contentType": true
            }
        },
        {
            "created": "2023-05-19T08:29:15.875+00:00",
            "modified": "2023-05-19T08:29:15.875+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.5"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerPlacement1234",
            "name": "Placement two",
            "description": "Placement description",
            "componentType": "html",
            "channel": "https://ns.adobe.com/xdm/channel-types/email",
            "itemCount": 1,
            "allowDuplicatePlacements": false,
            "returnContent": false,
            "returnMetaData": {
                "decisionName": true,
                "offerName": true,
                "offerAttributes": true,
                "offerPriority": true,
                "placementName": true,
                "channelType": true,
                "contentType": true
            }
        }
    ],
    "count": 2,
    "total": 4,
    "_links": {
        "self": {
            "href": "/placements?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/placements?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```

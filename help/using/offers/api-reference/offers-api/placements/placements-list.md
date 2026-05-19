---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: プレースメントのリスト
description: プレースメントは、オファーを表示するために使用されるコンテナです。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 36030ffe-eb7a-4487-914d-84ccb0a6bf6e
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/GOCFmBszGmJqwIyQKXVQIlTEBXeKxp3qvTgyI89pw8Q
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 0%

---

# プレースメントのリスト {#list-placements}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


プレースメントは、オファーを表示するために使用されるコンテナです。 プレースメントは、メッセージ内の適切な場所に適切なオファーコンテンツを表示するのに役立ちます。 オファーにコンテンツを追加すると、そのコンテンツを表示できるプレースメントを選択するように求められます。

[!DNL Offer Library] APIに対して1回のGET リクエストを実行すると、すべてのプレースメントのリストを表示できます。

**API形式**

```http
GET /{ENDPOINT_PATH}/placements?{QUERY_PARAMS}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |

## クエリパラメーターの使用 {#using-query-parameters}

クエリパラメーターを使用すると、リソースのリスト時に結果をページ化およびフィルタリングできます。

### ページング {#paging}

ページングの最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルター： <ul><li>プロパティはAND操作でグループ化されます。</li><li>パラメーターは、次のように繰り返すことができます。property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...]、property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...]</li><li>プロパティ式の形式は`[ !]field[op]value`で、正規表現をサポートする`[==,!=,<=,>=,<,>,~]`の`op`です。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。 名前の前に – を追加すると（orderby=-name）、項目が名前で降順に並べ替えられます（Z-A）。 パス式は、ドット区切りのパスの形式です。 このパラメーターは次のように繰り返すことができます。`orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |

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

応答が成功すると、存在するプレースメントとアクセス可能なプレースメントのリストが返されます。

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

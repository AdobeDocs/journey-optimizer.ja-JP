---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定ルールの一覧表示
description: 決定ルールは、パーソナライズされたオファーに追加され、適格性を判断するためにプロファイルに適用される制約です。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: c4c3e415-bc57-45db-b27f-4a5e9fc1f02c
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/OdxUlowpYo0O3wR-ZiTMn6wPNG-RlRoMmBAUttTtkH8
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
source-wordcount: 218
ht-degree: 0%

---

# 決定ルールの一覧表示 {#list-decision-rules}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


決定ルールは、パーソナライズされたオファーに追加され、適格性を判断するためにプロファイルに適用される制約です。 コンテナ内の既存の意思決定ルールのリストを表示するには、[!DNL Offer Library] APIに対して1回のGET リクエストを実行します。

**API形式**

```http
GET /{ENDPOINT_PATH}/offer-rules?{QUERY_PARAMS}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | 結果をフィルタリングするオプションのクエリパラメーター。 | `limit=2` |

## クエリパラメーターの使用 {#using-query-parameters}

クエリパラメーターを使用すると、リソースのリスト時に結果をページ化およびフィルタリングできます。

### ページング {#paging}

ページングの最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `property` | オプションのプロパティフィルター： <ul><li>プロパティはAND操作でグループ化されます。</li><li>パラメーターは、次のように繰り返すことができます。property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}...]、property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}...]</li><li>プロパティ式の形式は`[ !]field[op]value`で、正規表現をサポートする`[==,!=,<=,>=,<,>,~]`の`op`です。</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。 名前の前に – を追加すると（orderby=-name）、項目が名前で降順に並べ替えられます（Z-A）。 パス式は、ドット区切りのパスの形式です。 このパラメーターは次のように繰り返すことができます。`orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | 返されるエンティティの数を制限します。 | `limit=5` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-rules?limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、アクセス権のある決定ルールのリストが返されます。

```json
{
     "results": [
        {
            "created": "2022-09-16T18:59:53.651+00:00",
            "modified": "2022-09-16T18:59:53.651+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerRule1234",
            "name": "Californians with one or more purchases greater than $1000",
            "condition": {
                "type": "PQL",
                "format": "pql/text",
                "value": "homeAddress.stateProvince.equals(\"CA\", false) and (select var1 from xEvent where var1.eventType.equals(\"purchase\", true) and (var1.commerce.order.priceTotal = 1000.0 and var1.commerce.order.currencyCode.equals(\"USD\", false)))"
                 }
        },
        {
            "created": "2023-03-06T15:11:42.178+00:00",
            "modified": "2023-03-06T15:11:42.178+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerRule5678",
            "name": "People born after 1981",
            "description": "Persons with the birth date after 1981",
            "condition": {
                "type": "PQL",
                "format": "pql/text",
                "value": "person.birthDate occurs after date(1981, 1, 1)"
            }
        }
    ],
    "count": 2,
    "total": 25,
    "_links": {
        "self": {
            "href": "/offer-rules?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/offer-rules?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```

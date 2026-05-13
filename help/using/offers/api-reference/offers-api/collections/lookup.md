---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクションを検索
description: コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 723daab2-5590-4c44-acb6-93a77f2e7877
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/FhWiKNwWUr3amFyD3EoZvq1QTJh-tt5tK6qYYzNplTY
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 125
ht-degree: 0%

---

# コレクションを検索 {#look-up-collection}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。

コレクション `id`をリクエストパスに含む[!DNL Offer Library] APIにGET リクエストを行うことで、特定のコレクションを検索できます。

**API形式**

```http
GET /{ENDPOINT_PATH}/offer-collections/{ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 検索するエンティティのID。 | `offerCollection1234` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-collections/offerCollection1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、一意のコレクション `id`に関する情報を含むコレクションの詳細が返されます。

```json
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
}
```

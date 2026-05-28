---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定ルールの検索
description: 決定ルールは、パーソナライズされたオファーに追加される制約で、実施要件を決定するためにプロファイルに適用されます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 54368710-1021-43c0-87b7-5176cc6c72f7
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/cAYaAHZFXk7PYPfXIbeO-GQzCim6LBPtFyp1qBSEink
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
  - id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
  - id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 115
ht-degree: 100%

---

# 決定ルールの検索 {#lookup-decision-rule}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


特定の決定ルールを検索するには、リクエストパスに決定ルール `id` を含む GET リクエストを [!DNL Offer Library] API に対して実行します。

**API 形式**

```http
GET /{ENDPOINT_PATH}/offer-rules/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 参照するエンティティの ID。 | `offerRule1234` |

**リクエスト**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-rules/offerRule1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、一意の決定ルール `id` に関する情報など、検索した特定の決定ルールの詳細が返されます。

```json
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
}
```

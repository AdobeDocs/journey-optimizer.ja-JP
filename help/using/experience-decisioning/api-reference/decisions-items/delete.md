---
title: 決定項目の削除
description: 決定項目は、コレクションとカタログに作成および整理できるマーケティングオファーです。
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 0fd608e0-df71-4e2d-8304-d7d5561c7c7a
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/OkPIse7NFATcyTdTT0pzNhjPMenbrvigSG2lSRatb-M
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 100%

---

# 決定項目の削除 {#delete-decision-item}

決定項目を削除するには、削除する決定項目の ID を使用して、オファーライブラリ API に対する DELETE リクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offer-items/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 削除するエンティティの ID。 | `offerItem1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-items/offerItem1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-schema-id: {SCHEMA_ID}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

決定項目に対して参照（GET）リクエストを試行することで、削除を確認できます。 決定項目が削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

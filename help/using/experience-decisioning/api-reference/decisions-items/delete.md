---
title: 決定項目の削除
description: 決定項目は、コレクションとカタログに作成および整理できるマーケティングオファーです。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: c555e6a6d88f43d7c29e27060d464b8fd21aed96
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 27%

---


# 決定項目の削除 {#delete-decision-item}

場合によっては、決定項目を削除（DELETE）する必要があります。 削除するには、削除するDELETE項目の ID を使用して、オファーライブラリ API に対して決定リクエストを実行します。

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

決定項目に対して検索（GET）リクエストを実行することで、削除を確認できます。 決定項目が削除されているので、HTTP ステータス 404 （見つかりません）が返されます。

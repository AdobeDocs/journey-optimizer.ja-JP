---
title: 決定項目の削除
description: 決定項目は、コレクションとカタログに作成および整理できるマーケティングオファーです。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: eb89bc5205d98a67cd0bb42bebbd9429786e33e7
workflow-type: ht
source-wordcount: '112'
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

決定項目に対して参照（GET）リクエストを試行することで、削除を確認できます。決定項目が削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

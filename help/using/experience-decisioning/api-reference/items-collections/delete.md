---
title: アイテム コレクションの削除
description: コレクションを使用すると、環境設定に従って決定項目を分類およびグループ化できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: dc47e2835379fbb2afb768beea6e4a1596f70ee9
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 27%

---


# アイテム コレクションの削除 {#delete-decision-item}

場合によっては、項目のコレクションを削除（DELETE）する必要があります。 削除するには、削除する項目コレクションの ID を使用して、オファーライブラリ API に対してDELETEリクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/item-collections/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 削除するエンティティの ID。 | `itemCollections1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/item-collections/itemCollections1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

削除を確認するには、項目コレクションに対して検索（GET）リクエストを試みます。 項目コレクションが削除されているので、HTTP ステータス 404 （見つかりません）が返されます。

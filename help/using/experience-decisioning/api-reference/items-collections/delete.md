---
title: 項目コレクションの削除
description: グループの決定をコレクションに分類する方法について説明します。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: eb89bc5205d98a67cd0bb42bebbd9429786e33e7
workflow-type: ht
source-wordcount: '116'
ht-degree: 100%

---


# 項目コレクションの削除 {#delete-decision-item}

場合によっては、項目コレクションを削除（DELETE）する必要があります。これを行うには、削除する項目コレクションの ID を使用して、オファーライブラリ API に対して DELETE リクエストを実行します。

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

項目コレクションに対して参照（GET）リクエストを実行することで、削除を確認できます。項目コレクションが削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

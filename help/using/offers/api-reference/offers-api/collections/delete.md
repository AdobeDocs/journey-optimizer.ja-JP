---
title: コレクションの削除
description: コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: 2eaa0092-2436-4679-83f1-7530ab4a858f
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# コレクションの削除 {#delete-collection}

場合によっては、コレクションを削除（DELETE）する必要があります。これは、削除するコレクションの `id` を使用して [!DNL Offer Library] API に対して DELETE リクエストを実行することで行います。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offer-collections/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 削除するエンティティの ID。 | `offerCollection1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-collections/offerCollection1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' 
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

コレクションに対して検索（GET）リクエストを実行することで、削除を確認できます。コレクションが削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

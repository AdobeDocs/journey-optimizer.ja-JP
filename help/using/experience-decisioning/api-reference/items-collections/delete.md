---
title: 項目コレクションの削除
description: グループの決定をコレクションに分類する方法について説明します。
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 7290c857-cbc7-4197-ae13-430adcf1649b
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/JpZKEp0CnLg30ExvgHamm6dknBlr9vB1QlAlwMNAZKI
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 116
ht-degree: 100%

---

# 項目コレクションの削除 {#delete-decision-item}

場合によっては、項目コレクションを削除（DELETE）する必要があります。 これを行うには、削除する項目コレクションの ID を使用して、オファーライブラリ API に対して DELETE リクエストを実行します。

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

項目コレクションに対して参照（GET）リクエストを実行することで、削除を確認できます。 項目コレクションが削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

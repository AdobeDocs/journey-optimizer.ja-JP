---
title: ランキング式の削除
description: ランキング式を使用すると、項目のランク付けに使用されるスコアリングの関数を定義できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: 4ea50481-b1b9-4e0c-ad4e-c4139891bfdf
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 100%

---

# ランキング式の削除 {#delete-selection-strategy}

場合によっては、ランキング式を削除（DELETE）する必要があります。これを行うには、削除するランキング式の ID を使用して、オファーライブラリ API に対して DELETE リクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/ranking-formulas/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 削除するエンティティの ID。 | `rankingFormula1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/ranking-formulas/rankingFormula1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

ランキング式に対して参照（GET）リクエストを実行することで、削除を確認できます。ランキング式が削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

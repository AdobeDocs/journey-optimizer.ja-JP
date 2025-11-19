---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定の削除
description: 決定には、オファーの選択を通知するロジックが含まれています。
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 1eb19ff1-b210-4891-ab41-5488e2635527
version: Journey Orchestration
source-git-commit: d6a9a8a392f0492aa6e4f059198ce77b6b2cd962
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---

# 決定の削除 {#delete-decision}

場合によっては、決定ルールを削除（DELETE）する必要があります。これを行うには、削除する決定の `id` を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offer-decisions/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 削除するエンティティの ID。 | `offerDecision1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-decisions/offerDecision1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

決定に対して検索（GET）リクエストを試行することで、削除を確認できます。決定が削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

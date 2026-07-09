---
title: 実施要件ルールの削除
description: 実施要件ルールを使用すると、プロファイル属性やオーディエンスなど、ターゲットにする項目に基づいて実施要件を満たす候補を定義できます。
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 19baf888-23b7-46de-9d3c-9a0fa8ab2297
version: Journey Orchestration
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: 93712df16d9a3df94fd31cb8bc4da9762691d1ef
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 100%

---

# 実施要件ルールの削除 {#delete-eligibility-rule}

場合によっては、実施要件ルールを削除（DELETE）する必要があります。 これを行うには、削除する実施要件ルールの ID を使用して、オファーライブラリ API に対して DELETE リクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offer-rules/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 削除するエンティティの ID。 | `rule1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-rules/rule1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

ルールに対して参照（GET）リクエストを実行することで、削除を確認できます。 ルールが削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

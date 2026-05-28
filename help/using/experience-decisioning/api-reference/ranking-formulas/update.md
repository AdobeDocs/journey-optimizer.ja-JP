---
title: ランキング式の更新
description: ランキング式を使用すると、項目のランク付けに使用されるスコアリングの関数を定義できます。
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 4ef1bfc2-e74f-4b44-b3b5-8a4f2fbd6438
version: Journey Orchestration
feature_v2:
  - id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
  - id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 157
ht-degree: 100%

---

# ランキング式の更新 {#update-ranking-formula}

オファーライブラリ API に対して PUT リクエストを実行することで、ランキング式を変更または更新できます。

使用可能な操作など、JSON PUT について詳しくは、[JSON PUT の公式ドキュメント](http://jsonpatch.com/)を参照してください。

**Accept ヘッダーと Content-Type ヘッダー**

リクエストヘッダーの Content-Type フィールドを構成する有効な値を次の表に示します。

| ヘッダー名 | 値 |
| --------- | ----------- |
| Content-Type | `application/json` |

**API 形式**

```http
PUT /{ENDPOINT_PATH}/ranking-formulas/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 更新するエンティティの ID。 | `rankingFormula1234` |

**リクエスト**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/ranking-formulas/rankingFormula1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{
    "name": "[UPDATED] Test Ranking Function DPS",
    "description": "Ranking  function description",
    "isPure": true,
    "exdFunction": true,
    "returnType": {
        "type": "integer"
    },
    "expression": {
        "type": "PQL",
        "format": "pql/text",
        "value": "if(offer.rank.priority.isNotNull(), offer.rank.priority, 0) * if(offer.tags.intersects(boosted.tags), 2, 1)"
    },
    "definedOn": {
        "offer": {
            "schema": {
                "altId": "_experience.offer-management.personalized-offer",
                "version": "0"
            }
        },
        "boosted": {
            "schema": {
                "altId": "_xdm.context.foo",
                "version": "0"
            }
        }
    }
}'
```

| パラメーター | 説明 |
| --------- | ----------- |
| `value` | パラメーターの更新に使用する新しい値。 |
| `path` | 更新するパラメーターのパス。 |
| `op` | 接続の更新に必要なアクションを定義するのに使用される操作呼び出し。 操作には、`add`、`replace`、`remove`、`copy` および `test` があります。 |

**応答**

正常な応答では、ID など、ランキング式の更新された詳細が返されます。

```json
{
    "etag": 2,
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "{ID}",
    "sandboxId": "{SANDBOX_ID}",
    "createdDate": "2023-05-31T15:09:11.771Z",
    "lastModifiedDate": "2023-05-31T15:09:11.771Z",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

---
title: ランキング式の削除
description: ランキング式を使用すると、項目のランク付けに使用されるスコアリングの関数を定義できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 19%

---

# ランキング式の削除 {#delete-selection-strategy}

ランキング式を（DELETE）削除する必要が生じる場合があります。 これをおこなうには、削除するランキング式の ID を使用してオファーライブラリ API に対してDELETE リクエストを実行します。

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

ランキング式に対して検索（GET）リクエストを試みることで、削除を確認できます。 ランキング式が削除されているので、HTTP ステータス 404 （見つかりません）が返されます。


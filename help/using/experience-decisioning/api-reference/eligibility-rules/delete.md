---
title: 実施要件ルールの削除
description: 実施要件ルールを使用すると、プロファイル属性やオーディエンスなど、ターゲットにしたい項目に基づいて実施要件を満たす候補を定義できます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 25%

---

# 実施要件ルールの削除 {#delete-eligibility-rule}

場合によっては、（DELETE）実施要件ルールを削除する必要があります。 削除するには、削除する実施要件ルールの ID を使用して、オファーライブラリ API に対してDELETE リクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/eligibility-rules/{ID}
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

ルールに対して検索（GET）リクエストを実行することで、削除を確認できます。 ルールが削除されているので、HTTP ステータス 404 （見つかりません）が返されます。

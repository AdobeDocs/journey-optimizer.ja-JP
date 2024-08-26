---
title: 選択戦略の削除
description: 選択戦略は、オファーを決定するための制約とランキング方法に関連付けられたコレクションで構成されます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: c555e6a6d88f43d7c29e27060d464b8fd21aed96
workflow-type: ht
source-wordcount: '121'
ht-degree: 100%

---


# 選択戦略の削除 {#delete-selection-strategy}

場合によっては、選択戦略を削除（DELETE）する必要があります。これを行うには、削除する選択戦略の ID を使用して、オファーライブラリ API に対して DELETE リクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/selection-strategies/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 削除するエンティティの ID。 | `selectionStrategy1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/selection-strategies/selectionStrategy1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

選択戦略に対して参照（GET）リクエストを実行することで、削除を確認できます。選択戦略が削除されたので、HTTP ステータス 404（見つかりません）が表示されます。

---
title: 選択戦略の削除
description: 選択戦略は、制約に関連付けられたコレクションと、オファーを決定するためのランキングメソッドで構成されます。
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: c555e6a6d88f43d7c29e27060d464b8fd21aed96
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 27%

---


# 選択戦略の削除 {#delete-selection-strategy}

場合によっては、選択方針を削除（DELETE）する必要があります。 これは、削除するセレクション戦略の ID を使用してオファーライブラリ API に対するDELETEリクエストを実行することで行います。

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

セレクトストラテジーに対して検索（GET）リクエストを試行することで、削除を確定できます。 選択戦略が削除されているので、HTTP ステータス 404 （見つかりません）が返されます。

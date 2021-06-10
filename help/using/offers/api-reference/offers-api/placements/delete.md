---
title: プレースメントの削除
description: プレースメントは、オファーの表示に使用するコンテナです。
source-git-commit: 4ff255b6b57823a1a4622dbc62b4b8886fd956a0
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---

# プレースメントの削除

場合によっては、プレースメントを削除（DELETE）する必要があります。テナントコンテナで作成したプレースメントのみを削除できます。これは、削除するプレースメントのインスタンス ID を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行することでおこないます。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | プレースメントが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するプレースメントのインスタンス ID。 | `9aa58fd0-13d7-11eb-928b-576735ea4db8` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/9aa58fd0-13d7-11eb-928b-576735ea4db8' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答** 

正常な応答の場合は、空白の本文とともに HTTP ステータス 202 （コンテンツなし）が返されます。

プレースメントに対して検索（GET）リクエストを実行することで、削除を確認できます。リクエストには Accept ヘッダーを含める必要がありますが、プレースメントがコンテナから削除されたので、HTTP ステータス 404（見つかりません）を受け取ります。

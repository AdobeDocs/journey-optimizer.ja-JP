---
title: プレースメントを削除
description: プレースメントは、オファーの表示に使用するコンテナです。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 944efb12-6745-4bb2-be52-293e23925350
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 26%

---

# プレースメントの削除 {#delete-placement}

場合によっては、プレースメントを取り除く（DELETEする）必要があります。 テナントコンテナで作成したプレースメントのみを削除できます。 これを行うには、にDELETEリクエストを実行します。 [!DNL Offer Library] 削除するプレースメントのインスタンス ID を使用する API。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | プレースメントが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するプレースメントのインスタンス ID。 | `9aa58fd0-13d7-11eb-928b-576735ea4db8` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/9aa58fd0-13d7-11eb-928b-576735ea4db8' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、空白の本文とともに HTTP ステータス 202 （コンテンツなし）が返されます。

プレースメントに対して検索（GET）リクエストを試みることで、削除を確認できます。 リクエストには Accept ヘッダーを含める必要がありますが、プレースメントがコンテナから削除されたので、HTTP ステータス 404 （見つかりません）を受け取ります。

---
title: コレクション修飾子の削除
description: コレクション修飾子を使用すると、オファーをより適切に整理し並べ替えることができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 335c1b80-f1f0-4fd0-add8-84b8cc5e2e00
source-git-commit: 54b92b19f2e3a6afa6557ffeff0d971a4c411510
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 35%

---

# コレクション修飾子の削除 {#delete-tag}

コレクション修飾子（旧称「タグ」）を削除（DELETE）する必要が生じる場合があります。 これは、 [!DNL Offer Library] 削除するコレクション修飾子の ID を使用する API。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/tags/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 削除するエンティティの ID。 | `tag1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/tags/tag1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答は、HTTP ステータス 200 と空白の本文を返します。

コレクション修飾子に対して検索 (GET) リクエストを試みると削除を確認できます。削除されたので、HTTP ステータス 404（見つかりません）を受け取る必要があります。
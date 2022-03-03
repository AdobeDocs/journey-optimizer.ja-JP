---
title: 決定の削除
description: 決定には、オファーの選択を通知するロジックが含まれています。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 1eb19ff1-b210-4891-ab41-5488e2635527
source-git-commit: 2d859a5dab19a419d424acefd17d254473c00818
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# 決定の削除 {#delete-decision}

場合によっては、決定ルールを削除（DELETE）する必要があります。テナントコンテナで作成した決定のみを削除できます。これは、削除するフォールバックオファーの $id を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行することでおこないます。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 決定のインスタンスID。 | `f88c9be0-1245-11eb-8622-b77b60702882` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/f88c9be0-1245-11eb-8622-b77b60702882' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、空白の本文とともに HTTP ステータス 202 （コンテンツなし）が返されます。

決定に対して検索（GET）リクエストを試行することで、削除を確認できます。リクエストには Accept ヘッダーを含める必要がありますが、決定がコンテナから削除されたので、HTTP ステータス 404（見つかりません）が返されます。

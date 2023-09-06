---
title: 決定ルールの削除
description: 決定ルールは、パーソナライズされたオファーに追加される制約で、実施要件を決定するためにプロファイルに適用されます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 52f4803b-9e9a-4ad0-ae24-de652006763d
source-git-commit: 3568e86015ee7b2ec59a7fa95e042449fb5a0693
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 35%

---

# 決定ルールの削除 {#delete-decision-rule}

場合によっては、決定ルールを削除（DELETE）する必要があります。これは、 [!DNL Offer Library] を使用した API `id` 削除する決定ルールの名前を指定します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offer-rules/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | 削除するエンティティの ID。 | `offerRule1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-rules/offerRule1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答は、HTTP ステータス 200 と空白の本文を返します。

決定ルールに対して検索 (GET) リクエストを試行すると、削除を確認できます。決定ルールは削除されたので、HTTP ステータス 404（見つかりません）を受け取る必要があります。

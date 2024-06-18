---
title: フォールバックオファーの削除
description: フォールバックオファーは、他のオファーの対象とならない顧客に送信されます。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 5c94842a-021c-4a3a-ad9c-ccc2af2c1526
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 90%

---


# フォールバックオファーの削除 {#delete-fallback-offer}

場合によっては、フォールバックオファーを削除（DELETE）する必要があります。 それには、削除するフォールバックオファーの ID を使用して、[!DNL Offer Library] API に対する DELETE リクエストを実行します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offers/{ID}?offer-type=fallback
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 削除するエンティティの ID。 | `fallbackOffer1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offers/fallbackOffer1234?offer-type=fallback' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

削除を確認するには、オファーに対する参照（GET）リクエストを試みます。フォールバックオファーが削除されているので、HTTP ステータス 404（見つかりません）が表示されるはずです。

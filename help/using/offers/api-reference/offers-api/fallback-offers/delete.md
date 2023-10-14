---
title: フォールバックオファーの削除
description: フォールバックオファーは、他のオファーの対象とならない顧客に送信されます。
feature: Offers, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 5c94842a-021c-4a3a-ad9c-ccc2af2c1526
source-git-commit: 3f96cc0037b5bcdb2ce94e2721b02ba13b3cff36
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 35%

---


# フォールバックオファーの削除 {#delete-fallback-offer}

場合によっては、フォールバックオファーを削除（DELETE）する必要があります。これは、 [!DNL Offer Library] 削除するフォールバックオファーの ID を使用する API。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offers/{ID}?offer-type=fallback
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
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

正常な応答は、HTTP ステータス 200 と空白の本文を返します。

フォールバックオファーが削除されたので、オファーに対して検索 (GET) リクエストを試みて削除を確認できます。また、HTTP ステータス 404（見つかりません）が表示されます。

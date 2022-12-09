---
title: フォールバックオファーの削除
description: 代替オファーが他の特典に適合しない場合は、お客様に送信されます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 5c94842a-021c-4a3a-ad9c-ccc2af2c1526
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# フォールバックオファーの削除 {#delete-fallback-offer}

場合によっては、フォールバックオファーの削除 (削除) が必要になることがあります。 削除できるのは、テナントコンテナに作成したフォールバックオファーのみです。 そのためには、削除するフォールバックオファーの $id を使用して、API に [!DNL Offer Library] 削除要求を行います。

**API フォーマット**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | フォールバックが提供されているコンテナーが格納されています。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | フォールバックオファーのインスタンス id。 | `b3966680-13ec-11eb-9c20-8323709cfc65` |

**要求**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/b3966680-13ec-11eb-9c20-8323709cfc65' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**対し**

応答が成功した場合は、HTTP 状態 202 (内容なし) と空白の本文が返されます。

フォールバックオファーにルックアップ (GET) 要求を実行すると、削除の確認を行うことができます。 この場合は、要求に Accept ヘッダーを含める必要がありますが、フォールバックオファーがコンテナから削除されたので、HTTP ステータス 404 (見つからない) が返されます。

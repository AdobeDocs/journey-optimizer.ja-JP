---
title: パーソナライズされた特典の削除
description: パーソナライズされたオファーは、適格性ルールと制約に基づいてカスタマイズ可能なマーケティングメッセージです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 52a5053d-3b94-47fd-a064-a20f9a595150
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# パーソナライズされたオファーの削除 {#delete-personalized-offer}

カスタマイズしたオファーリングは、削除する必要がある場合があります。 テナントコンテナに作成した個別のオファーのみが削除される場合があります。 これは、削除するパーソナライズされたオファーリングの $id を使用して、API に [!DNL Offer Library] 削除要求を実行することによって行われます。

**API フォーマット**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | パーソナライズされたキャンペーンが配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**要求**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0f4bc230-13df-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**対し**

応答が成功した場合は、HTTP 状態 202 (内容なし) と空白の本文が返されます。

このような場合は、パーソナライズされた申し出に対して lookup (GET) 要求することによって、削除を確認することができます。 要求に Accept ヘッダーを含める必要がありますが、個人用オファーがコンテナから削除されたので、HTTP ステータス 404 (見つかりません) が表示されます。

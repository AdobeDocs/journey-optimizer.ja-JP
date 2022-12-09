---
title: 決定の削除
description: 「決定」には、申し出を選択したことを示すロジックが含まれています。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 1eb19ff1-b210-4891-ab41-5488e2635527
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# 意思決定の削除 {#delete-decision}

場合によっては、決定を削除 (削除) することが必要な場合があります。 テナントコンテナに作成した意思決定のみが削除される場合があります。 そのためには、削除するフォールバックオファーの $id を使用して、API に [!DNL Offer Library] 削除要求を行います。

**API フォーマット**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 決定のインスタンス id です。 | `f88c9be0-1245-11eb-8622-b77b60702882` |

**要求**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/f88c9be0-1245-11eb-8622-b77b60702882' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**対し**

応答が成功した場合は、HTTP 状態 202 (内容なし) と空白の本文が返されます。

このような場合は、決定に対する lookup (GET) 要求を実行することによって、削除を確認することができます。 要求に Accept ヘッダーを含める必要がありますが、この決定がコンテナから削除されたので、HTTP ステータス 404 (見つかりません) が表示されます。

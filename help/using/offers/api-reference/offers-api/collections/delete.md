---
title: コレクションの削除
description: コレクションは、オファーのカテゴリなど、marketer によって定義されている事前に定義された条件に基づいて作成されたオファーのサブセットです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 2eaa0092-2436-4679-83f1-7530ab4a858f
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# コレクションの削除 {#delete-collection}

コレクションを削除 (削除) することが必要になる場合があります。 テナントコンテナに作成したコレクションだけが削除される場合があります。 これは、削除したいコレクションの $id を使用して、API に [!DNL Offer Library] 削除要求を実行することによって実行されます。

**API フォーマット**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクションが格納されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するコレクションのインスタンス id です。 | `0bf31c20-13f1-11eb-a752-e58fd7dc4cb3` |

**要求**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0bf31c20-13f1-11eb-a752-e58fd7dc4cb3' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**対し**

応答が成功した場合は、HTTP 状態 202 (内容なし) と空白の本文が返されます。

コレクションに対する lookup (GET) 要求を試みることによって、削除を確認することができます。 要求に Accept ヘッダーを含める必要がありますが、コレクションがコンテナから削除されたので、HTTP ステータス 404 (見つかりません) が表示されます。

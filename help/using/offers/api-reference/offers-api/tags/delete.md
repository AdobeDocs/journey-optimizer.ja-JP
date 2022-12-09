---
title: タグの削除
description: タグを使用すると、キャンペーンをより簡単に整理し、並べ替えることができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 335c1b80-f1f0-4fd0-add8-84b8cc5e2e00
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---

# タグの削除 {#delete-tag}

タグの削除 (削除) が必要になる場合があります。 テナントコンテナで作成したタグのみが削除される場合があります。 これは、削除するタグの $id を使用して、API に [!DNL Offer Library] 削除要求を実行することによって実行されます。

**API フォーマット**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | タグが配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するタグのインスタンス id。 | `d48fd160-13dc-11eb-bc55-c11be7252432` |

**要求**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/d48fd160-13dc-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**対し**

応答が成功した場合は、HTTP 状態 202 (内容なし) と空白の本文が返されます。

削除を確認するには、タグに対して lookup (GET) 要求を実行します。 要求に Accept ヘッダーを含める必要がありますが、タグがコンテナから削除されているので、HTTP ステータス 404 (見つかりません) が表示されます。

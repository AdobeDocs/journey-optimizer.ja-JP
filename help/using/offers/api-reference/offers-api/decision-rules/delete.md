---
title: 意思決定ルールの削除
description: 決定ルールとは、パーソナライズされた申し出に追加され、プロファイルに適用されて、適格性を決定することです。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 52f4803b-9e9a-4ad0-ae24-de652006763d
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# 決定ルールの削除 {#delete-decision-rule}

場合によっては、決定ルールを削除 (削除) することが必要な場合があります。 テナントコンテナに作成した decision rules Only は削除することができます。 これは、削除する意思決定規則のインスタンス ID を使用して、API に [!DNL Offer Library] 削除要求を実行することによって実行されます。

**API フォーマット**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | 決定ルールが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するデシジョンルールのインスタンス id です。 | `eaa5af90-13d9-11eb-9472-194dee6dc381` |

**要求**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/eaa5af90-13d9-11eb-9472-194dee6dc381' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**対し**

応答が成功した場合は、HTTP 状態 202 (内容なし) と空白の本文が返されます。

Decision ルールに対して lookup (GET) 要求することによって、削除を確認することができます。 要求に Accept ヘッダーを含める必要がありますが、decision ルールがコンテナから削除されているので、HTTP ステータス 404 (見つかりません) を受け取る必要があります。

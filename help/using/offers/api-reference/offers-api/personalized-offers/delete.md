---
title: パーソナライズされたオファーの削除
description: パーソナライズされたオファーは、実施要件ルールおよび制約に基づいてカスタマイズできるマーケティングメッセージです。
translation-type: tm+mt
source-git-commit: 4ff255b6b57823a1a4622dbc62b4b8886fd956a0
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 100%

---

# パーソナライズされたオファーの削除

場合によっては、パーソナライズされたオファーを削除（DELETE）する必要があります。テナントコンテナで作成したパーソナライズされたオファーのみを削除できます。これは、削除するパーソナライズされたオファーの $id を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行することでおこないます。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | パーソナライズされたオファーが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0f4bc230-13df-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答** 

正常な応答の場合は、空白の本文とともに HTTP ステータス 202 （コンテンツなし）が返されます。

パーソナライズされたオファーに対して検索（GET）リクエストを実行することで、削除を確認できます。リクエストには Accept ヘッダーを含める必要がありますが、パーソナライズされたオファーがコンテナから削除されたので、HTTP ステータス 404（見つかりません）を受け取ります。

---
title: コレクション修飾子の削除
description: コレクション修飾子を使用すると、オファーをより整理および並べ替えることができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 335c1b80-f1f0-4fd0-add8-84b8cc5e2e00
source-git-commit: 835e4bf227ce330b1426a9a4331fdf533fc757e3
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 15%

---

# コレクション修飾子の削除 {#delete-tag}

コレクション修飾子（旧称「tag」）を削除 (DELETE) する必要が生じる場合があります。 削除できるのは、テナントコンテナで作成したコレクション修飾子だけです。 これは、 [!DNL Offer Library] 削除するコレクション修飾子の$id を使用する API。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクション修飾子が配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するコレクション修飾子のインスタンス ID。 | `d48fd160-13dc-11eb-bc55-c11be7252432` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/d48fd160-13dc-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、空白の本文とともに HTTP ステータス 202 （コンテンツなし）が返されます。

コレクション修飾子に対して検索 (GET) リクエストを試みることで、削除を確認できます。 リクエストに Accept ヘッダーを含める必要がありますが、コレクション修飾子がコンテナから削除されたので、HTTP ステータス 404(Not Found) を受け取る必要があります。

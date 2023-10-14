---
title: プレースメントの削除
description: プレースメントは、オファーの表示に使用するコンテナです。
feature: Offers, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: ca7af3b0-62cd-44ac-8856-b3d1ec15f284
source-git-commit: 3f96cc0037b5bcdb2ce94e2721b02ba13b3cff36
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 39%

---

# プレースメントの削除 {#delete-placement}

場合によっては、プレースメントを削除（DELETE）する必要があります。これは、 [!DNL Offer Library] 削除する配置の ID を使用する API。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/placements/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 更新するプレースメントのインスタンス ID。 | `offerPlacement1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/placements/offerPlacement1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答は、HTTP ステータス 200 と空白の本文を返します。

配置が削除されたので、配置に対して検索 (GET) リクエストを試行すると、HTTP ステータス 404（見つかりません）が返されます。

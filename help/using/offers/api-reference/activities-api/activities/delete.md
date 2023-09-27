---
title: 決定の削除
description: 決定には、オファーの選択を通知するロジックが含まれています。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 1eb19ff1-b210-4891-ab41-5488e2635527
source-git-commit: 805f7bdc921c53f63367041afbb6198d0ec05ad8
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 44%

---

# 決定の削除 {#delete-decision}

場合によっては、決定ルールを削除（DELETE）する必要があります。これは、 [!DNL Offer Library] を使用した API `id` を選択します。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/offer-decisions/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続化 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 削除するエンティティの ID。 | `offerDecision1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-decisions/offerDecision1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答は、HTTP ステータス 200 と空白の本文を返します。

決定に対して検索（GET）リクエストを試行することで、削除を確認できます。決定が削除されたので、HTTP ステータス 404(Not Found) が表示されます。

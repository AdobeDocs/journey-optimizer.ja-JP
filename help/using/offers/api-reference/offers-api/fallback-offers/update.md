---
title: フォールバックオファーの更新
description: フォールバックオファーは、他のオファーの対象とならない顧客に送信されます。
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 7ff69887-620f-4bc0-b8ff-5144ff30696c
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 100%

---

# フォールバックオファーの更新 {#update-fallback-offer}

[!DNL Offer Library] API に対して PATCH リクエストを実行することで、コンテナ内のフォールバックオファーを変更または更新できます。

使用可能な操作など、JSON パッチの詳細については、[JSON パッチの公式ドキュメント](https://jsonpatch.com/)を参照してください。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、リクエストヘッダーの *Content-Type* フィールドと *Accept* フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Content-Type | `application/json` |

**API 形式**

```http
PATCH /{ENDPOINT_PATH}/offers/{ID}?offer-type=fallback
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 更新するエンティティの ID。 | `fallbackOffer1234` |

**リクエスト**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offers/fallbackOffer1234?offer-type=fallback' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated fallback offer"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated fallback offer description"
    }
]'
```

| パラメーター | 説明 |
| --------- | ----------- |
| `op` | 接続の更新に必要なアクションを定義するのに使用される操作呼び出し。操作には、`add`、`replace`、`remove`、`copy` および `test` があります。 |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターの更新に使用する新しい値。 |

**応答**

応答が成功すると、フォールバックオファーの更新された詳細（`id` を含む）が返されます。

```json
{
    "id": "{ID}",
    "datasetId": "{DATASET_ID}",
    "sandboxId": "{SANDBOX_ID}",
    "etag": 2,
    "createdDate": "2023-09-07T12:47:43.012Z",
    "lastModifiedDate": "2023-09-07T12:47:43.012Z",
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

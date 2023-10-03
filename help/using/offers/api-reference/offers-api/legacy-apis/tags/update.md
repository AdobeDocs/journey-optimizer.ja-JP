---
title: コレクション修飾子の更新
description: コレクション修飾子を使用すると、オファーをより適切に整理し並べ替えることができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 918927e1-ad7a-4937-b652-2a0932e9efa1
source-git-commit: 54b92b19f2e3a6afa6557ffeff0d971a4c411510
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 64%

---

# コレクション修飾子の更新 {#update-collection-qualifier}

コレクション修飾子（旧称「タグ」）の変更または更新は、 [!DNL Offer Library] API.

使用可能な操作など、JSON パッチの詳細については、[JSON パッチの公式ドキュメント](https://jsonpatch.com/)を参照してください。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、 *Content-Type* リクエストヘッダーのフィールド：

| ヘッダー名 | 値 |
| ----------- | ----- |
| Content-Type | `application/json` |

**API 形式**

```http
PATCH /{ENDPOINT_PATH}/tags/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | タグが配置されているコンテナ。 | `tag1234` |

**リクエスト**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/tags/tag1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated tag"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated tag description"
    }
]'
```

| パラメーター | 説明 |
| --------- | ----------- |
| `op` | 接続の更新に必要なアクションを定義するために使用される操作呼び出し。操作には次のものが含まれます。 `add`, `replace`, `remove`, `copy` および `test`. |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターの更新に使用する新しい値。 |

**応答**

正常な応答は、コレクション修飾子とコレクション修飾子の更新された詳細を返します `id`.

```json
{
    "etag": 2,
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "{ID}",
    "sandboxId": "{SANDBOX_ID}",
    "createdDate": "2023-05-31T15:09:11.771Z",
    "lastModifiedDate": "2023-05-31T15:09:11.771Z",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

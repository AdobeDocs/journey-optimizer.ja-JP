---
title: フォールバックオファーの更新
description: フォールバックオファーは、他のオファーの対象とならない顧客に送信されます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7ff69887-620f-4bc0-b8ff-5144ff30696c
source-git-commit: 722b908c33834af1c4199d597fe4d573cdea8557
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 86%

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
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | フォールバックオファーが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | フォールバックオファーのインスタンス ID。 | `b3966680-13ec-11eb-9c20-8323709cfc65` |

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
| `op` | 接続の更新に必要なアクションを定義するために使用される操作呼び出し。操作には、`add`、`replace`、`remove` があります。 |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターの更新に使用する新しい値。 |
ens35577は、この会話を解決済みとマークしました。
解決済みを表示

**応答**

正常な応答は、フォールバックオファーの更新された詳細（一意のインスタンスを含む）を返します `id`.

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

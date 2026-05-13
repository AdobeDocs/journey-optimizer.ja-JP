---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: プレースメントの更新
description: プレースメントは、オファーを表示するために使用されるコンテナです。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 6990918c-e736-4f28-9ac6-9ac3101b069f
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/0Oy4Xd0F9lDuDC6A6IiTIp50LhJCfgCMgYcP4o4w8DQ
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 166
ht-degree: 0%

---

# プレースメントの更新 {#update-placement}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


プレースメントを変更または更新するには、[!DNL Offer Library] APIに対してPATCH リクエストを行います。

使用可能な操作を含むJSON パッチについて詳しくは、公式の[JSON パッチドキュメント ](https://jsonpatch.com/)を参照してください。

## 受け入れるヘッダーとコンテンツタイプのヘッダー {#accept-and-content-type-headers}

次の表は、リクエストヘッダーの&#x200B;*Content-Type* フィールドを構成する有効な値を示しています。

| ヘッダー名 | 値 |
| ----------- | ----- |
| コンテンツタイプ | `application/json` |

**API形式**

```http
PATCH /{ENDPOINT_PATH}/placements/{ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 更新するエンティティのID。 | `offerPlacement1234` |

**リクエスト**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/placements/offerPlacement1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated placement"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated placement description"
    }
]'
```

| パラメーター | 効果 |
| --------- | ----------- |
| `op` | 接続の更新に必要なアクションを定義するために使用される操作呼び出し。 操作には、`add`、`replace`、`remove`、`copy`および`test`が含まれます。 |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターを更新する新しい値。 |

**応答**

応答が成功すると、プレースメントの更新された詳細（一意のプレースメント `id`を含む）が返されます。

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

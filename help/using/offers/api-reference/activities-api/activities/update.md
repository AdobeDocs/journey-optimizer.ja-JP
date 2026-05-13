---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定の更新
description: 決定には、オファーの選択に役立つロジックが含まれます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 98c5ccf9-2a7f-4129-a520-d0671a86e13d
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/KUJuVzsryTRtcVfxPPkolvVQyh67PlZCNHAyP87sIIE
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 167
ht-degree: 0%

---

# 決定の更新 {#update-decision}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


PATCH リクエストを[!DNL Offer Library] APIに行うことで、決定を変更または更新できます。

使用可能な操作を含むJSON パッチについて詳しくは、公式の[JSON パッチドキュメント &#x200B;](https://jsonpatch.com/)を参照してください。

## 受け入れるヘッダーとコンテンツタイプのヘッダー {#accept-and-content-type-headers}

次の表は、リクエストヘッダーの&#x200B;*Content-Type*&#x200B;および&#x200B;*Accept* フィールドを構成する有効な値を示しています。

| ヘッダー名 | 値 |
| ----------- | ----- |
| コンテンツタイプ | `application/json` |

**API形式**

```http
PATCH /{ENDPOINT_PATH}/offer-decisions/{ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 更新するエンティティのID。 | `offerDecision1234` |

**リクエスト**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offer-decisions/offerDecision1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated offer decision"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated offer decision description"
    }
]'
```

| パラメーター | 効果 |
| --------- | ----------- |
| `op` | 接続の更新に必要なアクションを定義するために使用される操作呼び出し。 操作には、`add`、`replace`、`remove`、`copy`および`test`が含まれます。 |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターを更新する新しい値。 |

**応答**

応答が成功すると、決定`id`を含む、決定の更新された詳細が返されます。

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

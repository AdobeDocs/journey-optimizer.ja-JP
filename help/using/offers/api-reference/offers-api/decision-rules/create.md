---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定ルールの作成
description: 決定ルールは、パーソナライズされたオファーに追加される制約で、実施要件を決定するためにプロファイルに適用されます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 6a05efca-31bd-46d5-998d-ff3038d9013f
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/wpVQ64pwXQz9So3T8MLgooq3gmwEBC28lEq3UllDDL8
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: c132d929-fa62-4271-803e-b823be07b914id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 100%

---

# 決定ルールの作成 {#create-decision-rule}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


決定ルールは、パーソナライズされたオファーに追加される制約で、実施要件を決定するのにプロファイルに適用されます。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、リクエストヘッダーの「*Content-Type*」フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Content-Type | `application/json` |

**API 形式**

```http
POST /{ENDPOINT_PATH}/offer-rules
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |

**リクエスト**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/offer-rules' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{
    "name": "Sales rule",
    "description": "Decisioning rule for sales",
    "condition": {
        "type": "PQL",
        "format": "pql/text",
        "value": "profile.person.name.firstName.equals(\"Joe\", false)"
    },
    "definedOn": {
        "profile": {
            "schema": {
                "ref": "https://ns.adobe.com/xdm/context/profile_union",
                "version": "1"
            },
            "referencePaths": [
                "person.name.firstName"
            ]
        }
    }
}'
```

**応答**

応答が成功すると、新規作成された決定ルール`id`に関する情報が返されます。 後の手順で `id` を使用して、決定ルールを更新または削除するか、後のチュートリアルで使用して、決定、決定ルールおよびフォールバックオファーを作成します。

```json
{
   "etag": 1,
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

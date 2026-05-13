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
exl-id: 63a6b50b-9e42-43c0-87ee-19fcb6ecdd98
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/JECQ2xgIFVzyr9ycjIr-3KmbBr-9bfVOOD2472Q12G4
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 180
ht-degree: 0%

---

# 決定の更新 {#update-decision}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


PATCH リクエストを[!DNL Offer Library] APIに行うことで、コンテナ内の決定を変更または更新できます。

使用可能な操作を含むJSON パッチについて詳しくは、公式の[JSON パッチドキュメント ](https://jsonpatch.com/)を参照してください。

## 受け入れるヘッダーとコンテンツタイプのヘッダー {#accept-and-content-type-headers}

次の表は、リクエストヘッダーの&#x200B;*Content-Type*&#x200B;および&#x200B;*Accept* フィールドを構成する有効な値を示しています。

| ヘッダー名 | 値 |
| ----------- | ----- |
| 承認 | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| コンテンツタイプ | `application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"` |

**API形式**

```http
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | 決定が配置されるコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 決定のインスタンス ID。 | `f88c9be0-1245-11eb-8622-b77b60702882` |

**リクエスト**

```shell
curl -X PATCH \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/f88c9be0-1245-11eb-8622-b77b60702882' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5"' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
            "path": "/_instance/xdm:name",
            "value": "Example Activity Name"
    }
]'
```

| パラメーター | 効果 |
| --------- | ----------- |
| `op` | 接続の更新に必要なアクションを定義するために使用される操作呼び出し。 操作には、`add`、`replace`および`remove`が含まれます。 |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターを更新する新しい値。 |

**応答**

応答が成功すると、一意のインスタンス IDと決定`@id`を含む、決定の更新された詳細が返されます。

```json
{
    "instanceId": "f88c9be0-1245-11eb-8622-b77b60702882",
    "@id": "xcore:offer-activity:124b79dc3ce2d720",
    "repo:etag": 2,
    "repo:createdDate": "2023-10-19T20:02:09.694067Z",
    "repo:lastModifiedDate": "2023-10-19T21:28:24.284719Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

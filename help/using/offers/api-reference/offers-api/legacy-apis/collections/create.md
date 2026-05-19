---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクションを作成
description: コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: ea79add2-1ea7-4c5c-ba67-f99d10975c4f
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/b79e3rlJX5ZZnq6QXvrWkkSjlTKHShiJ0Cc2jXEPQnE
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 177
ht-degree: 0%

---

# コレクションを作成 {#create-collection}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。

コンテナ IDを指定しながら、[!DNL Offer Library] APIにPOST リクエストを行うことで、コレクションを作成できます。

## 受け入れるヘッダーとコンテンツタイプのヘッダー {#accept-and-content-type-headers}

次の表は、リクエストヘッダーの&#x200B;*Content-Type*&#x200B;および&#x200B;*Accept* フィールドを構成する有効な値を示しています。

| ヘッダー名 | 値 |
| ----------- | ----- |
| 承認 | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| コンテンツタイプ | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"` |

**API形式**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクションが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**リクエスト**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
        "xdm:name": "Offer Collection 1",
        "xdm:filterType": "anyTags",
        "xdm:ids": [
            "xcore:tag:124e147572cd7866"
        ]
    }'
```

**応答**

応答が成功すると、一意のインスタンス IDとプレースメント `@id`を含む、新しく作成されたコレクションに関する情報が返されます。 後の手順でインスタンス IDを使用して、コレクションを更新または削除できます。 後のチュートリアルで独自のコレクション `@id`を使用して、決定を作成できます。

```json
{
   "@id": "xcore:offer-filter:124e3594ce8b4930",
    "repo:etag": 1,
    "repo:createdDate": "2023-10-21T22:59:17.345797Z",
    "repo:lastModifiedDate": "2023-10-21T22:59:17.345797Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクションを更新
description: コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: bf12d22f-e6c0-45fd-a2b2-149d3f4cf882
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/6IMCGBo0Mi1Xokge4f7i9QBfdoVikblWSOuT76Ziapw
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 0%

---

# コレクションの更新 {#update-collection}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


コレクションを変更または更新するには、[!DNL Offer Library] APIに対してPATCH リクエストを行います

使用可能な操作を含むJSON パッチについて詳しくは、公式の[JSON パッチドキュメント ](https://jsonpatch.com/)を参照してください。

## 受け入れるヘッダーとコンテンツタイプのヘッダー {#accept-and-content-type-headers}

次の表は、リクエストヘッダーの&#x200B;*Content-Type*&#x200B;および&#x200B;*Accept* フィールドを構成する有効な値を示しています。

| ヘッダー名 | 値 |
| ----------- | ----- |
| 承認 | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| コンテンツタイプ | `application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"` |

**API形式**

```http
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクションが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するコレクションのインスタンス ID。 | `0bf31c20-13f1-11eb-a752-e58fd7dc4cb3` |

**リクエスト**

```shell
curl -X PATCH \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0bf31c20-13f1-11eb-a752-e58fd7dc4cb3' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1"' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
            "op": "add",
            "path": "/_instance/xdm:filterType",
            "value": "anyTags"
    },
    {
            "op": "add",
            "path": "/_instance/xdm:ids",
            "value": ["xcore:tag:124e147572cd7866"]
    }
]'
```

| パラメーター | 効果 |
| --------- | ----------- |
| `op` | 接続の更新に必要なアクションを定義するために使用される操作呼び出し。 操作には、`add`、`replace`および`remove`が含まれます。 |
| `path` | 更新するパラメーターのパス。 |
| `value` | パラメーターを更新する新しい値。 |

**応答**

応答が成功すると、一意のインスタンス IDとコレクション `@id`を含む、コレクションの更新された詳細が返されます。

```json
{
    "instanceId": "0bf31c20-13f1-11eb-a752-e58fd7dc4cb3",
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

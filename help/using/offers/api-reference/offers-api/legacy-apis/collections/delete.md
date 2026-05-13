---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクションの削除
description: コレクションは、オファーのカテゴリなど、マーケターが定義した定義済みの条件に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 351d1f44-f3dc-49f9-bc3d-c775dad3cad4
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/G6jbQBv1gvN0sYtrD34swQNoYwQgnSXKgipIHw395Lw
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 0%

---

# コレクションの削除 {#delete-collection}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


（DELETE）コレクションを削除する必要がある場合があります。 テナントコンテナで作成したコレクションのみが削除されます。 これは、削除するコレクションの$idを使用して、[!DNL Offer Library] APIに対してDELETE リクエストを実行することで実行されます。

**API形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクションが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するコレクションのインスタンス ID。 | `0bf31c20-13f1-11eb-a752-e58fd7dc4cb3` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0bf31c20-13f1-11eb-a752-e58fd7dc4cb3' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、HTTP ステータス 202 （コンテンツなし）と空白の本文が返されます。

コレクションに対するルックアップ（GET）リクエストを試みることで、削除を確定できます。 リクエストにAccept ヘッダーを含める必要がありますが、コレクションがコンテナから削除されたため、HTTP ステータス 404 （見つかりません）を受け取る必要があります。

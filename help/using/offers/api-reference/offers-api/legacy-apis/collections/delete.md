---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクションの削除
description: コレクションは、マーケターが事前に定義した条件（オファーのカテゴリなど）に基づくオファーのサブセットです。
feature: Decision Management, API, Collections
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 351d1f44-f3dc-49f9-bc3d-c775dad3cad4
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/G6jbQBv1gvN0sYtrD34swQNoYwQgnSXKgipIHw395Lw
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 100%

---

# コレクションの削除 {#delete-collection}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


場合によっては、コレクションを削除（DELETE）する必要があります。 テナントコンテナで作成したコレクションのみを削除できます。 これは、削除するコレクションの $id を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行することでおこないます。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
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

リクエストが成功した場合は、HTTP ステータス 202（コンテンツなし）が空白の本文とともに返されます。

コレクションに対して検索（GET）リクエストを実行することで、削除を確認できます。 リクエストには Accept ヘッダーを含める必要がありますが、コレクションがコンテナから削除されたので、HTTP ステータス 404（見つかりません）を受け取ります。

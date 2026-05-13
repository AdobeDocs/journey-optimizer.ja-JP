---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクション修飾子の削除
description: コレクション修飾子を使用すると、オファーをより適切に整理し、並べ替えることができます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: cc67519e-7a80-49c7-8c8b-c777be633026
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/F-VfY9-rc6cxyIz077xD6oRzXUUThUpokPjDEn3wNnE
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
source-wordcount: 178
ht-degree: 0%

---

# コレクション修飾子の削除 {#delete-tag}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


コレクション修飾子（以前は「タグ」と呼ばれていました）を削除（DELETE）する必要がある場合があります。 テナントコンテナで作成したコレクション修飾子のみが削除されます。 これは、削除するコレクション修飾子の$idを使用して、[!DNL Offer Library] APIに対してDELETE リクエストを実行することで実行されます。

**API形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | コレクション修飾子が配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新するコレクション修飾子のインスタンス ID。 | `d48fd160-13dc-11eb-bc55-c11be7252432` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/d48fd160-13dc-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、HTTP ステータス 202 （コンテンツなし）と空白の本文が返されます。

コレクション修飾子に対するルックアップ（GET）リクエストを試みることで、削除を確定できます。 リクエストにAccept ヘッダーを含める必要がありますが、コレクション修飾子がコンテナから削除されたため、HTTP ステータス 404 （見つかりません）を受け取る必要があります。

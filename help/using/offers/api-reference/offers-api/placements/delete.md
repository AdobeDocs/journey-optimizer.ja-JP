---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: プレースメントの削除
description: プレースメントは、オファーの表示に使用するコンテナです。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: ca7af3b0-62cd-44ac-8856-b3d1ec15f284
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/ACEsOlaOqRgSxKAkgd-X2IK0oL8IQ7vmv4RwTwyOMTA
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 128
ht-degree: 100%

---

# プレースメントの削除 {#delete-placement}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../../../experience-decisioning/gs-experience-decisioning.md)


場合によっては、プレースメントを削除（DELETE）する必要があります。 これは、削除するプレースメントの ID を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行することで行います。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/placements/{ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | 永続性 API のエンドポイントパス。 | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | 更新するプレースメントのインスタンス ID。 | `offerPlacement1234` |

**リクエスト**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/placements/offerPlacement1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答の場合は、HTTP ステータス 200 と空白の本文が返されます。

プレースメントに対して検索（GET）リクエストを試行することで、プレースメントが削除されるので、HTTP ステータス 404（見つかりません）が表示され、削除を確認できます。

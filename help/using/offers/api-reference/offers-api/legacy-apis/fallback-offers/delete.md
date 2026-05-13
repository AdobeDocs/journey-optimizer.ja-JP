---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: フォールバックオファーの削除
description: 他のオファーの対象ではない場合は、フォールバックオファーが顧客に送信されます
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 5e97a1fd-7542-4c9a-8234-21c1fa419671
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/AwEMmVSJOAsd0uD45JftZ0PqavVLuIXMpOTqNUeDNmg
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 0%

---

# フォールバックオファーの削除 {#delete-fallback-offer}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


（DELETE）フォールバックオファーを削除する必要がある場合があります。 テナントコンテナで作成したフォールバックオファーのみが削除されます。 これは、削除するフォールバックオファーの$idを使用して、[!DNL Offer Library] APIに対してDELETE リクエストを実行することで実行されます。

**API形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | フォールバックオファーが配置されるコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | フォールバックオファーのインスタンス ID。 | `b3966680-13ec-11eb-9c20-8323709cfc65` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/b3966680-13ec-11eb-9c20-8323709cfc65' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、HTTP ステータス 202 （コンテンツなし）と空白の本文が返されます。

フォールバックオファーに対してルックアップ（GET）リクエストを試行することで、削除を確定できます。 リクエストにAccept ヘッダーを含める必要がありますが、フォールバックオファーがコンテナから削除されたため、HTTP ステータス 404 （見つかりません）を受け取る必要があります。

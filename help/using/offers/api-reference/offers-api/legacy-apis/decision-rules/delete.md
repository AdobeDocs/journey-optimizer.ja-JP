---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定ルールの削除
description: 決定ルールは、パーソナライズされたオファーに追加される制約で、実施要件を決定するためにプロファイルに適用されます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 7c02041c-b022-4027-b932-294b207add80
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/2wENqKr6NPiduDQYRD8VdJtbzjgSGubC0rlpHy-wLW8
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: c132d929-fa62-4271-803e-b823be07b914id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 180
ht-degree: 100%

---

# 決定ルールの削除 {#delete-decision-rule}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


場合によっては、決定ルールを削除（DELETE）する必要があります。 テナントコンテナで作成した決定ルールのみを削除できます。 これは、削除する決定ルールのインスタンス ID を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行することでおこないます。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | 決定ルールが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | 更新する決定ルールのインスタンス ID。 | `eaa5af90-13d9-11eb-9472-194dee6dc381` |

**リクエスト**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/eaa5af90-13d9-11eb-9472-194dee6dc381' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

リクエストが成功した場合は、HTTP ステータス 202（コンテンツなし）が空白の本文とともに返されます。

決定ルールに対して検索（GET）リクエストを実行することで、削除を確認できます。 リクエストには Accept ヘッダーを含める必要がありますが、決定ルールがコンテナから削除されたので、HTTP ステータス 404（見つかりません）を受け取ります。

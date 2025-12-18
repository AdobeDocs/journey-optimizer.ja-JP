---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクション修飾子の削除
description: コレクション修飾子を使用すると、オファーをより適切に整理し並べ替えることができます。
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: cc67519e-7a80-49c7-8c8b-c777be633026
version: Journey Orchestration
source-git-commit: 0b6d41fad9715985ec6418cdda27760f977bbc47
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 100%

---

# コレクション修飾子の削除 {#delete-tag}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。[詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


コレクション修飾子（旧称「タグ」）を削除（DELETE）する必要が生じる場合があります。 テナントコンテナで作成したコレクション修飾子のみを削除できます。これは、削除するコレクション修飾子の $id を使用して [!DNL Offer Library] API に対する DELETE リクエストを実行することで行います。

**API 形式**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
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

正常な応答の場合は、空白の本文とともに HTTP ステータス 202 （コンテンツなし）が返されます。

コレクション修飾子に対して検索（GET）リクエストを実行することで、削除を確認できます。リクエストには Accept ヘッダーを含める必要がありますが、コレクション修飾子がコンテナから削除されたので、HTTP ステータス 404（見つかりません）を受け取ります。

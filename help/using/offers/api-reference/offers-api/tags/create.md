---
title: タグの作成
description: タグを使用すると、オファーの整理と並べ替えをより適切におこなうことができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: f3f7cccb-0173-409e-8b76-8b6e136a22ac
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: ht
source-wordcount: '128'
ht-degree: 100%

---

# タグの作成

コンテナ ID を提供しながら [!DNL Offer Library] API に対して POST リクエストを実行することで、タグを作成できます。

## Accept ヘッダーと Content-Type ヘッダー

次の表に、リクエストヘッダーの *Content-Type* フィールドと *Accept* フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Accept | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/schema-instance+json; version=1; schema="https://ns.adobe.com/experience/offer-management/tag;version=0.1"` |

**API 形式**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | タグが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**リクエスト**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/schema-instance+json; version=1; schema="https://ns.adobe.com/experience/offer-management/tag;version=0.1"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
        "xdm:name": "Holiday sales and promotions"
    }'
```

**応答**

正常な応答では、新たに作成されたタグに関する情報（一意のインスタンス ID とプレースメント `@id` を含む）が返されます。後の手順で、このインスタンス ID を使用してタグを更新または削除できます。後のチュートリアルで、独自のタグ `@id` を使用して、コレクションやパーソナライズされたオファーを作成できます。

```json
{
    "instanceId": "d48fd160-13dc-11eb-bc55-c11be7252432",
    "@id": "xcore:tag:124e147572cd7866",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-21T20:34:34.486296Z",
    "repo:lastModifiedDate": "2020-10-21T20:34:34.486296Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

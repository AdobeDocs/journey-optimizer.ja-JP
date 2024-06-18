---
title: プレースメントの作成
description: プレースメントは、オファーの表示に使用するコンテナです。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 5c7301f6-95d3-4720-81fe-5f2602cd30ec
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 41%

---

# プレースメントの作成 {#create-placement}

に対してPOSTリクエストを実行することで、プレースメントを作成できます。 [!DNL Offer Library] API、コンテナ ID を提供している間。

## Accept ヘッダーと Content-Type ヘッダー {#accept-and-content-type-headers}

次の表に、を構成する有効な値を示します *Content-Type* および *承諾* リクエストヘッダーのフィールド :

| ヘッダー名 | 値 |
| ----------- | ----- |
| Accept | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"` |

**API 形式**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | プレースメントが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**リクエスト**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{
        "xdm:name": "Sales Placement",
        "xdm:componentType": "https://ns.adobe.com/experience/offer-management/content-component-html",
        "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
        "xdm:description": "A test placement to contain offers"
}'
```

**応答**

正常な応答では、新たに作成されたプレースメントの詳細（一意のインスタンス ID とプレースメントを含む）が返されます `@id`. 後の手順で、このインスタンス ID を使用してプレースメントを更新または削除できます。 後のチュートリアルでは独自のプレースメント `@id` を使用して、アクティビティ、決定ルール、フォールバックオファーを作成できます。

```json
{
    "instanceId": "9aa58fd0-13d7-11eb-928b-576735ea4db8",
    "@id": "xcore:offer-placement:124e0be5699743d3",
    "repo:etag": 1,
    "repo:createdDate": "2023-10-21T19:57:09.837456Z",
    "repo:lastModifiedDate": "2023-10-21T19:57:09.837456Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```

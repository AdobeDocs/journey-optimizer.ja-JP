---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: ルックアップフォールバックオファー
description: 他のオファーの対象ではない場合は、フォールバックオファーが顧客に送信されます
feature: Decision Management, API
badge: label="レガシー" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: e470d491-b30b-4d26-83a6-e5b34e49fe61
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/GubmNQXLGlQAodN0cCHU8gzxr6IAzGQnaNEQfDceRYg
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 0%

---

# フォールバックオファーの検索 {#look-up-fallback-offers}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../../../experience-decisioning/gs-experience-decisioning.md)


フォールバックオファー`@id`またはリクエストパス内のフォールバックオファーの名前を含む[!DNL Offer Library] APIに対してGET リクエストを行うことで、特定のフォールバックオファーを検索できます。

**API形式**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_FALLBACK_OFFER}&{QUERY_PARAMS}
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | フォールバックオファーが配置されるコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_FALLBACK_OFFER}` | フォールバックオファーに関連付けられたスキーマを定義します。 | `https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1` |
| `id` | エンティティの`@id` プロパティに一致するために使用される文字列。 文字列が正確に一致します。 パラメーター`id`と`name`は同時に使用できません。 | `xcore:fallback-offer:122206064e0d98df` |
| `name` | エンティティのxdm:name プロパティに一致するために使用される文字列。 文字列は大文字と小文字が正確に一致しますが、ワイルドカード文字を使用できます。 パラメーター`id`と`name`は同時に使用できません | `F1: Web fallback` |

**リクエスト**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances?schema=https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1&id=xcore:fallback-offer:122206064e0d98df' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

応答が成功すると、コンテナ ID、インスタンス ID、一意のフォールバックオファー`@id`に関する情報を含む、プレースメントの詳細が返されます。

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1",
    "requestTime": "2023-10-21T22:21:50.658080Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "053bc610-f8f9-11ea-ad6e-775ad2c9b1a1",
    "schemas": [
                    "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.5"
                ],
                "productContexts": [
                    "acp"
    ],
                "repo:etag": 3,
                "repo:createdDate": "2023-09-17T15:18:20.657299Z",
                "repo:lastModifiedDate": "2023-10-02T02:34:48.034583Z",
                "repo:createdBy": "712B3670554A7AF17F000101@AdobeID",
                "repo:lastModifiedBy": "68D9EA8559BC2D810A495CC2@AdobeID",
                "repo:createdByClientId": "exc_app",
                "repo:lastModifiedByClientId": "exc_app",
                "_score": 0,
                "_instance": {
                    "xdm:name": "F1: Web fallback ",
                    "xdm:representations": [
                        {
                            "xdm:components": [
        {
                                    "xdm:content": "aaa",
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-json",
                                    "dc:format": "application/json",
                                    "repo:name": "aa"
                                }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                            "xdm:placement": "xcore:offer-placement:122201b2150d98c2"
                        },
                        {
                            "xdm:components": [
                                {
                                    "xdm:content": "bb",
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-html",
                                    "dc:format": "text/html",
                                    "repo:name": "bb"
                                }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                            "xdm:placement": "xcore:offer-placement:122201c34354a2b4"
                        },
                {
                            "xdm:components": [
                                {
                                    "xdm:deliveryURL": "https://mysite.com",
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-imagelink",
                                    "dc:format": "image/png",
                                    "repo:name": "ll"
                                }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                            "xdm:placement": "xcore:offer-placement:122207eddb05205a"
                        }
                    ],
                    "xdm:status": "approved",
                    "xdm:tags": [],
                    "@id": "xcore:fallback-offer:122206064e0d98df"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.5#053bc610-f8f9-11ea-ad6e-775ad2c9b1a1",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/053bc610-f8f9-11ea-ad6e-775ad2c9b1a1",
                        "@type": "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.5"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            }
        ],
        "total": 1,
        "count": 1
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances?schema=https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.1&id=xcore:fallback-offer:122206064e0d98df",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
                }
        }
}
```

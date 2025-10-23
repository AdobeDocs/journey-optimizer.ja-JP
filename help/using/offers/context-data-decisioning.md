---
product: experience platform
solution: Experience Platform
title: コンテキストデータと決定リクエスト
description: 決定リクエストでコンテキストデータを渡す方法について説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management
role: Developer
level: Experienced
exl-id: 45d060ce-0a12-4a6e-a594-ec10cdff8f38
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---

# コンテキストデータと決定リクエスト {#context-data-decisioning}

この節では、決定リクエストでコンテキストデータを渡し、実施要件ルールで使用する方法について説明します。

>[!BEGINSHADEBOX]

さらに進んで、コンテキストを&#x200B;**ランキング式**&#x200B;に活用し、オファーの優先度を上げることもできます。コンテキストデータを活用したランキング式の例について詳しくは、[この節](../offers/ranking/create-ranking-formulas.md#context-data)を参照してください。

>[!ENDSHADEBOX]

## 決定リクエストのコンテキストデータを渡す

決定リクエストのコンテキストデータは、`xdm:ContextData` キーを使用して定義されます。

コンテキストデータ属性は、XDM スキーマによって駆動されません。決定リクエストペイロードの一部として、JSON で任意のコンテキストデータを渡すことができます。

コンテキストデータを含む決定リクエストの例を次に示します（`xdm:ContextData` を参照）。

```
curl --location 'https://platform-stage.adobe.io/data/core/ods/decisions' \
--header 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
--header 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"' \
--header 'Authorization: Bearer eyJhbGciOi....' \
--header 'x-api-key: {{api_key}}' \
--header 'x-gw-ims-org-id: {{ims_org}}' \
--header 'x-sandbox-name: {{sandbox_name}}' \
--header 'x-request-id: {{$guid}}' \
--data-raw '{
    "xdm:propositionRequests": [
        {
            "xdm:activityId": "dps:offer-activity:19978bf95ebfc8fb",
            "xdm:placementId": "dps:offer-placement:199772e1c90d50ac"
        }
    ],
    "xdm:profiles": [
        {
            "xdm:identityMap": {
                "Email": [
                    {
                        "xdm:id": "test@test.com",
                        "primary": true
                    }
                ]
            },
            "xdm:contextData": [
                {
                    "@type": "_xdm.context.additionalParameters;version=1",
                    "xdm:data": {
                        "xdm:channel": "mobile",
                        "xdm:language": "en",
                        "xdm:isThirdParty": true,
                        "xdm:mobileVersion": "3.0.5106",
                        "xdm:mobileVersionMajor": "3",
                        "xdm:mobileVersionMinor": "0",
                        "xdm:mobileVersionPatch": "125",
                        "xdm:deviceType": "iOS",
                        "xdm:features": [
                            "p1000",
                            "p1001"
                        ]
                    }
                }
            ]
        }
    ],
    "xdm:allowDuplicatePropositions": {
        "xdm:acrossActivities": true,
        "xdm:acrossPlacements": true
    },
    "xdm:responseFormat": {
        "xdm:includeContent": true,
        "xdm:includeMetadata": {
            "xdm:activity": [
                "name"
            ],
            "xdm:option": [
                "name"
            ],
            "xdm:placement": [
                "name"
            ]
        }
    }
}'
```

## 実施要件ルールでのコンテキストデータの使用

決定リクエストで渡されるコンテキストデータを実施要件ルールで使用する方法の例を次に示します。

* コンテキストデータ機能に特定の値が含まれている場合は、次を実施できます。

  ```
  select contextData from @{_xdm.context.additionalParameters;version=1} where contextData.features AND (select personetic from contextData.features where personetic.contains("123"))
  ```

* チャネルが空でなくモバイルと等しい場合は、次を実施できます。

  ```
  select contextData from @{_xdm.context.additionalParameters;version=1} where !contextData.channel.isNull() AND contextData.channel!="" AND contextData.channel="mobile"
  ```

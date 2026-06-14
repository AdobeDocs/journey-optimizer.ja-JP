---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーにイベントを送信するための追加手順
description: ジャーニーにイベントを送信するための追加手順を学ぶ
feature: Journeys, Events
topic: Administration
role: Developer, Admin
level: Intermediate, Experienced
keywords: 手順, 設定, ジャーニー, イベント, ストリーム, API
exl-id: e0144151-6c54-4656-9650-b544d8e7be16
TQID: https://experienceleague.adobe.com/SiUXmerz2D-TYmIEXvaYk4usjRq67Y0v7V7sGVN-4vo
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d998adac-2f81-400b-a669-d07bb196e4ebid: baecb07f-ce89-4ebb-9cd9-0f7c053f944f
subfeature_v2: id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 867eeef1f90c152c463397222f5ed95f3b9c264b
workflow-type: tm+mt
source-wordcount: 347
ht-degree: 87%

---

# イベントを送信するための手順 {#additional-steps-to-send-events}

>[!BEGINSHADEBOX]

**このページ：** ストリーミング取り込みAPIにイベントをプッシュするようにデータ システムを設定して、設定したイベントが実際にJourney Optimizerに到達し、ジャーニーをトリガーするようにします。

>[!ENDSHADEBOX]

イベントを&#x200B;**[!UICONTROL ストリーミング取得 API]**&#x200B;に送信し、[!DNL Journey Optimizer] で使用するように設定するには、次の手順に従う必要があります。

1. Adobe Experience Platform API からインレット URL を取得します。 詳しくは、[ストリーミング取得 API の概要](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja){target="_blank"}を参照してください。
1. **[!UICONTROL イベント]**&#x200B;メニューのペイロードプレビューから、ペイロードをコピーします。 詳しくは、[このページ](../event/about-creating.md#define-the-payload-fields)を参照してください。

>[!IMPORTANT]
>
>イベントの要件と制限（ストリーミング、クエリサービス、バッチ取り込み）については、[ジャーニーガードレール – イベント ](../start/guardrails.md#events-g)を参照してください。

次に、コピーしたペイロードを使用してイベントをストリーミング取得 API にプッシュするデータシステムを設定する必要があります。

1. ストリーミング取得 API URL（インレットと呼びます) に対する POST API 呼び出しを設定します。
1. ストリーミング取得 API への API 呼び出しの本文（&quot;data section&quot;）で、[!DNL Journey Optimizer] からコピーしたペイロードを使用します。 以下に例を示します
1. ペイロードに存在するすべての変数を取得する場所を決定します。 例：イベントがアドレスを伝えることになっている場合、貼り付けられたペイロードには &quot;address&quot;: &quot;string&quot; と表示されます。 &quot;string&quot; は、正しい値（メッセージを送信する相手のメール）を自動的に入力する変数に置き換える必要があります。 ペイロードプレビューの&#x200B;**[!UICONTROL ヘッダー]**&#x200B;セクションでは、作業を容易にするために多くの値が自動的に入力されます。
1. 本文タイプとして &quot;application/json&quot; を選択します。
1. 「x-gw-ims-org-id」キーを使用して、ヘッダーに組織 ID を渡します。 値には、組織 ID（「XXX@AdobeOrg」）を使用します。

以下にストリーミング取得 API イベントの例を示します。

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2023-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

「data」 部分をどこに貼り付けるかを特定しやすくするために、[JSON フォーマッター](https://jsonformatter.curiousconcept.com){target="_blank"}などの JSON ビジュアライゼーションツールを使用できます。

Streaming Ingestion API のトラブルシューティングについて詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=ja){target="_blank"}を参照してください。

---
title: ジャーニーにイベントを送信するための追加手順
description: ジャーニーにイベントを送信するための追加手順を学ぶ
feature: イベント
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 84%

---

# イベントを送信するための追加手順 {#concept_xrz_n1q_y2b}

イベントを&#x200B;**[!UICONTROL ストリーミング取得 API]**&#x200B;に送信し、[!DNL Journey Optimizer] で使用するように設定するには、次の手順に従う必要があります。

1. Adobe Experience Platform API からインレット URL を取得します。詳しくは、[ストリーミング取得APIの概要](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja){target=&quot;_blank&quot;}を参照してください。
1. **[!UICONTROL イベント]**&#x200B;メニューのペイロードプレビューから、ペイロードをコピーします。詳しくは、[このページ](../event/about-creating.md#define-the-payload-fields)を参照してください。

次に、コピーしたペイロードを使用してイベントをストリーミング取得 API にプッシュするデータ システムを設定する必要があります。

1. ストリーミング取得 API URL（インレットと呼びます) に対する POST API 呼び出しを設定します。
1. ストリーミング取得 API への API 呼び出しの本文（&quot;data section&quot;）で、[!DNL Journey Optimizer] からコピーしたペイロードを使用します。以下に例を示します
1. ペイロードに存在するすべての変数を取得する場所を決定します。例：イベントがアドレスを伝えることになっている場合、貼り付けられたペイロードには &quot;address&quot;: &quot;string&quot; と表示されます。&quot;string&quot; は、正しい値（メッセージを送信する相手のメール）を自動的に入力する変数に置き換える必要があります。ペイロードプレビューの&#x200B;**[!UICONTROL ヘッダー]**&#x200B;セクションでは、作業を容易にするために多くの値が自動的に入力されます。
1. 本文タイプとして &quot;application/json&quot; を選択します。
1. &quot;x-gw-ims-org-id&quot; キーを使用して、ヘッダーに IMS 組織 ID を渡します。値には、IMS 組織 ID（&quot;XXX@AdobeOrg&quot;）を使用します。

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
            "timestamp": "2018-05-29T00:00:00.000Z",
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

「データ」部分を貼り付ける場所を特定しやすくするために、[JSONフォーマッター](https://jsonformatter.curiousconcept.com?lang=ja){target=&quot;_blank&quot;}などのJSONビジュアライゼーションツールを使用できます。

ストリーミング取得APIのトラブルシューティングについては、[Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

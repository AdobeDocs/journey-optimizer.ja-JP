---
title: ジャーニーにイベントを送信するための追加手順
description: ジャーニーにイベントを送信するための追加手順を説明します。
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 3%

---

# イベントを送信するための追加手順 {#concept_xrz_n1q_y2b}

![](../assets/do-not-localize/badge.png)

**[!UICONTROL ストリーミング取り込みAPI]**&#x200B;に送信し、[!DNL Journey Optimizer]で使用するイベントを設定するには、次の手順に従う必要があります。

1. Adobe Experience PlatformAPIからインレットURLを取得します。 詳しくは、[ストリーミング取り込みAPIの概要](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html)を参照してください。
1. ペイロードプレビューの&#x200B;**[!UICONTROL イベント]**&#x200B;メニュー内のペイロードをコピーします。 詳しくは、[このページ](../event/about-creating.md#define-the-payload-fields)を参照してください。

次に、コピーしたペイロードを使用してイベントをストリーミングインジェストAPIにプッシュするデータシステムを設定する必要があります。

1. ストリーミング取り込みAPIのURLに対するPOSTAPI呼び出しを設定します（入口と呼ばれます）。
1. [!DNL Journey Optimizer]からコピーしたペイロードを、ストリーミングインジェストAPIへのAPI呼び出しの本文(「data section」)で使用します。 以下に例を示します
1. ペイロード内のすべての変数を取得する場所を決定します。 例：イベントが住所を伝えると想定されている場合、貼り付けられたペイロードには「住所」が表示されます。&quot;string&quot;. 「string」は、メッセージの送信先の電子メールである適切な値を自動的に設定する変数に置き換える必要があります。 ペイロードプレビューの&#x200B;**[!UICONTROL Header]**&#x200B;セクションでは、作業を容易にするために予想される多くの値が自動的に入力されます。
1. 「application/json」をbodyタイプとして選択します。
1. 「x-gw-ims-org-id」キーを使用して、IMS組織IDをヘッダーで渡します。 値には、IMS組織ID(「XXX@AdobeOrg」)を使用します。

以下に、ストリーミング取り込みAPIイベントの例を示します。

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

「data」部分を貼り付ける場所の特定を容易にするために、[https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)などのJSONビジュアライゼーションツールを使用できます。

ストリーミング取り込みAPIのトラブルシューティングについては、[ページ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html)を参照してください。

---
solution: Journey Optimizer
product: journey optimizer
title: イベントを旅に送信するためのその他の手順
description: 旅にイベントを送信するためのその他の手順を説明します。
feature: Events
topic: Administration
role: Admin
level: Intermediate
exl-id: e0144151-6c54-4656-9650-b544d8e7be16
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# イベントを送信するためのその他の手順 {#additional-steps-to-send-events}

で [!DNL Journey Optimizer] 送受信 **[!UICONTROL Streaming Ingestion APIs]** するイベントを設定するには、次の手順を実行する必要があります。

1. Adobe エクスペリエンスプラットフォーム Api を利用して、入口 URL を取得します。 ストリーミングの取り込み Api ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html) について詳しくは、target = &quot;_blank&quot;} を [ 参照してください。
1. メニューの「ペイロードプレビュー **[!UICONTROL Event]** 」から、ペイロードをコピーします。 詳しくは、このページ ](../event/about-creating.md#define-the-payload-fields) を [ 参照してください。

次に、コピーしたペイロードを使用して、イベントをプッシュするデータシステムを設定して、取り込み用に使用する Api を作成する必要があります。

1. ストリーミング POST Api の URL (入口と呼ばれます) を指定して、API への POST 呼び出しを設定します。
1. API 呼び出しの body (&quot;data セクション&quot;) にコピー [!DNL Journey Optimizer] したペイロードを、ストリーミングのストリーミング用に使用します。 以下の例を参照してください。
1. ペイロードに含まれるすべての変数を取得する場所を指定します。 例: イベントがアドレスを伝達することを想定している場合は、ペーストされるペイロードに「address」: &quot;string&quot; と表示されます。 「string」を、正しい値、メッセージ送信先の電子メールアドレスの順に自動的に挿入される変数に置き換えてください。 このセクションの「ペイロードプレビュー **[!UICONTROL Header]** 」には、作業を容易にするために必要な多くの値が自動編集されています。
1. 本文の種類として「application/json」を選択します。
1. 「X gw: ims-組織 id」キーを使用して、ヘッダーに組織 ID を渡します。 値を指定するには、組織 ID (&quot;XXX@AdobeOrg&quot;) を使用します。

ここでは、ストリーミングインジェスト Api イベントの例を示します。

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

&quot;Data&quot; 部品をペーストする場所の識別を容易にするために、json フォーマッタ ](https://jsonformatter.curiousconcept.com) {target = &quot;_blank&quot;} などの json ビジュアライゼーションツール [ を使用することができます。

ストリーミングの取り込み Api のトラブルシューティングについては、「エクスペリエンスプラットフォームのドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html) 」「target = &quot;_blank&quot;}」を [ 参照してください。

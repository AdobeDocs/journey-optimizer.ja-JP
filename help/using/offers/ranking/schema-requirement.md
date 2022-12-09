---
product: experience platform
solution: Experience Platform
title: イベントキャプチャの設定
description: イベントを捕捉するようにオファースキーマを設定する方法について説明します。
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: f70ba749-f517-4e09-a381-243b21713b48
source-git-commit: 2160d52f24af50417cdcf8c6ec553b746a544c2f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# イベントキャプチャの設定 {#schema-requirements}

この時点で、次の設定を行う必要があります。

* AI モデルを作成しました。
* キャプチャするイベントの種類を指定します。「表示」をクリックして (インプレッション)、「(変換)」をクリックします。
* そして、イベントデータを収集するデータセットを指定します。

これで、オファーが表示されたとき、またはクリックされたときに、対応するイベントが、Adobe エクスペリエンス Platform Web SDK ](https://experienceleague.adobe.com/docs/experience-platform/edge/web-sdk-faq.html#what-is-adobe-experience-platform-web-sdk%3F) {target = &quot;_blank&quot;} または「MOBILE SDK」を使用して [ フィールドグループによって **[!UICONTROL Experience Event - Proposition Interactions]** 自動的にキャプチャされるようにすることができます。

「表示する」または「選択したイベント」タイプに送信するには、Adobe エクスペリエンスプラットフォームに送信されたエクスペリエンスイベントの各イベントタイプに適切な値を設定する必要があります。 JavaScript コードに実装する必要があるスキーマ要件は、次のとおりです。

## 表示するシナリオ

**イベントタイプ:** `decisioning.propositionDisplay` **Source:** web.xml/合金 ( `sendEvent command -> xdm : {eventType, interactionMixin}` ) または batch インジェスト

+++**ペイロードのサンプル:**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2020-09-26T15:52:25+00:00",
    "xdm:eventType": "decisioning.propositionDisplay",
    "https://ns.adobe.com/experience/decisioning/propositions":
    [
        {
            "xdm:items":
            [
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee4",
                },
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee5",
                }
            ],
            "xdm:id": "3cc33a7e-13ca-4b19-b25d-c816eff9a70a", //decision event id - taken from experience event for "nextBestOffer"
            "xdm:scope": "scope:12cfc3fa94281acb", //decision scope id - taken from experience event for "nextBestOffer"
        }
    ]
}
```

+++

### クリックされたシナリオ

**イベントタイプ:** `decisioning.propositionInteract` **Source:** web.xml/合金 ( `sendEvent command -> xdm : {eventType, interactionMixin}` ) または batch インジェスト

+++**ペイロードのサンプル:**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2020-09-26T15:52:25+00:00",
    "xdm:eventType": "decisioning.propositionInteract",
    "https://ns.adobe.com/experience/decisioning/propositions":
    [
        {
            "xdm:items":
            [
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee4"
                },
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee5"
                },
            ],
            "xdm:id": "3cc33a7e-13ca-4b19-b25d-c816eff9a70a", //decision event id
            "xdm:scope": "scope:12cfc3fa94281acb", //decision scope id
        }
    ]
}
```

+++

<!--
## Using a ranking strategy {#using-ranking}

To use the ranking strategy you created above, follow the steps below:

Once a ranking strategy has been created, you can assign it to a placement in a decision. For more on this, see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md).

1. Create a decision.
1. Add a placement.
1. Add a collection.
1. Choose to rank offers by AI ranking (select it from the drop-down list).
1. Click Add ranking.
1. Select the ranking strategy that you created. All the details of the ranking strategy are displayed.
1. Click Next to confirm.
1. Save your decision.

It is now ready to be used in a decision to rank eligible offers for a placement (see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md)).
-->

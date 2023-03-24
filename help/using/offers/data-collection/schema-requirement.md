---
product: experience platform
solution: Experience Platform
title: イベントキャプチャの設定
description: イベントをキャプチャするためのオファースキーマの設定方法を学ぶ
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: f70ba749-f517-4e09-a381-243b21713b48
source-git-commit: b06b545d377fcd1ffe6ed218badeb94c1bb85ef2
workflow-type: ht
source-wordcount: '206'
ht-degree: 100%

---

# データ収集の設定 {#schema-requirements}

<!--To send in feedback data, you must define how the experience events will be captured.-->

決定イベントタイプ以外のイベントタイプに関するフィードバックを取得できるようにするには、Adobe Experience Platform に送信される&#x200B;**エクスペリエンスイベント**&#x200B;で、各イベントタイプに正しい値を設定する必要があります。

イベントタイプごとに、データセットで使用されるスキーマに、**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**&#x200B;フィールドグループが関連付けられていることを確認してください。[詳細情報](create-dataset.md)

JavaScript コードに実装する必要があるスキーマ要件は、以下のとおりです。

>[!NOTE]
>
>決定イベントは意思決定管理により自動的に生成され、自動生成される **[!UICONTROL ODE DecisionEvents]** データセット<!--to check-->に配置されるので、これらのイベントを送信する必要はありません。

## インプレッションの追跡

イベントタイプとソースが次のようになっていることを確認します。

**エクスペリエンスイベントタイプ：** `decisioning.propositionDisplay`
**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取り込み
+++**サンプルペイロード：**

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

## クリックの追跡

イベントタイプとソースが次のようになっていることを確認します。

**エクスペリエンスイベントタイプ：** `decisioning.propositionInteract`
**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取り込み
+++**サンプルペイロード：**

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

## カスタムイベントの追跡

カスタムイベントの場合、データセットで使用されるスキーマには、**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**&#x200B;フィールドグループも関連付けられている必要がありますが、これらのイベントのタグ付けに使用する必要があるエクスペリエンスイベントタイプに関する特定の要件はありません。

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

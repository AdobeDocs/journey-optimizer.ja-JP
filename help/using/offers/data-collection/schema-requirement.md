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
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 9%

---

# データ収集の設定 {#schema-requirements}

<!--To send in feedback data, you must define how the experience events will be captured.-->

判定イベント以外のイベントタイプに関するフィードバックを得るには、 **エクスペリエンスイベント** Adobe Experience Platformに送られる

各イベントタイプで、データセットで使用されるスキーマに **[!UICONTROL エクスペリエンスイベント — 提案インタラクション]** 関連付けられているフィールドグループ。 [詳細情報](create-dataset.md)

JavaScript コードに実装する必要があるスキーマ要件を以下に示します。

>[!NOTE]
>
>決定管理はこれらのイベントを自動的に生成し、それらを **[!UICONTROL ODE DecisionEvents]** データセット<!--to check--> 自動生成された

## インプレッションの追跡

イベントタイプとソースが次のようになっていることを確認します。

**エクスペリエンスのイベントタイプ：** `decisioning.propositionDisplay`
**ソース：** Web.sdk/Alloy.js (`sendEvent command -> xdm : {eventType, interactionMixin}`) またはバッチ取得
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

**エクスペリエンスのイベントタイプ：** `decisioning.propositionInteract`
**ソース：** Web.sdk/Alloy.js (`sendEvent command -> xdm : {eventType, interactionMixin}`) またはバッチ取得
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

カスタムイベントの場合、データセットで使用されるスキーマにも **[!UICONTROL エクスペリエンスイベント — 提案インタラクション]** フィールドグループに関連付けられていますが、これらのイベントのタグ付けに使用する必要があるエクスペリエンスイベントタイプに関する特定の要件はありません。

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

---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: イベントキャプチャの設定
description: イベントをキャプチャするためのオファースキーマの設定方法を学ぶ
badge: label="レガシー" type="Informative"
feature: Ranking, Datasets, Decision Management
role: Developer
level: Experienced
exl-id: f70ba749-f517-4e09-a381-243b21713b48
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/DhaXO7sS2zR9iewgoQjrN5ptYNpYSt97e-hflU2iq7c
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2id: ad78185d-8f79-40ad-9bad-cbde74af74ee
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 307
ht-degree: 94%

---

# データ収集の設定 {#schema-requirements}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

決定イベントタイプ以外のイベントタイプに関するフィードバックを取得できるようにするには、Adobe Experience Platform に送信される&#x200B;**エクスペリエンスイベント**&#x200B;で、各イベントタイプに正しい値を設定する必要があります。

>[!CAUTION]
>
>イベントタイプごとに、データセットで使用されるスキーマに、**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**&#x200B;フィールドグループが関連付けられていることを確認してください。 [詳細情報](create-dataset.md)

JavaScript コードに実装する必要があるスキーマ要件は、以下のとおりです。

>[!NOTE]
>
>決定イベントは意思決定管理により自動的に生成され、自動生成される **[!UICONTROL ODE DecisionEvents]** データセット<!--to check-->に配置されるので、これらのイベントを送信する必要はありません。

## インプレッションの追跡 {#track-impressions}

イベントタイプとソースが次のようになっていることを確認します。

**エクスペリエンスイベントの種類：** `decisioning.propositionDisplay`
**Source:** Web.sdk/Alloy.js （`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取得
+++**サンプルペイロード：**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2023-09-26T15:52:25+00:00",
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

## クリックの追跡 {#track-clicks}

イベントタイプとソースが次のようになっていることを確認します。

**エクスペリエンスイベントの種類：** `decisioning.propositionInteract`
**Source:** Web.sdk/Alloy.js （`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取得
+++**サンプルペイロード：**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2023-09-26T15:52:25+00:00",
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

## カスタムイベントの追跡 {#track-custom-events}

カスタムイベントの場合、データセットで使用されるスキーマには、**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**&#x200B;フィールドグループも関連付けられている必要がありますが、これらのイベントのタグ付けに使用する必要があるエクスペリエンスイベントタイプに関する特定の要件はありません。

>[!NOTE]
>
>[フリークエンシーキャップ](../offer-library/add-constraints.md#capping)でカスタムイベントを考慮するには、次の 2 つの Edge データ収集エンドポイントのいずれかにエクスペリエンスイベントを送信して、エクスペリエンスイベントを Adobe Experience Platform エンドポイントに接続する必要があります。
>
>* POST /ee/v2/interact
>* POST /ee/v2/collect
>
>[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} または [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html?lang=ja){target="_blank"} を使用している場合、接続は自動的に行われます。

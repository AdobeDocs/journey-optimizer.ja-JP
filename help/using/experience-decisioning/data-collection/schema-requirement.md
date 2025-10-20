---
product: experience platform
solution: Experience Platform
title: イベントキャプチャの設定
description: イベントをキャプチャするためのオファースキーマの設定方法を学ぶ
feature: Ranking, Datasets, Decision Management
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: ce3a2c33-c15b-436f-90b1-7373d7b2b1ca
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 100%

---

# データ収集の設定 {#schema-requirements}

決定イベントタイプ以外のイベントタイプに関するフィードバックを取得できるようにするには、Adobe Experience Platform に送信される&#x200B;**エクスペリエンスイベント**&#x200B;で、各イベントタイプに正しい値を設定する必要があります。

>[!CAUTION]
>
>イベントタイプごとに、データセットで使用されるスキーマに、**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**&#x200B;フィールドグループが関連付けられていることを確認してください。[詳細情報](create-dataset.md)

JavaScript コードに実装する必要があるスキーマ要件は、以下のとおりです。

>[!NOTE]
>
>決定イベントは意思決定管理により自動的に生成され、自動生成される **[!UICONTROL ODE DecisionEvents]** データセット<!--to check-->に配置されるので、これらのイベントを送信する必要はありません。

## インプレッションの追跡 {#track-impressions}

イベントタイプとソースが次のようになっていることを確認します。

**エクスペリエンスイベントタイプ：** `decisioning.propositionDisplay`
**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取り込み
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

**エクスペリエンスイベントタイプ：** `decisioning.propositionInteract`
**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取り込み
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
>[キャップ](../items.md#capping)でカスタムイベントを考慮するには、次の 2 つの Edge データ収集エンドポイントのいずれかにエクスペリエンスイベントを送信して、エクスペリエンスイベントを Adobe Experience Platform エンドポイントに接続する必要があります。
>
>* POST /ee/v2/interact
>* POST /ee/v2/collect
>
>[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} または [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html?lang=ja){target="_blank"} を使用している場合、接続は自動的に行われます。

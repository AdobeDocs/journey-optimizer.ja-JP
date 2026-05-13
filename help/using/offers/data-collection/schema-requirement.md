---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: イベントキャプチャの設定
description: イベントをキャプチャするようにオファースキーマを設定する方法について説明します
badge: label="レガシー" type="Informative"
feature: Ranking, Datasets, Decision Management
role: Developer
level: Experienced
exl-id: f70ba749-f517-4e09-a381-243b21713b48
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/DhaXO7sS2zR9iewgoQjrN5ptYNpYSt97e-hflU2iq7c
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: e08599ea-8888-4294-ba74-3ba0a7762a46id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: acc16deb-1d7f-4ec9-9ce3-6cdf355afde6
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 307
ht-degree: 0%

---

# データ収集の設定 {#schema-requirements}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

決定イベント以外のイベントタイプに関するフィードバックを取得するには、Adobe Experience Platformに送信される&#x200B;**エクスペリエンスイベント**&#x200B;で、各イベントタイプに正しい値を設定する必要があります。

>[!CAUTION]
>
>各イベントタイプについて、データセットで使用されるスキーマに&#x200B;**[!UICONTROL エクスペリエンスイベント – 提案インタラクション]** フィールドグループが関連付けられていることを確認します。 [詳細情報](create-dataset.md)

JavaScript コードに実装する必要があるスキーマ要件を以下に示します。

>[!NOTE]
>
>決定管理はこれらのイベントを自動的に生成し、自動生成される&#x200B;**[!UICONTROL ODE DecisionEvents]** データセット <!--to check-->に入れるので、決定イベントを送信する必要はありません。

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

カスタムイベントの場合、データセットで使用されるスキーマには、**[!UICONTROL エクスペリエンスイベント – 提案インタラクション]** フィールドグループも関連付ける必要がありますが、これらのイベントのタグ付けに使用する必要があるエクスペリエンスイベントタイプに関する特定の要件はありません。

>[!NOTE]
>
>カスタムイベントを[頻度キャップ ](../offer-library/add-constraints.md#capping)で考慮するには、エクスペリエンスイベントを次の2つのAdobe Experience Platform データコレクションエンドポイントのいずれかに送信して、Edge エンドポイントに接続する必要があります。
>
>* POST /ee/v2/interact
>* POST /ee/v2/collect
>
>[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html){target="_blank"}または[Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html){target="_blank"}を使用している場合、接続は自動的に行われます。

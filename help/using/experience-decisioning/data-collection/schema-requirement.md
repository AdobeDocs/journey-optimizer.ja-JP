---
solution: Journey Optimizer
product: Journey Optimizer
title: イベントキャプチャの設定
description: イベントをキャプチャするためのオファースキーマの設定方法を学ぶ
feature: Ranking, Datasets, Decisioning
role: Developer
level: Experienced
exl-id: ce3a2c33-c15b-436f-90b1-7373d7b2b1ca
version: Journey Orchestration
source-git-commit: d7d9c371f4b0d8b4ea51e1f23eb9a2f665711fce
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%

---

# データ収集の設定 {#schema-requirements}

決定イベントタイプ以外のイベントタイプに関するフィードバックを取得できるようにするには、Adobe Experience Platform に送信される&#x200B;**エクスペリエンスイベント**&#x200B;で、各イベントタイプに正しい値を設定する必要があります。

>[!CAUTION]
>
>イベントタイプごとに、データセットで使用されるスキーマに、**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**&#x200B;フィールドグループが関連付けられていることを確認してください。<!--[Learn more](create-dataset.md)-->

JavaScript コードに実装する必要があるスキーマ要件は、以下のとおりです。

## インプレッションの追跡 {#track-impressions}

次のフィールドが正しく設定されていることを確認します。

**エクスペリエンスイベントタイプ：**`decisioning.propositionDisplay`

**propositionEventType：**`_experience.decisioning.propositionEventType.display`

**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取り込み

+++**サンプルペイロード：**

```json
{
  "_experience": {
    "decisioning": {
      "propositionEventType": {
        "display": 1
      },
      "proposition": [
        {
          "items": [
            {
              "itemSelection": {
                "rankingDetail": {
                  "algorithmID": "RANDOM",
                  "strategyID": "1YYKhS4MImWqIBrpudMIf4",
                  "trafficType": "random",
                  "step": "aiModel"
                },
                "selectionDetail": {
                  "selectionType": "selectionStrategy",
                  "strategyName": "not a real selection strategy",
                  "strategyID": "dps:selection-strategy:1b630b32da42125a",
                  "version": "35a6b5b1-62ff-4a4b-94cd-96852a59d89a"
                }
              },
              "name": "not a real offer",
              "id": "dps:14c7468e7f6271ff8023748a1146d11f05f77b7fc1368081:1b630a7d8d9f2g4j",
              "score": 0.9765416360350985
            }
          ],
          "scopeDetails": {
            "decisionPolicy": {
              "id": "01c3ad3d-6d41-4013-a88f-5a4975579179"
            },
            "decisionProvider": "EXD",
            "placement": {
              "id": "a99d6b1e-5930-4ba6-hd64-17a14bb15032#farouk-img-test"
            },
            "correlationID": "28ca161e-552c-464e-dh37-bc38d4ce944b-0"
          },
          "scope": "a99d6b1e-5930-4ba6-hd64-17a14bb15032#farouk-img-test",
          "id": "86fb8f37-0498-4533-9dab-c206690c1f67"
        }
      ],
      "exdRequestID": "edb61199-ef92-46c8-adc5-f622df5b9078"
    }
  },
  "eventType": "decisioning.propositionDisplay",
  "_id": "04b5384e-c09c-4df8-b6f0-7c476a51b219",
  "timestamp": "2025-10-07T20:22:00Z"
}
```

+++

## クリックの追跡 {#track-clicks}

次のフィールドが正しく設定されていることを確認します。

**エクスペリエンスイベントタイプ：**`decisioning.propositionInteract`

**propositionEventType：**`_experience.decisioning.propositionEventType.interact`

**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取り込み

提案内の各オファーには、アドビで生成される一意の ID であるトラッキングトークンが含まれます。このトークンは、対応するクリックイベントまたはインプレッションイベントで、受信したとおりに（変更せずに）渡す必要があります。一致するトラッキングトークンにより、アドビではユーザーアクションを正しいオファーの決定に正確に関連付けることができ、ダウンストリームレポートと AI ベースの最適化が可能になります。

>[!CAUTION]
>
>クリックを追跡する際に `propositionAction.tokens` フィールドにトラッキングトークンを渡さないと、クリックイベントは対応するオファーに適切に関連付けられません。これにより、トラッキングデータが不完全になり、レポートや AI ベースのランキング最適化に悪影響を与えます。クリックの追跡の実装には常に、提案からのトラッキングトークンを含めてください。

+++**サンプルペイロード：**

```json
{
  "_experience": {
    "decisioning": {
      "propositionEventType": {
        "interact": 1
      },
      "propositionAction": {
        "tokens": [
          "Vx9fwWXmp6/kyYRVOUZWEQ"
        ]
      },
      "proposition": [
        {
          "items": [
            {
              "itemSelection": {
                "rankingDetail": {
                  "algorithmID": "RANDOM",
                  "strategyID": "1YYKhS4MImWqIBrpudMIf4",
                  "trafficType": "random",
                  "step": "aiModel"
                },
                "selectionDetail": {
                  "selectionType": "selectionStrategy",
                  "strategyName": "not a real selection strategy",
                  "strategyID": "dps:selection-strategy:1b630b32da42125a",
                  "version": "35a6b5b1-62ff-4a4b-94cd-96852a59d89a"
                }
              },
              "name": "not a real offer",
              "id": "dps:14c7468e7f6271ff8023748a1146d11f05f77b7fc1368081:1b630a7d8d9f2g4j",
              "score": 0.9765416360350985
            }
          ],
          "scopeDetails": {
            "decisionPolicy": {
              "id": "01c3ad3d-6d41-4013-a88f-5a4975579179"
            },
            "decisionProvider": "EXD",
            "placement": {
              "id": "a99d6b1e-5930-4ba6-hd64-17a14bb15032#farouk-img-test"
            },
            "correlationID": "28ca161e-552c-464e-dh37-bc38d4ce944b-0"
          },
          "scope": "a99d6b1e-5930-4ba6-hd64-17a14bb15032#farouk-img-test",
          "id": "86fb8f37-0498-4533-9dab-c206690c1f67"
        }
      ],
      "exdRequestID": "edb61199-ef92-46c8-adc5-f622df5b9078"
    }
  },
  "eventType": "decisioning.propositionInteract",
  "_id": "04b5384e-c09c-4df8-b6f0-7c476a51b765",
  "timestamp": "2025-10-07T20:50:00Z"
}
```

+++

## カスタムイベントの追跡 {#track-custom-events}

カスタムイベントの場合、データセットで使用されるスキーマには、**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**&#x200B;フィールドグループも関連付けられている必要がありますが、これらのイベントのタグ付けに使用する必要があるエクスペリエンスイベントタイプに関する特定の要件はありません。

<!--
>[!NOTE]
>
>To have your custom events accounted for in [capping](../items.md#capping), you need to connect the experience event to Adobe Experience Platform endpoints by sending it to either one of these two Edge data collection endpoints:
>
>* POST /ee/v2/interact
>* POST /ee/v2/collect
>
>If you are using the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} or [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html?lang=ja){target="_blank"}, the connection is made automatically.
-->

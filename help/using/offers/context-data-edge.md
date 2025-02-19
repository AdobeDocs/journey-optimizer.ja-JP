---
product: experience platform
solution: Experience Platform
title: コンテキストデータとEdge Decisioning リクエスト
description: Edge Decisioning リクエストでコンテキストデータを渡す方法を説明します。
feature: Decision Management
role: Developer, Data Engineer
level: Experienced
source-git-commit: 9b66f4871d8b539bf0201b2974590672205a3243
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 1%

---


# コンテキストデータとEdge Decisioning リクエスト {#edge}

この節では、Edge Decisioning リクエストでコンテキストデータを渡し、それらを実施要件ルールで使用する方法について説明します。 顧客が使用しているデバイスのタイプに基づいてパーソナライズされたオファーを配信する方法を示す、エンドツーエンドのユースケースを見ていきます。

このユースケースには、いくつかの重要な手順が含まれます。

1. [ 前提条件の設定 ](#prerequisites)：リクエストでコンテキストデータを渡すために必要なすべての手順が完了していることを確認します。
1. [ 実施要件ルールの UEE コンテキストデータ ](#rule): ユーザーのデバイスタイプに基づいて表示するオファーを決定するルールを作成します。
1. [ デバイス固有のオファーの設計 ](#offers)：デバイスタイプごとにカスタマイズされたオファーを作成し、対応するルールにリンクします。
1. [ オファーコレクションの作成 ](#collection)：すべてのオファーを静的なコレクションにグループ化します。
1. [ 決定の設定 ](#decision)：オファー決定エンジンを活用する新しい決定を作成し、デバイスタイプに基づいて、ユーザーに提示する最適なオファーを選択します。
1. [Edge Decisioning リクエストでコンテキストデータを渡す ](#request):API リクエストを通じてコンテキストデータを渡し、適切なオファーを取得してユーザーに提示します。

>[!BEGINSHADEBOX]

さらに進むには、コンテキストデータを **ランキング式** に活用するか、動的に **オファー表示域をパーソナライズ** することもできます。 例えば、1 つのオファーを作成し、パーソナライゼーションフィールドを使用して、コンテキストデータに基づいて表示域を適応させることができます。 例えば、ユーザーが iphone を使用している場合は特定の画像を表示し、ipad ユーザー用には別の画像を表示します。 詳しくは、次の節を参照してください。

* [ランキング式 – コンテキストデータに基づいてオファーをブースト](../offers/ranking/create-ranking-formulas.md#context-data)
* [コンテキストデータに基づいた表示域のパーソナライズ](../offers/offer-library/add-representations.md#context-data)

>[!ENDSHADEBOX]

## Edge Decisioning リクエストでコンテキストデータを渡すための前提条件 {#prerequisites}

Decisioning API を使用してかなり自由なフォーマットでコンテキストを渡すのではなく、Edge Decisioning コンテキストペイロードは XDM Experience Event に準拠している必要があります。 これを行うには、データ収集に使用される「XDM エクスペリエンスイベント」の一部としてコンテキストを定義する必要があります。

1. エクスペリエンスイベントスキーマを定義します。 このユースケースでは、「オファーコンテキスト」スキーマが作成され、オファーコンテキストフィールドが「オファーコンテキスト」フィールドグループの一部になります。 実際には、フィールドグループは、「Edge Collection Network」データストリームに関連付けられたデータ収集に使用されるエクスペリエンスイベントスキーマに追加されます。

   >[!NOTE]
   >
   >オファーコンテキストエクスペリエンスイベントスキーマは、プライマリ ID として「CUSTOMER_ID」フィールドを使用する、プロファイルの一部である必要があります。

   この例では、「Offer Context」フィールドグループには、language と deviceType の 2 つのプロパティがあります。 これらのプロパティは、オファーのランキングと実施要件ルールで使用されます。

   ![](assets/context-edge-xdm.png){width="60%" align="center" zoomable="yes"}

   Adobe Experience Platform [Experience Data Model （XDM）ガイド）でスキーマの操作方法を説明し ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home){target="_blank"} す。

1. データセット（ここでは「オファーコンテキスト」）を作成し、プロファイルに対して有効になっていることを確認します。

1. **[!UICONTROL データ収集]**/ **[!UICONTROL データストリーム]** メニューから新しいデータストリームを作成します。 Adobe Experience Platformでデータストリームを作成および設定する方法を学ぶ [ データストリームガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure){target="_blank"}

   ここでは、「オファーコンテンツ」イベントスキーマを選択した「オファーコンテキスト」データストリームを作成しました。

   ![](assets/context-edge-datastream.png)

1. 新しく作成したデータストリームを編集し、サービスとして「Adobe Experience Platform」、イベントデータセットとして「オファーコンテキスト」を選択します。

   ![](assets/context-edge-datastream-new.png)

1. データストリームを保存し、その ID をコピーします。 この ID は、API リクエストエンドポイントで使用されます。 [API 呼び出しの作成方法を学ぶ ](#request)

   ![](assets/context-edge-datastream-copy.png)

## 実施要件ルールでのコンテキストデータの使用 {#rules}

ユーザーのデバイスタイプに基づいて表示するオファーを決定する実施要件ルールを作成します。

![](assets/context-edge-device.png)

* iphone デバイスルール：

   * ルール名：「Edge Context Rule - iphone」
   * 設定：deviceType = &#39;iphone&#39;
   * PQL構文：

     ```
     select _Any1 from xEvent where _Any1._experienceplatform.offerContextData.deviceType.equals("iphone", false)
     ```

* ipad デバイスの規則：

   * 規則名：「Edge Context Rule - ipad」
   * 設定：deviceType = &#39;ipad&#39;
   * PQL構文

     ```
     select _Any1 from xEvent where _Any1._experienceplatform.offerContextData.deviceType.equals("ipad", false)
     ```

## オファーの作成 {#offers}

デバイスタイプごとにオファーを作成し、前に作成した対応する実施要件ルールにリンクします。

* iphone ユーザー向けオファー：

   * オファー名：「Edge コンテキスト - iPhone オファーコンテンツ」
   * 関連するルール：「Edge コンテキストルール - iphone」

* ipad ユーザー向けオファー：

   * オファー名：Edge コンテキスト - iPad オファーコンテンツ :
   * 関連するルール：「Edge コンテキストルール - ipad」

さらに、フォールバックオファー（ここでは「コンテキストフォールバックコンテンツ」）を作成して、特定のデバイス条件を満たさない場合に表示します。

## コレクションへのオファーの追加 {#collection}

作成済みのオファーを、ここに「Edge Device Context」という名前の静的コレクションに追加します。 このコレクションは、オファーの決定が、顧客に提示する実施要件を満たすオファーを選択する場所になります。

![](assets/context-edge-collection.png)

## オファーの決定を作成 {#decision}

フォールバックオファーとして選択した「コンテキストフォールバック」オファーを使用し、オファー決定エンジンを活用して、デバイスタイプに応じてユーザーに提示する最適なオファーを選択する新しい決定を作成します。

![](assets/context-edge-decision.png)

>[!NOTE]
>
>さらに先に進むには、コンテキストデータをランキング式に活用して、それらを決定に割り当てます。 情報を追加

## Edge Decisioning リクエストでコンテキストデータを渡す {#request}

### エンドポイント

エンドポイントでは、以前に作成した [datastream](#prerequisites) の ID を使用します。

`https://edge.adobedc.net/ee/irl1/v1/interact?configId=f3c47f2a-c484-4908-87a5-a82b55039e22`

### ペイロード

次に、コンテキストデータを渡すリクエストの例を示します。

* デバイスのタイプに関する情報は、`xdm:ContextData` ノードに渡されます。
* `decisionScopes` ノードで、以前に設定した [ オファーの決定 ](#decision) の決定範囲をコピーして貼り付けます。

  +++決定範囲の取得先

  ![](assets/context-edge-copy-scope.png)

+++

```
{
	"events": [{
		"xdm": {
			"identityMap": {
				"customerId": [{
					"id": "0000158216",
					"authenticatedState": "authenticated",
					"primary": true
				}]
			},
			"_experienceplatform": {
				"identity": {
					"core": {
						"customerId": "0000158216"
					}
				},
                "offerContextData" : {
                    "language" : "NL",
                    "deviceType" : "iphone"
                }
			}
		}
	}],
	"query": {
		"personalization": {
			"decisionScopes": ["eyJ4ZG06YWN0aXZpdHlJZCI6Inhjb3JlOm9mZmVyLWFjdGl2aXR5OjE3M2I1MGM5Mjg0ZGQ4NzkiLCJ4ZG06cGxhY2VtZW50SWQiOiJ4Y29yZTpvZmZlci1wbGFjZW1lbnQ6MTZhMzQxZWQ4ZDYyMzc2MSJ9"]
		}
	}
}
```

### 応答

応答の例を次に示します。

```
{
    "requestId": "14a2d3f5-a6fa-494e-b42c-cc65a845284a",
    "handle": [
        {
            "payload": [
                {
                    "id": "1eafc831-4819-4800-8e25-c9e9f0838e09",
                    "scope": "eyJ4ZG06YWN0aXZpdHlJZCI6Inhjb3JlOm9mZmVyLWFjdGl2aXR5OjE3M2I1MGM5Mjg0ZGQ4NzkiLCJ4ZG06cGxhY2VtZW50SWQiOiJ4Y29yZTpvZmZlci1wbGFjZW1lbnQ6MTZhMzQxZWQ4ZDYyMzc2MSJ9",
                    "activity": {
                        "id": "xcore:offer-activity:173b50c9284dd879",
                        "etag": "1",
                        "name": "Edge Device Context"
                    },
                    "placement": {
                        "id": "xcore:offer-placement:16a341ed8d623761",
                        "etag": "1",
                        "name": "HIB",
                        "channel": "https://ns.adobe.com/xdm/channel-types/mobile",
                        "componentType": "https://ns.adobe.com/experience/offer-management/content-component-json"
                    },
                    "items": [
                        {
                            "id": "xcore:personalized-offer:173b4e05676d87f5",
                            "etag": "3",
                            "name": "Edge Context - iPhone Offer",
                            "priority": 0,
                            "schema": "https://ns.adobe.com/experience/offer-management/content-component-json",
                            "data": {
                                "id": "xcore:personalized-offer:173b4e05676d87f5",
                                "format": "application/json",
                                "language": [
                                    "en-gb"
                                ],
                                "content": "{\n    \"name\" : \"iphone offer\"\n}"
                            }
                        }
                    ]
                }
            ],
            "type": "personalization:decisions",
            "eventIndex": 0
        },
        {
            "payload": [],
            "type": "activation:pull",
            "eventIndex": 0
        },
        {
            "payload": [],
            "type": "personalization:decisions",
            "eventIndex": 0
        },
        {
            "payload": [
                {
                    "scope": "Target",
                    "hint": "37",
                    "ttlSeconds": 1800
                },
                {
                    "scope": "AAM",
                    "hint": "6",
                    "ttlSeconds": 1800
                },
                {
                    "scope": "EdgeNetwork",
                    "hint": "irl1",
                    "ttlSeconds": 1800
                }
            ],
            "type": "locationHint:result"
        },
        {
            "payload": [
                {
                    "key": "kndctr_907075E95BF479EC0A495C73_AdobeOrg_identity",
                    "value": "CiY0MDAwMDgyMjMzNTEzNzU1OTcwMjQ0NDcyNjU1MTAyMDEwNDQ3MVIRCNnE4Y6QMRABGAEqBElSTDHwAdnE4Y6QMQ==",
                    "maxAge": 34128000
                },
                {
                    "key": "kndctr_907075E95BF479EC0A495C73_AdobeOrg_cluster",
                    "value": "irl1",
                    "maxAge": 1800
                }
            ],
            "type": "state:store"
        }
    ]
}
```

---
title: Edge Decisioning API を使用したオファーの配信
description: Adobe Experience Platform Web SDK を使用すると、API またはオファーライブラリを使用して作成した、パーソナライズされたオファーを取得およびレンダリングできます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: b02981f2c0cf74c8dba657570157709bc422d94c
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 14%

---


# Edge Decisioning API を使用したオファーの配信 {#edge-decisioning-api}

## はじめに/前提条件 {#aep-web-sdk-overview-and-prerequisites}

この [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja#video-overview) は、Adobe Experience Cloudのお客様がExperience PlatformEdge ネットワークを通じてExperience Cloud内の様々なサービスを操作できる、クライアントサイド JavaScript ライブラリです。

 Experience Platform Web SDK では、意思決定管理を含む Adobe のパーソナライゼーションソリューションのクエリをサポートしており、API またはオファーライブラリを使用して作成した、パーソナライズされたオファーを取得およびレンダリングできます。
詳しい手順については、 [オファーの作成](../../get-started/starting-offer-decisioning.md).

を使用してOffer decisioningを実装するには、次の 2 つの方法があります [Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html#video-overview). 1 つの方法は開発者を対象とし、Web サイトやプログラミングに関する知識が必要です。 もう 1 つの方法は、Adobe Experience Platformのユーザーインターフェイスを使用して、HTMLページのヘッダーで参照する小さなスクリプトのみを必要とするオファーを設定することです。

に関するドキュメントを参照してください。 [offer decisioning](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/offer-decisioning/offer-decisioning-overview.html?lang=ja#enabling-offer-decisioning) を参照してください。

>[!NOTE]
>
>現在、Adobe Experience Platform Web SDK での意思決定管理は、一部のユーザーに対する早期アクセスで利用いただけます。
この機能は、すべての IMS 組織で使用できるわけではありません。

## Adobe Experience Platform Web SDK  {#aep-web-sdk-overview-and-prerequisites}

Platform Web SDK は、次の SDK に代わるものです。

* Visitor.js
* AppMeasurement.js
* AT.js
* DIL.js

SDK は、これらのライブラリを組み合わせることができず、新しい実装です。 これを使用するには、まず次の手順に従う必要があります。

1. 組織が SDK を使用するための適切な権限を持っていることと、権限を正しく設定していることを確認します。

   <!-- For more detailed instructions, refer to the documentation on using the [Adobe Experience Platform Web SDK](). -->

1. [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html?lang=ja) をクリックします。

1. SDK のインストール. 複数の方法があり、 [SDK ページのインストール](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en). このページは、異なる実装方法で引き続き表示されます。

SDK を使用するには、 [スキーマ](../../../start/get-started-schemas.md) および [datastream](../../../start/get-started-datasets.md) 定義済み

<!-- ****TODO - Configure schema**** -->

オファーをパーソナライズするには、パーソナライゼーション/プロファイルを個別に設定する必要があります。

<!-- Refer to the [doc](www.link.com) for detailed instructions.  -->

SDK をOffer decisioning用に設定するには、次の 2 つの手順に従います。

## オプション 1 - Launch を使用したタグ拡張機能と実装のインストール

このオプションは、コーディングの経験が少ないユーザーにとって、より使いやすくなります。

1. [タグプロパティの作成](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en)

1. [ 埋め込みコードの追加](https://experienceleague.adobe.com/docs/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch-add-embed.html?lang=en)

1. 「データストリーム」ドロップダウンから設定を選択し、作成したデータストリームを使用して、Platform Web SDK 拡張機能をインストールして設定します。 詳しくは、 [拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/overview.html?lang=en).

   ![Adobe Experience Platform Web SDK](../../assets/installed-catalog-web-sdk.png)

   ![拡張機能の設定](../../assets/configure-sdk-extension.png)

1. 必要な [データ要素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en). 少なくとも、Platform Web SDK Identity Map と Platform Web SDK XDM オブジェクトデータ要素を作成する必要があります。

   ![ID マップ](../../assets/sdk-identity-map.png)

   ![XDM オブジェクト](../../assets/xdm-object.png)

1. を [ルール](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=en):

   Platform Web SDK の「イベントの送信」アクションを追加し、関連する decisionScopes をそのアクションの設定に追加します。

   ![オファーをレンダリング](../../assets/rule-render-offer.png)

   ![オファーをリクエスト](../../assets/rule-request-offer.png)

1. [作成して公開](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=en) 設定した関連するすべてのルール、データ要素、拡張機能を含むライブラリ

## オプション 2 — 事前にビルドされたスタンドアロンバージョンを使用して手動で実装

Web SDK の事前にビルドされたスタンドアロンOffer decisioningを使用してインストールを使用するために必要な手順を次に示します。 このガイドは、SDK を初めて実装する場合を想定しているので、すべての手順が適用されない場合があります。 このガイドは、開発エクスペリエンスも前提としています。

オプション 2 から次の JavaScript スニペットを含めます。にあらかじめ組み込まれているスタンドアロンバージョン [このページ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en) 内 `<head>` 」セクションに表示されるHTMLページの

```
javascript
    <script>
        !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
        []).push(o),n[o]=function(){var u=arguments;return new Promise(
        function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
        (window,["alloy"]);
    </script>
    <script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.js" async></script>
```

SDK 設定をセットアップするには、Adobeアカウント内から 2 つの ID（ edgeConfigId と orgId ）が必要です。 edgeConfigId は、前提条件で設定する必要があるデータストリーム ID と同じです。

edgeConfigID/datastream ID を探すには、「データ収集」に移動し、「データストリーム」を選択します。 orgId を確認するには、自分のプロファイルに移動します。

このページの手順に従って、JavaScript で SDK を設定します。 設定関数では、必ず edgeConfigId と orgId を使用します。 このドキュメントでは、設定に存在するオプションのパラメーターについても説明します。 最終的な設定は、次のようになります。

```
javascript
    alloy("configure", {
        "edgeConfigId": "12345678-0ABC-DEF-GHIJ-KLMNOPQRSTUV",                            
        "orgId":"ABCDEFGHIJKLMNOPQRSTUVW@AdobeOrg",
        "debugEnabled": true,
        "edgeDomain": "edge.adobedc.net",
        "clickCollectionEnabled": true,
        "idMigrationEnabled": true,
        "thirdPartyCookiesEnabled": true,
        "defaultConsent":"in"  
    });
```

デバッグで使用する Debugger Chrome 拡張機能をインストールします。 これは次の場所にあります。 <https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob>

次に、デバッガー内でアカウントにログインします。 次に、「ログ」に移動し、正しいワークスペースに接続されていることを確認します。 次に、オファーから base64 エンコードされたバージョンの決定範囲をコピーします。

Web サイトの編集時に、設定および `sendEvent` 関数を使用して、判定範囲をAdobeに送信します。

**例**:

```
javascript
    alloy("sendEvent", {
        "decisionScopes": 
        [
        "eyJ4ZG06YWN0aXZpdHlJZCI6Inhjb3JlOm9mZmVyLWFjdGl2aXR5OjE0ZWE4MDhhZjJjZDM1NzQiLCJ4ZG06cGxhY2VtZW50SWQiOiJ4Y29yZTpvZmZlci1wbGFjZW1lbnQ6MTRjNGFmZDI2OTXXXXXXXXXX"
        ]
    });
```

応答の処理方法の例については、次を参照してください。

```
javascript
    alloy("sendEvent", {
        "decisionScopes":
        [
        "eyJ4ZG06YWN0aXZpdHlJZCI6Inhjb3JlOm9mZmVyLWFjdGl2aXR5OjE0ZWE4MDhhZjJjZDM1NzQiLCJ4ZG06cGxhY2VtZW50SWQiOiJ4Y29yZTpvZmZlci1wbGFjZW1lbnQ6MTRjNGFmZDI2OTXXXXXXXXXX"
        ]
    }).then(function(result) {
        Object.entries(result).forEach(([key, value]) => {
            console.log(key, value);
        });
    });
```

デバッガーを使用して、Edge ネットワークに正常に接続されたことを確認できます。

>[!NOTE]
>
>ログの Edge への接続が表示されない場合は、広告ブロッカーを無効にする必要がある可能性があります。

オファーの作成方法と使用されている書式に戻ります。 決定で満たされた条件に基づいて、オファーが、Adobe Experience Platform内で作成する際に指定した情報を含むユーザーに返されます。

この例では、返される JSON は次のようになります。

```
json
{
   "name":"ABC Test",
   "description":"This is a test offer", 
   "link":"https://sampletesting.online/",
   "image":"https://sample-demo-URL.png"
}
```

応答オブジェクトを処理し、必要なデータを解析します。 複数の決定範囲を 1 つで送信できるように `sendEvent` を呼び出すと、応答が少し異なるように見える場合があります。

```
json
    {
        "id": "abrxgl843d913",
        "scope": "eyJ4ZG06YWN0aXZpdHlJZCI6Inhjb3JlOm9mZmVyLWFjdGl2aXR5OjE0ZWE4MDhhZjJjZDM1NzQiLCJ4ZG06cGxhY2VtZW50SWQiOiJ4Y29yZTpvZmZlci1wbGFjZW1lbnQ6MTRjNGFmZDI2OTVlNWRmOSJ9",
        "items": 
        [
            {
                "id": "xcore:fallback-offer:14ea7f1ea26ebd0a",
                "etag": "1",
                "schema": "https://ns.adobe.com/experience/offer-management/content-component-json",
                "data": {
                    "id": "xcore:fallback-offer:14ea7f1ea26ebd0a",
                    "format": "application/json",
                    "language": [
                        "en-us"
                    ],
                    "content": "{\"name\":\"ABC Test\",\"description\":\"This is a test offer\", \"link\":\"https://sampletesting.online/\",\"image\":\"https://sample-demo-URL.png\"}"
                }
            }
        ]
    }
]
}
```

```
json
{
    "propositions": 
    [
    {
        "renderAttempted": false,
        "id": "e15ecb09-993e-4b66-93d8-0a4c77e3d913",
        "scope": "eyJ4ZG06YWN0aXZpdHlJZCI6Inhjb3JlOm9mZmVyLWFjdGl2aXR5OjE0ZWE4MDhhZjJjZDM1NzQiLCJ4ZG06cGxhY2VtZW50SWQiOiJ4Y29yZTpvZmZlci1wbGFjZW1lbnQ6MTRjNGFmZDI2OTVlNWRmOSJ9",
        "items": 
        [
            {
                "id": "xcore:fallback-offer:14ea7f1ea26ebd0a",
                "etag": "1",
                "schema": "https://ns.adobe.com/experience/offer-management/content-component-json",
                "data": {
                    "id": "xcore:fallback-offer:14ea7f1ea26ebd0a",
                    "format": "application/json",
                    "language": [
                        "en-us"
                    ],
                    "content": "{\"name\":\"Claire Hubacek Test\",\"description\":\"This is a test offer\", \"link\":\"https://sampletesting.online/\",\"image\":\"https://sample-demo-URL.png\"}"
                }
            }
        ]
    }
    ]
}
```

この例では、Web ページでオファー固有の詳細を処理して使用するために必要なパスは次のとおりです。 `result['decisions'][0]['items'][0]['data']['content']`

JS 変数を設定するには：

```
javascript
const offer = JSON.parse(result['decisions'][0]['items'][0]['data']['content']);

let offerURL = offer['link'];
let offerDescription = offer['description'];
let offerImageURL = offer['image'];

document.getElementById("offerDescription").innerHTML = offerDescription;
document.getElementById('offerImage').src = offerImageURL;
```

## 制限事項

一部のオファー制約は、現在、Capping などのモバイル Experience Edge ワークフローではサポートされていません。 「キャッピング」フィールドの値は、すべてのユーザーに対して 1 つのオファーを提示できる回数を指定します。 詳しくは、 [オファーへの制約の追加](../../offer-library/add-constraints.md#capping).

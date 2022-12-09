---
title: Edge Decisioning API を使用した提供を提供します。
description: Adobe エクスペリエンス Platform Web SDK では、Api またはオファーライブラリを使用して作成した、パーソナライズされたサービスを取得して表示することができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 4e2dc0d6-4610-4a2f-8388-bc58182b227f
source-git-commit: 6f509a2518866b8e16a16a5550c41f7fb4154642
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 0%

---

# Edge Decisioning API を使用した提供を提供します。 {#edge-decisioning-api}

## 作業の開始に関する前提条件 {#edge-overview-and-prerequisites}

[Adobe エクスペリエンス Platform WEB SDK ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html#video-overview) は、クライアントサイドの JavaScript ライブラリで、Adobe エクスペリエンスクラウドユーザーは、エクスペリエンスクラウド上の様々なサービスと利用して、経験のあるプラットフォームエッジネットワークを通じて操作することができます。

エクスペリエンスプラットフォーム Web SDK では、意志決定管理など、アドビシステムズ社の個人用設定ソリューションに対するクエリーがサポートされているので、Api またはオファーライブラリを使用して作成したパーソナライズされたサービスを取得して表示することができます。 詳細な手順については、オファー ](../../get-started/starting-offer-decisioning.md) の作成に [ 関するドキュメントを参照してください。

プラットフォーム Web SDK ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html#video-overview) を使用して意思決定管理を実装するには、 [ 2 つの方法があります。1つの方法を開発者に向けて、web サイトやプログラミングに関する知識が必要な場合もあります。 もう1つの方法は、Adobe エクスペリエンス Platform のユーザーインターフェイスを使用して、HTML ページのヘッダーで参照される小規模なスクリプトのみを設定することです。

Adobe エクスペリエンス Platform Web SDK を使用して、パーソナライズされた機能を提供する方法について詳しくは、デシジョン管理 ](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/offer-decisioning/offer-decisioning-overview.html?lang=en#enabling-offer-decisioning) の [ マニュアルを参照してください。

>[!NOTE]
>
>Adobe エクスペリエンス Platform Web SDK での意思決定管理は、1組の組織でのみ使用できます (利用が制限されます)。 この機能を活用するには、Adobe アカウントエグゼクティブにお問い合わせください。

## Adobe エクスペリエンス Platform Web SDK {#aep-web-sdk}

Platform Web SDK によって次の Sdk が置き換えられます。

* Visitor.js
* AppMeasurement.js
* AT.js
* DIL.js

SDK では、これらのライブラリは結合されていません。また、新しく導入されたものです。 この方法を使用するには、まず、次の手順を実行する必要があります。

1. SDK を使用するための適切なアクセス許可が組織に割り当てられていることと、アクセス許可が正しく設定されていることを確認してください。

   <!-- For more detailed instructions, refer to the documentation on using the [Adobe Experience Platform Web SDK](). -->

1. [Adobe エクスペリエンスクラウドのアカウントの「データコレクション」タブで、データストリーム ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html?lang=en) を設定します。

1. SDK をインストールします。 このようにするには、「SDK のインストール」ページ ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en) で [ 説明されている複数の方法があります。このページは、それぞれの異なる実装方法について継続的に使用されます。

SDK を使用するには、スキーマ ](../../../data/get-started-schemas.md) と [ 、すべてのストリーム ](../../../data/get-started-datasets.md) が [ 定義されている必要があります。

<!-- ****TODO - Configure schema**** -->

特典を個人用に設定するには、個人用設定/プロフィールを個別に設定する必要があります。

<!-- Refer to the [doc](www.link.com) for detailed instructions.  -->

意思決定管理のために SDK を設定するには、次の2つの手順のいずれかを実行します。

## オプション 1-起動を使用して、タグの拡張機能と実装をインストールします。

このオプションを使用すると、コーディング操作が少ない方がユーザーにとってわかりやすくなります。

1. [Tag プロパティの作成](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en)

1. [埋め込みコードの追加](https://experienceleague.adobe.com/docs/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch-add-embed.html?lang=en)

1. 「ストリーム」ドロップダウンから設定を選択して、作成したストリームを使用して Adobe エクスペリエンス Platform Web SDK 拡張機能をインストールして設定します。 拡張機能 ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/overview.html?lang=en) の [ マニュアルを参照してください。

   ![Adobe エクスペリエンス Platform Web SDK](../../assets/installed-catalog-web-sdk.png)

   ![拡張機能の設定](../../assets/configure-sdk-extension.png)

1. 必要な [ データエレメント ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) を作成します。 最低でも、Platform Web SDK Id マップと Platform Web SDK の XDM オブジェクトデータエレメントを作成する必要があります。

   ![Id マップ](../../assets/sdk-identity-map.png)

   ![XDM オブジェクト](../../assets/xdm-object.png)

1. ルール ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=en) を作成し [ ます。

   プラットフォーム Web SDK Send イベントアクションを追加し、そのアクションの設定に関連する decisionScopes を追加します。

   ![Render Offer](../../assets/rule-render-offer.png)

   ![依頼への申し出](../../assets/rule-request-offer.png)

1. [設定した関連するルール、データエレメントおよび拡張機能すべてを含むライブラリを作成してパブリッシュ ](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=en) します。

## オプション 2-事前に作成したスタンドアロン版を使用して手動で実装します。

ここでは、事前に作成したスタンドアロンインストールを使用して、意志決定管理を行うために必要な手順を説明します。 このガイドでは、SDK の実装を初めて実行することを前提としているので、すべての手順を実行する必要はありません。 このガイドでは、いくつかの開発環境についても説明しています。

HTML ページのセクションにある `<head>` 、オプション2から、このページ ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en) に [ 組み込まれているスタンドアロン版の JavaScript スニペットを追加します。

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

SDK 設定を設定するには、Adobe アカウント内に、edgeConfigId と orgId の2つの Id が必要です。 EdgeConfigId は、前提条件に設定しておく必要があります。これは、ID と同じです。

EdgeConfigID/ストリーム ID を検索するには、データ収集に移動して、データストリームを選択します。 OrgId を検索するには、プロフィールに移動してください。

このページの指示に従うと、JavaScript の SDK を設定することができます。 EdgeConfigId および orgId は、configuration 関数で常に使用されます。 このドキュメントでは、設定に必要なオプションのパラメーターについても説明しています。 最終的な設定は、次のようになることがあります。

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

デバッグに使用するデバッガ Chrome 拡張機能をインストールします。 これについては、以下を参照してください。 <https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob>

次に、デバッガーでアカウントにログインします。 次に、ログに移動して、適切なワークスペースに接続されていることを確認してください。 ここで、デシジョンスコープの base64 エンコードされたバージョンをオファーからコピーします。

Web サイトを編集する際には、このスクリプトと `sendEvent` その構成と、ディシジョンスコープをアドビに送信する関数を含めてください。

**次に例** を示します。

```
javascript
    alloy("sendEvent", {
        "decisionScopes": 
        [
        "eyJ4ZG06YWN0aXZpdHlJZCI6Inhjb3JlOm9mZmVyLWFjdGl2aXR5OjE0ZWE4MDhhZjJjZDM1NzQiLCJ4ZG06cGxhY2VtZW50SWQiOiJ4Y29yZTpvZmZlci1wbGFjZW1lbnQ6MTRjNGFmZDI2OTXXXXXXXXXX"
        ]
    });
```

応答を処理する方法の例については、以下を参照してください。

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

このデバッガーを使用すると、エッジネットワークに正しく接続されているかどうかを確認することができます。

>[!NOTE]
>
>ログのエッジに接続されていない場合は、ad ブロッカーを無効にする必要がある場合があります。

オファーの作成方法と使用したフォーマットについては、前の手順を参照してください。 決定に適合した条件に基づいて、Adobe エクスペリエンスプラットフォームで作成したときに指定した情報を含むオファーが返されます。

この例では、返される JSON は以下のとおりです。

```
json
{
   "name":"ABC Test",
   "description":"This is a test offer", 
   "link":"https://sampletesting.online/",
   "image":"https://sample-demo-URL.png"
}
```

Response オブジェクトを処理し、必要なデータを解析します。 1回 `sendEvent` の呼び出しで複数のデシジョンスコープを送信することができるので、応答は多少異なります。

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

次の例では、web ページで提供された詳細を処理および使用するために必要なパスは、次のようになりました。 `result['decisions'][0]['items'][0]['data']['content']`

JS 変数を設定するには、次のようにします。

```
javascript
const offer = JSON.parse(result['decisions'][0]['items'][0]['data']['content']);

let offerURL = offer['link'];
let offerDescription = offer['description'];
let offerImageURL = offer['image'];

document.getElementById("offerDescription").innerHTML = offerDescription;
document.getElementById('offerImage').src = offerImageURL;
```

## 限界

一部の提供制約は、現在モバイルエクスペリエンスのエッジワークフローによってサポートされていません。例えば、「上限」のようになります。 「上限」フィールドには、すべてのユーザーに対してオファーを表示できる回数を指定します。 詳しくは、「オファー ](../../offer-library/add-constraints.md#capping) への制約の追加」を参照してください [ 。

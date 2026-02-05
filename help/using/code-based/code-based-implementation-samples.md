---
title: コードベースの実装サンプル
description: このページでは、Journey Optimizer のコードベース機能の実装方法のサンプルを紹介します。
feature: Code-based Experiences
topic: Content Management
role: Developer
level: Experienced
exl-id: e5ae8b4e-7cd2-4a1d-b2c0-8dafd5c4cdfd
source-git-commit: 30241f4504ad82bf8ef9f6b58d3bb9482f572dae
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 81%

---

# コードベースの実装方法のサンプル {#implementation-samples}

コードベースのエクスペリエンスは、あらゆるタイプの顧客実装をサポートします。このページでは、各実装方法のサンプルを確認できます。

* [クライアントサイド](#client-side-implementation)
* [サーバーサイド](#server-side-implementation)
* [ハイブリッド](#hybrid-implementation)

>[!IMPORTANT]
>
>[このリンク](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"}から、様々なパーソナライゼーションや実験のユースケースのサンプル実装を確認できます。必要な実装手順とエンドツーエンドのパーソナライゼーションフローの仕組みをより深く理解するには、これらを確認および実行してください。

➡️ コードベースのエクスペリエンスと決定のための Web SDK の設定について詳しくは、[これらのチュートリアル](code-based-decisioning-implementations.md#tutorials)を参照してください

## クライアントサイドの実装 {#client-side-implementation}

クライアントサイドの実装がある場合、AEP Web SDK または AEP Mobile SDK のいずれかの AEP クライアント SDK を使用できます。

* [以下](#client-side-how)の手順では、サンプル **Web SDK** 実装のコードベースのエクスペリエンスジャーニーとキャンペーンによってエッジに公開されたコンテンツを取得し、パーソナライズされたコンテンツを表示するプロセスについて説明します。

* **Mobile SDK** を使用してコードベースのチャネルを実装する手順について詳しくは、[このチュートリアル](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/code-based/tutorial/){target="_blank"}を参照してください。

  >[!NOTE]
  >
  >モバイルユースケースのサンプル実装は、[iOS アプリ](https://github.com/adobe/aepsdk-messaging-ios/tree/main/TestApps/MessagingDemoAppSwiftUI){target="_blank"}と [Android アプリ](https://github.com/adobe/aepsdk-messaging-android/tree/main/code/testapp){target="_blank"}で利用できます。

### 仕組み - Web SDK {#client-side-how}

1. [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} がページに含まれています。

1. `sendEvent` コマンドを使用して[サーフェス URI](code-based-surface.md)<!--( or location/path)--> を指定し、パーソナライゼーションコンテンツを取得する必要があります。

   ```javascript
   alloy("sendEvent", {
   renderDecisions: true,
   personalization: {
       surfaces: ["#sample-json-content"],
   },
   }).then(applyPersonalization("#sample-json-content"));
   ```

1. コードベースのエクスペリエンス項目は、実装コード（[`applyPersonalization`](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/ajo/personalization-client-side/public/script.js){target="_blank"} メソッドを使用）により手動で適用され、決定に基づいて DOM を更新する必要があります。

1. コードベースのエクスペリエンスジャーニーとキャンペーンの場合、コンテンツがいつ表示されたかを示すために、表示イベントを手動で送信する必要があります。これは、`sendEvent` コマンドを使用して行われます。

   ```javascript
   function sendDisplayEvent(decision) {
     const { id, scope, scopeDetails = {} } = decision;
   
     alloy("sendEvent", {
   
       xdm: {
         eventType: "decisioning.propositionDisplay",
         _experience: {
           decisioning: {
             propositions: [
               {
                 id: id,
                 scope: scope,
                 scopeDetails: scopeDetails,
               },
             ],
           },
         },
       },
     });
   }
   ```

1. コードベースのエクスペリエンスジャーニーとキャンペーンの場合、ユーザーがいつコンテンツを操作したかを示すために、インタラクションイベントを手動で送信する必要があります。これは、`sendEvent` コマンドを使用して行われます。

   ```javascript
   function sendInteractEvent(label, proposition) {
     const { id, scope, scopeDetails = {} } = proposition;
   
     alloy("sendEvent", {
   
       xdm: {
         eventType: "decisioning.propositionInteract",
         _experience: {
           decisioning: {
             propositions: [
               {
                 id: id,
                 scope: scope,
                 scopeDetails: scopeDetails,
               },
             ],
             propositionEventType: {
               interact: 1
             },
             propositionAction: {
               id: label,
               label: label,
               tokens: proposition.items?.[0]?.characteristics?.tokens || []
             },
           },
         },
       },
     });
   }
   ```

   >[!IMPORTANT]
   >
   >`tokens` の `propositionAction` フィールドは、Adobe Journey Optimizer Decisioning で正確なトラッキングとアトリビューションを行うために重要です（AJO-D）。 これらのトークンは以下を可能にします。
   >- 決定アクティビティの適切なクリック属性
   >- 決定されたコンテンツに対するユーザーのインタラクションを正確にレポート
   >- ユーザーエンゲージメントに基づくオファーのパフォーマンスの最適化
   >
   >トークンは通常、`proposition.items[0].characteristics.tokens` にあり、決定されたコンテンツとのユーザーインタラクションをトラッキングする際には、常に含める必要があります。

### 主な所見

**Cookie**

Cookie は、ユーザー ID とクラスター情報を保持するために使用されます。クライアントサイドの実装を使用する場合、Web SDK は、リクエストのライフサイクル中にこれらの Cookie の保存と送信を自動処理します。

| Cookie | 目的 | 保存者 | 送信者 |
| ------------------------ | -------------------------------------------------------------------------- | --------- | ------- |
| kndctr_AdobeOrg_identity | ユーザー ID の詳細を含む | Web SDK | Web SDK |
| kndctr_AdobeOrg_cluster | リクエストを満たすために使用すべきエクスペリエンスエッジクラスターを示します。 | Web SDK | Web SDK |

**リクエストの配置**

提案を取得し、表示通知を送信するには、Adobe Experience Platform API へのリクエストが必要です。クライアントサイドの実装を使用する場合、Web SDK は `sendEvent` コマンドの使用時にこれらのリクエストを作成します。

| リクエスト | 作成者 |
| ---------------------------------------------- | ----------------------------------- |
| 提案を取得するためのインタラクションリクエスト | sendEvent コマンドを使用する Web SDK |
| 表示通知を送信するためのインタラクションリクエスト | sendEvent コマンドを使用する Web SDK |

**フロー図**

![](assets/code-based-client-side-implementation.png)

## サーバーサイド実装 {#server-side-implementation}

サーバーサイド実装がある場合は、いずれかの AEP Edge Network API を使用できます。

次の手順では、web ページのサンプルの Edge Network API 実装で、コードベースのエクスペリエンスジャーニーとキャンペーンによってエッジに公開されたコンテンツを取得し、パーソナライズされたコンテンツを表示するプロセスについて説明します。

### 仕組み

1. Web ページがリクエストされ、ブラウザーによって以前に保存された `kndctr_` 接頭辞付きの Cookie が含まれます。
1. アプリサーバーからページがリクエストされると、[インタラクティブデータ収集エンドポイント](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja)にイベントが送信され、パーソナライゼーションコンテンツが取得されます。このサンプルアプリでは、ヘルパーメソッドをいくつか使用して、API へのリクエストの作成と送信を簡素化します（[aepEdgeClient.js](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/common/aepEdgeClient.js){target="_blank"} を参照）。ただし、このリクエストはイベントとクエリを含むペイロード付きの単なる `POST` です。前の手順の Cookie（使用可能な場合）は、`meta>state>entries` 配列内のリクエストに含まれます。

   ```javascript
   fetch(
     "https://edge.adobedc.net/ee/v2/interact?dataStreamId=abc&requestId=123",
     {
       headers: {
         accept: "*/*",
         "accept-language": "en-US,en;q=0.9",
         "cache-control": "no-cache",
         "content-type": "text/plain; charset=UTF-8",
         pragma: "no-cache",
         "sec-fetch-dest": "empty",
         "sec-fetch-mode": "cors",
         "sec-fetch-site": "cross-site",
         "sec-gpc": "1",
         "Referrer-Policy": "strict-origin-when-cross-origin",
         Referer: "https://localhost/",
       },
       body: JSON.stringify({
         event: {
           xdm: {
             eventType: "decisioning.propositionFetch",
             web: {
               webPageDetails: {
                 URL: "https://localhost/",
               },
               webReferrer: {
                 URL: "",
               },
             },
             identityMap: {
               FPID: [
                 {
                   id: "xyz",
                   authenticatedState: "ambiguous",
                   primary: true,
                 },
               ],
             },
             timestamp: "2022-06-23T22:21:00.878Z",
           },
           data: {},
         },
         query: {
           identity: {
             fetch: ["ECID"],
           },
           personalization: {
             schemas: [
               "https://ns.adobe.com/personalization/default-content-item",
               "https://ns.adobe.com/personalization/html-content-item",
               "https://ns.adobe.com/personalization/json-content-item",
               "https://ns.adobe.com/personalization/redirect-item",
               "https://ns.adobe.com/personalization/dom-action",
             ],
             surfaces: ["web://localhost/","web://localhost/#sample-json-content"],
           },
         },
         meta: {
           state: {
             domain: "localhost",
             cookiesEnabled: true,
             entries: [
               {
                 key: "kndctr_XXX_AdobeOrg_identity",
                 value: "abc123",
               },
               {
                 key: "kndctr_XXX_AdobeOrg_cluster",
                 value: "or2",
               },
             ],
           },
         },
       }),
       method: "POST",
     }
   ).then((res) => res.json());
   ```

1. コードベースのエクスペリエンスジャーニーとキャンペーンの JSON エクスペリエンスは、応答から読み取られ、HTML 応答の生成時に使用されます。

1. コードベースのエクスペリエンスジャーニーとキャンペーンの場合、ジャーニーまたはキャンペーンのコンテンツがいつ表示されたかを示すために、実装内で表示イベントを手動で送信する必要があります。この例では、通知はリクエストのライフサイクル中にサーバーサイドで送信されます。

   ```javascript
   function sendDisplayEvent(aepEdgeClient, req, propositions, cookieEntries) {
     const address = getAddress(req);
   
     aepEdgeClient.interact(
       {
         event: {
           xdm: {
             web: {
               webPageDetails: { URL: address },
               webReferrer: { URL: "" },
             },
             timestamp: new Date().toISOString(),
             eventType: "decisioning.propositionDisplay",
             _experience: {
               decisioning: {
                 propositions: propositions.map((proposition) => {
                   const { id, scope, scopeDetails } = proposition;
   
                   return {
                     id,
                     scope,
                     scopeDetails,
                   };
                 }),
               },
             },
           },
         },
         query: { identity: { fetch: ["ECID"] } },
         meta: {
           state: {
             domain: "",
             cookiesEnabled: true,
             entries: [...cookieEntries],
           },
         },
       },
       {
         Referer: address,
       }
     );
   }
   ```

1. HTML 応答が返されると、ID とクラスターの Cookie がアプリケーションサーバーによって応答に設定されます。

### 主な所見

**Cookie**

Cookie は、ユーザー ID とクラスター情報を保持するために使用されます。サーバーサイド実装を使用する場合、アプリケーションサーバーは、リクエストのライフサイクル中にこれらの Cookie の保存と送信を処理する必要があります。

| Cookie | 目的 | 保存者 | 送信者 |
| ------------------------ | -------------------------------------------------------------------------- | ------------------ | ------------------ |
| kndctr_AdobeOrg_identity | ユーザー ID の詳細を含む | アプリケーションサーバー | アプリケーションサーバー |
| kndctr_AdobeOrg_cluster | リクエストを満たすために使用すべきエクスペリエンスエッジクラスターを示します。 | アプリケーションサーバー | アプリケーションサーバー |

**リクエストの配置**

提案を取得し、表示通知を送信するには、Adobe Experience Platform API へのリクエストが必要です。クライアントサイドの実装を使用する場合、Web SDK は `sendEvent` コマンドの使用時にこれらのリクエストを作成します。

| リクエスト | 作成者 |
| ---------------------------------------------- | ------------------------------------------------------------ |
| 提案を取得するためのインタラクションリクエスト | Adobe Experience Platform API を呼び出すアプリケーションサーバー |
| 表示通知を送信するためのインタラクションリクエスト | Adobe Experience Platform API を呼び出すアプリケーションサーバー |

**フロー図**

![](assets/code-based-server-side-implementation.png)

## ハイブリッド実装 {#hybrid-implementation}

ハイブリッド実装を使用している場合は、以下のリンクを確認してください。

* アドビのテクニカルブログ：[Adobe Experience Platform Web SDK のハイブリッドパーソナライゼーション](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"}
* SDK ドキュメント：[Web SDK と Edge Network Server API を使用したハイブリッドパーソナライゼーション](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/hybrid-personalization.html?lang=ja){target="_blank"}

## Adobe Experience Platform Assuranceを使用したEdge ネットワーク API 呼び出しのデバッグ {#debugging-edge-api-assurance}

（Web SDKやモバイル SDKを使用せずに）コードベースのエクスペリエンスにEdge Network API を直接使用する場合は、Assurance セッション ID を検証トークンヘッダーとして含めることで、Adobe Experience Platform Assuranceを使用して API 呼び出しをデバッグできます。

1. アクティブなAssurance セッションからAdobe Experience Platform Assurance セッション ID を取得するか、Assurance API を使用して作成します。

1. `x-adobe-aep-validation-token` ヘッダーをAssurance セッション ID に追加して、Assurance セッションを通じてEdge Network API リクエストをルーティングします。

   **例：**

   ```bash
   curl -v 'https://edge.adobedc.net/ee/v1/interact?configId={DATASTREAM_ID}&requestId={REQUEST_ID}' \
   --header 'Content-Type: application/json' \
   --header 'x-adobe-aep-validation-token: {ASSURANCE_SESSION_ID}' \
   --data-raw '{
       "xdm": {
         "identityMap": {
               "ECID": [
                   {
                       "id": "{ECID_VALUE}"
                   }
               ]
           }
       },
       "events": [
           {
               "xdm": {
                   "eventType": "test",
                   "timestamp": "{TIMESTAMP}"
               }
           }
       ]
   }'
   ```

1. 設定が完了したら、Assurance セッションを開き、**[!UICONTROL Edge Delivery]** ビューを選択して、リクエストペイロード、応答コンテンツ、パーソナライゼーションの提案、エラーメッセージなど、Edge Network API のリクエストと応答をリアルタイムで表示します。


<!--
## Implementation guides and tutorials {#implementation-guides}

To help you get started with implementing code-based experiences, refer to the comprehensive step-by-step tutorials below:

* **Mobile SDK implementation**: Follow [this tutorial](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/code-based/tutorial/){target="_blank"} to learn how to set up code-based experiences on mobile apps using the Adobe Experience Platform Mobile SDK.

* **Web SDK implementation**: Learn how to configure the Web SDK for decisioning and code-based experiences in [these tutorials](code-based-decisioning-implementations.md#tutorials).

* **Decisioning implementation**: To learn how to implement decisioning capabilities on a code-based campaign, follow [this use case tutorial](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/experience-decisioning-uc){target="_blank"}.-->

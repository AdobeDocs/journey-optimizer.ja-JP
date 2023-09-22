---
title: コードベースの実装サンプル
description: このページでは、Journey Optimizerのコードベースの機能の実装方法のサンプルを示します
feature: Offers
topic: Content Management
role: User
level: Experienced
hide: true
hidefromtoc: true
badge: label="ベータ版"
source-git-commit: f271aa457d2f8b7e66e58692b613d80c6e6b3adb
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 16%

---

# コードベースの実装方法のサンプル {#implementation-samples}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [コードベースのチャネルを使い始める](get-started-code-based.md)
* [コードベースの前提条件](code-based-prerequisites.md)
* **[コードベースの実装サンプル](code-based-implementation-samples.md)**
* [コードベースのエクスペリエンスの作成](create-code-based.md)

>[!ENDSHADEBOX]

コードベースのエクスペリエンスは、あらゆる種類の顧客実装をサポートします。 このページでは、各実装方法のサンプルを確認できます。

* [クライアントサイド](#client-side-implementation)
* [サーバーサイド](#server-side-implementation)
* [ハイブリッド](#hybrid-implementation)

また、次の操作も可能です [このリンク](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"} 様々なパーソナライゼーションおよび実験の使用例に関する実装例を見つけるには、を参照してください。 必要な実装手順とエンドツーエンドのパーソナライゼーションフローの仕組みをより深く理解するために、実行する必要があるパーソナライゼーションフローを確認します。

## クライアント側実装 {#client-side-implementation}

クライアント側の実装がある場合、AEP Web SDK または AEP Mobile SDK のいずれかの AEP クライアント SDK を使用できます。 以下の手順では、サンプル Web SDK 実装のコードベースのエクスペリエンスキャンペーンによってエッジに公開されたコンテンツを取得し、パーソナライズされたコンテンツを表示するプロセスを説明します。

### 仕組み

1. [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} がページに含まれています。

1. 次を使用する必要があります。 `sendEvent` 」コマンドを入力し、パーソナライゼーションコンテンツを取得するサーフェス URI を指定します。

   ```javascript
   alloy("sendEvent", {
   renderDecisions: true,
   personalization: {
       surfaces: ["#sample-json-content"],
   },
   }).then(applyPersonalization("#sample-json-content"));
   ```

1. コードベースのエクスペリエンス項目は、実装コード ( [`applyPersonalization`](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/ajo/personalization-client-side/public/script.js){target="_blank"} メソッドを参照 ) を使用して、決定に基づいて DOM を更新します。

1. コードベースのエクスペリエンスキャンペーンの場合、表示イベントを手動で送信して、コンテンツがいつ表示されたかを示す必要があります。 これは、`sendEvent` コマンドを使用して行われます。

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

### 主な観測

**Cookie**

Cookie は、ユーザー ID とクラスター情報を保持するために使用されます。クライアント側の実装を使用する場合、Web SDK は、リクエストのライフサイクル中に、これらの Cookie の保存と送信を自動的に処理します。

| Cookie | 目的 | 保存者 | 送信者 |
| ------------------------ | -------------------------------------------------------------------------- | --------- | ------- |
| kndctr_AdobeOrg_identity | ユーザー ID の詳細が含まれます | Web SDK | Web SDK |
| kndctr_AdobeOrg_cluster | リクエストを満たすために使用するエクスペリエンスエッジクラスターを示します | Web SDK | Web SDK |

**リクエストの配置**

提案を取得し、表示通知を送信するには、Adobe Experience Platform API へのリクエストが必要です。 クライアント側の実装を使用する場合、Web SDK は、 `sendEvent` コマンドを使用します。

| リクエスト | 作成者 |
| ---------------------------------------------- | ----------------------------------- |
| 提案を得るためのインタラクションリクエスト | sendEvent コマンドを使用する Web SDK |
| 表示通知を送信するインタラクションリクエスト | sendEvent コマンドを使用する Web SDK |

**フロー図**

![](assets/code-based-client-side-implementation.png)

## サーバー側実装 {#server-side-implementation}

サーバー側実装がある場合は、いずれかの AEP Edge Network API を使用できます。 次の手順では、Web ページのサンプルの Edge Network API 実装で、コードベースのエクスペリエンスキャンペーンによってエッジに公開されたコンテンツを取得し、パーソナライズされたコンテンツを表示するプロセスを説明します。

### 仕組み

1. Web ページがリクエストされ、以前に `kndctr_` が含まれます。
1. アプリサーバーからページがリクエストされると、[インタラクティブデータ収集エンドポイント](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en)にイベントが送信され、パーソナライゼーションコンテンツが取得されます。このサンプルアプリでは、API へのリクエストの作成と送信を簡単にするヘルパーメソッドを使用しています ( [aepEdgeClient.js](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/common/aepEdgeClient.js){target="_blank"}) をクリックします。 しかし、この要求は単に `POST` を、イベントとクエリを含むペイロードで置き換えます。 前の手順で作成した cookie（使用可能な場合）は、 `meta>state>entries` 配列。

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

1. コードベースのエクスペリエンスキャンペーンの JSON エクスペリエンスは、応答から読み取られ、応答の生成時にHTMLされます。
1. コードベースのエクスペリエンスキャンペーンの場合、実装時に表示イベントを手動で送信して、キャンペーンコンテンツがいつ表示されたかを示す必要があります。 この例では、リクエストのライフサイクル中に通知がサーバー側で送信されます。

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

### 主な観測

**Cookie**

Cookie は、ユーザー ID とクラスター情報を保持するために使用されます。サーバー側実装を使用する場合、アプリケーションサーバーは、リクエストのライフサイクル中に、これらの cookie の保存と送信を処理する必要があります。

| Cookie | 目的 | 保存者 | 送信者 |
| ------------------------ | -------------------------------------------------------------------------- | ------------------ | ------------------ |
| kndctr_AdobeOrg_identity | ユーザー ID の詳細が含まれます | アプリケーションサーバー | アプリケーションサーバー |
| kndctr_AdobeOrg_cluster | リクエストを満たすために使用するエクスペリエンスエッジクラスターを示します | アプリケーションサーバー | アプリケーションサーバー |

**リクエストの配置**

提案を取得し、表示通知を送信するには、Adobe Experience Platform API へのリクエストが必要です。 クライアント側の実装を使用する場合、Web SDK は、 `sendEvent` コマンドを使用します。

| リクエスト | 作成者 |
| ---------------------------------------------- | ------------------------------------------------------------ |
| 提案を得るためのインタラクションリクエスト | Adobe Experience Platform API を呼び出すアプリケーションサーバー |
| 表示通知を送信するインタラクションリクエスト | Adobe Experience Platform API を呼び出すアプリケーションサーバー |

**フロー図**

![](assets/code-based-server-side-implementation.png)

## ハイブリッド実装 {#hybrid-implementation}

ハイブリッド実装の場合は、以下のリンクを確認してください。

* Adobeのテクニカルブログ： [Adobe Experience Platform Web SDK のハイブリッドパーソナライゼーション](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"}
* SDK ドキュメント： [Web SDK と Edge Network Server API を使用したハイブリッドパーソナライゼーション](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/hybrid-personalization.html){target="_blank"}


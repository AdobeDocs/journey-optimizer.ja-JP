---
title: Experience Platform Web SDKでのAdobe Journey Optimizerの使用
description: Adobe Journey Optimizerを使用して、Experience Platform Web SDKでパーソナライズされたコンテンツをレンダリングする方法について説明します
feature: Web Channel
topic: Content Management
role: Developer
level: Intermediate
keywords: ajo;ajo web;adobe journey optimizer;renderDecisions；サーフェス；決定；提案；スコープ；スキーマ
source-git-commit: 2ab7c7b767f2f04cb4519d203d92f7f7d4611540
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 4%

---

# [!DNL Adobe Journey Optimizer]を[!DNL Experience Platform Web SDK]と共に使用

[!DNL Adobe Experience Platform] [!DNL Web SDK]は、[!DNL Adobe Journey Optimizer]で管理されているパーソナライズされたエクスペリエンスをweb チャネルに配信してレンダリングできます。 WYSIWYG エディター、[!DNL Adobe Journey Optimizer] [Web チャネル &#x200B;](get-started-web.md)、または非ビジュアル インターフェイスの[&#x200B; コードベースのエクスペリエンスチャネル &#x200B;](../code-based/get-started-code-based.md)を使用して、[!DNL Journey Optimizer Web]のキャンペーンとパーソナライゼーションエクスペリエンスを作成、アクティブ化、配信できます。

## 用語 {#terminology}

**[!UICONTROL サーフェス]**: web サーフェスは、[!DNL Adobe Journey Optimizer] エクスペリエンスコンテンツが配信されるURIによって識別されるページ上のweb ページまたは場所です。

**[!UICONTROL 提案]**: [!DNL Adobe Journey Optimizer]では、提案は[!DNL Journey Optimizer Campaign]から選択したエクスペリエンスに関連付けられます。

## [!DNL Adobe Journey Optimizer]を有効にしています {#enable-ajo}

[!DNL Adobe Journey Optimizer]の使用を開始するには、次の手順に従います。

1. [の前提条件](web-prerequisites.md)を確認します。具体的には：
   * [!DNL Adobe Experience Cloud Visual Editing Helper]を設定します。
   * [&#x200B; データストリーム &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=ja){target="_blank"}で[!DNL Adobe Journey Optimizer]を有効にします。
   * 「[!UICONTROL &#x200B; アクティブ時Edge結合ポリシー]」オプションを有効にします。

1. イベントに`renderDecisions` オプションを追加します。 Web ページサーフェスで配信されたJourney Optimizer コンテンツ提案の自動レンダリングを行うには、`renderDecisions`から`true`に設定します。

   ```javascript
   alloy("sendEvent", {
       ...,
       "renderDecisions": true
   })
   ```

1. 必要に応じて、イベント内の追加のサーフェスを指定します。 デフォルトでは、Web SDKは現在のweb ページのweb サーフェスを自動生成し、Edge Networkへのリクエストに含めます。 必要に応じて、`sendEvent` コマンドの`personalization.surfaces` オプションでこれらを指定するか、Web SDK拡張機能の対応する&#x200B;**[!UICONTROL Surfaces]** [[!UICONTROL Send event] action](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/action-types.html?lang=ja#send-event){target="_blank"}設定でこれらを指定することで、リクエストに追加のサーフェスを含めることができます。

   ```javascript
   alloy("sendEvent", {
       ...
       "personalization": {
           "surfaces": [ "web://my.site.com/about.html", "web://my.site.com/contact.html" ]
       }
   })
   ```

   ![extension-add-surface](assets/extension-add-surface.png)

   イベントサーフェスは、`query.personalization.surfaces` リクエストフィールドに含まれます。

   ```json
   {
   "events": [
       {
           "query": {
               "personalization": {
               "schemas": [
                   ...
               ],
               "decisionScopes": [
                   "__view__"
               ],
               "surfaces": [
                   "web://ajostage.weebly.com/"
               ]
               }
           },
           ...
       }
   ]
   }
   ```

1. 他のパーソナライゼーション機能と同様に、**[事前非表示スニペット &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/manage-flicker.html?lang=ja){target="_blank"}**&#x200B;を追加して、エクスペリエンスの取得中にページの特定の部分のみを非表示にすることができます。

## パーソナライズされたコンテンツのレンダリング {#rendering-personalized-content}

パーソナライズされたコンテンツのレンダリングについて詳しくは、[Adobe Experience Platform Web SDK ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/rendering-personalization-content.html?lang=ja){target="_blank"}を参照してください。

web サーフェスのAdobe Journey Optimizer提案は、`__view__`決定範囲提案と同様の方法で処理されます。 特に、`sendEvent` コマンドで`renderDecisions` オプションが`true`に設定されている場合、これらはWeb SDKによって自動的にレンダリングされます。

Adobe Journey Optimizerのコンテンツに関する提案の例：

```json
{
    "scope": "web://ajostage.weebly.com/",
    "scopeDetails": {
        "correlationID": "ccfaf19c-6360-4aea-b464-0cf924db5da7",
        "characteristics": {
            "eventToken": "eyJtZXNzYWdlRXhlY3V0aW9uIjp7Im1lc3NhZ2VFeGVjdXRpb25JRCI6ImEzNDYxYTMzLTc5MjktNGQyNS1hNmMxLTVkYzM2YWY1NzRmMyIsIm1lc3NhZ2VJRCI6ImNjZmFmMTljLTYzNjAtNGFlYS1iNDY0LTBjZjkyNGRiNWRhNyIsIm1lc3NhZ2VUeXBlIjoibWFya2V0aW5nIiwiY2FtcGFpZ25JRCI6IjEzN2JmMzllLWM1ODgtNGI1My1iODQxLTJiMWZiZDYxM2JkYiIsImNhbXBhaWduVmVyc2lvbklEIjoiMTA1NzY1MmEtZWYwNS00YjE3LWExMmUtY2FlOTQyOTFhMWFjIiwiY2FtcGFpZ25BY3Rpb25JRCI6ImViNTlmODQ4LTk5ZDYtNGE1OC05YmU4LTk4MjIxODU0NmYzNiIsIm1lc3NhZ2VQdWJsaWNhdGlvbklEIjoiYzg2NzFjZmItNDdjYS00YTVjLTg4Y2YtNzYwZDFlZjU1MzQyIn0sIm1lc3NhZ2VQcm9maWxlIjp7ImNoYW5uZWwiOnsiX2lkIjoiaHR0cHM6Ly9ucy5hZG9iZS5jb20veGRtL2NoYW5uZWxzL3dlYiIsIl90eXBlIjoiaHR0cHM6Ly9ucy5hZG9iZS5jb20veGRtL2NoYW5uZWwtdHlwZXMvd2ViIn0sIm1lc3NhZ2VQcm9maWxlSUQiOiI2YTViY2I3ZC02MmYxLTQ5NDItODRkMC02MzE5ZjM5Zjk1ZGUifX0="
        },
        "decisionProvider": "AJO",
        "activity": {
            "id": "137bf39e-c588-4b53-b841-2b1fbd613bdb#eb59f848-99d6-4a58-9be8-982218546f36"
        }
    },
    "id": "002321c0-dff5-4153-b171-a9dfb70b9750",
    "items": [
        {
            "schema": "https://ns.adobe.com/personalization/dom-action",
            "data": {
                "uiData": {
                    "tagType": "Text",
                    "actionType": "changed"
                },
                "content": "Welcome AJO!",
                "prehidingSelector": "#wsite-content > DIV:nth-of-type(2) > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(3) > FONT:nth-of-type(1) > SPAN:nth-of-type(1)",
                "type": "setHtml",
                "selector": "#wsite-content > DIV.wsite-section-wrap:eq(1) > DIV.wsite-section:eq(0) > DIV.wsite-section-content:eq(0) > DIV.container:eq(0) > DIV.wsite-section-elements:eq(0) > DIV.paragraph:eq(0) > FONT:nth-of-type(1) > SPAN:nth-of-type(1)"
            },
            "id": "0a522f66-9e6a-4ded-b1d0-e9167f103290"
        }
    ]
}
```

## デバッグ {#debugging}

Adobe Journey Optimizer パーソナライゼーションの実装をデバッグするには、[Web SDK デバッグ &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/debugging.html?lang=ja){target="_blank"}を使用します。 [[!DNL Adobe Experience Platform Assurance]](https://developer.adobe.com/client-sdks/documentation/platform-assurance/)を使用してトラブルシューティングを行う場合、[!DNL Adobe Journey Optimizer]個のデバッグトレースを利用できます。 `AJO:`接頭辞を持つイベントを確認します。

![assurance-ajo-trace](assets/assurance-ajo-trace.png)

---
title: コードベースのサーフェス
description: コードベースのエクスペリエンスサーフェスとは
feature: Code-based Experiences, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
exl-id: 07ec74fb-7fbc-48c6-a8fc-f58f24a60723
TQID: https://experienceleague.adobe.com/pwEZHMppLlVIPYRsb0ZAg69tSUh0Qyia-pvqJTAmU6I
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d556b755-390a-43f0-be32-a08cf6236126id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2: id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 828
ht-degree: 0%

---

# コードベースのエクスペリエンスサーフェス {#code-based-surface}

## サーフェスとは {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_uri"
>title="コンポーネントのサーフェス URIを追加します"
>abstract="実装がWeb、iOS、Android向けでない場合、または特定のURIをターゲットにする必要がある場合は、エクスペリエンスを配信するエンティティに向かう一意のIDであるサーフェス URIを入力します。 独自の実装で使用されているものと一致するサーフェス URIを入力してください。"
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/code-based-experience/configure-code-based-channel/code-based-configuration#other" text="他のプラットフォーム用のコードベースのエクスペリエンス設定の作成"

コードベースのエクスペリエンス **サーフェス**&#x200B;は、[URI](#surface-uri)によって一意に識別される、ユーザーまたはシステムの操作のために設計された任意のエンティティです。 サーフェスは[ アプリケーション実装](code-based-prerequisites.md#implementation-prerequisites)で指定されており、[ コードベースのエクスペリエンスチャネル設定](code-based-configuration.md)で参照されているサーフェスと一致する必要があります。

サーフェスは、存在するエンティティ（タッチポイント）を持つ階層の任意のレベルのコンテナと見なすことができます。

* Web ページ、モバイルアプリ、デスクトップアプリ、大規模なエンティティ内の特定のコンテンツの場所（例：`div`）、非標準の表示パターン（キオスクやデスクトップアプリバナーなど）を指定できます。<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* また、非表示または抽象表示の目的で特定のコンテンツコンテナに拡張することもできます（例えば、サービスに配信されるJSON BLOB）。

* また、様々なクライアントサーフェス定義に一致するワイルドカードサーフェスにすることもできます（例えば、web サイトのすべてのページのヒーローイメージの場所は、web://mydomain.com/*#hero_imageのようなサーフェス URIで変換できます）。

>[!NOTE]
>
>同じサーフェスで複数のコードベースのエクスペリエンスアクションを実行している場合、エンドユーザーが複数のアクションに適格である場合に、キャンペーンまたはジャーニーの&#x200B;**[!UICONTROL 優先スコア]**&#x200B;によって、エンドユーザーに配信される内容が決定されます。 [優先度スコアの詳細](../conflict-prioritization/priority-scores.md)

## サーフェス ID {#surface-uri}

**サーフェス URI**&#x200B;は、アプリケーション内の個別のユーザーインターフェイス要素またはコンポーネントに誘導する正確な識別子として機能します。 基本的に、サーフェス URIは複数のセクションで構成されます。

1. **種類**: web、モバイルアプリ、atm、キオスク、tvcd、サービスなど
1. **プロパティ**: ページ URLまたはアプリバンドル
1. **コンテナ**：ページ/アプリアクティビティ上の場所

以下の表に、様々なデバイスのサーフェス URI定義例を示します。

**Webとモバイル**

| タイプ | URI | 効果 |
| --------- | ----------- | ------- |
| Web | `web://domain.com/path/page.html#element` | 特定のドメインの特定のページ内の個々の要素を表します。この要素は、次の例のようにラベルにすることができます：hero_banner, top_nav, menu, footer, etc. |
| iOS アプリ | `mobileapp://com.vendor.bundle/activity#element` | ボタンやその他のビュー要素など、ネイティブアプリアクティビティ内の特定の要素を表します。 |
| Android アプリ | `mobileapp://com.vendor.bundle/#element` | ネイティブアプリ内の特定の要素を表します。 |

**その他のデバイスの種類**

| タイプ | URI | 効果 |
| --------- | ----------- | ------- |
| デスクトップ | `desktop://com.vendor.bundle/#element` | ボタン、メニュー、ヒーローバナーなど、アプリケーション内の特定の要素を表します。 |
| TV アプリ | `tvcd://com.vendor.bundle/#element` | スマートテレビまたはテレビ接続デバイスアプリ内の特定の要素を表します – バンドル ID。 |
| サービス | `service://servicename/#element` | サーバーサイドプロセスまたはその他の手動エンティティを表します。 |
| キオスク | `kiosk://location/screen#element` | 簡単に追加できる潜在的な追加サーフェスタイプの例。 |
| ATM | `atm://location/screen#element` | 簡単に追加できる潜在的な追加サーフェスタイプの例。 |

**ワイルドカードサーフェス**

| タイプ | URI | 効果 |
| --------- | ----------- | ------- |
| ワイルドカード web | `wildcard:web://domain.com/*#element` | ワイルドカードサーフェス – 特定のドメインの下にある各ページの個々の要素を表します。 |
| ワイルドカード web | `wildcard:web://*domain.com/*#element` | ワイルドカードサーフェス – 「domain.com」で終わるすべてのドメインの各ページの個々の要素を表します。 |

## URI コンポジション {#uri-composition}

[!DNL Journey Optimizer]では、コードベースのエクスペリエンスチャネルは、次の2種類の顧客実装をサポートしています。

* お客様のWeb サイトの[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"}またはモバイルアプリの[Adobe Experience Platform モバイルSDK](https://developer.adobe.com/client-sdks/documentation){target="_blank"}に基づきます。
* [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"}を使用したサーバーサイドまたはハイブリッド。

>[!NOTE]
>
>実装の前提条件について詳しくは、[この節](code-based-prerequisites.md#implementation-prerequisites)を参照してください。

コードベースのエクスペリエンスを使用すると、[ サーフェス URI](#surface-uri)を使用して、[!DNL Journey Optimizer]によって一意に識別される詳細な場所<!--(such as a specific location on a page, or inside a mobile native app)-->のコンテンツを変更できます。

これらのサーフェス URIは、実装方法に応じて構成および処理されます。

* **Web/Mobile SDK**:Web/Mobile SDKは、現在のURL/アプリ IDと位置情報文字列に基づいてサーフェス URIを自動的に構成できるため、web/モバイル開発者はこれらの詳細な場所を単純な文字列として定義する必要があります。

* **Edge Network API**：完全なURIがこのタイプの実装では必要であるため、アプリ/ページ開発者は、コンテンツが消費されるフルパスと場所を含む完全なサーフェス URIを定義する必要があります。

そのため、[ コードベースのエクスペリエンスチャネル設定](code-based-configuration.md)を作成する場合、選択したプラットフォームに応じてサーフェスを指定する2つの方法があります。

* **[!UICONTROL Web]**、**[!UICONTROL iOS]**、**[!UICONTROL Android]** プラットフォームの場合、サーフェスを構成するには、**URL/アプリ ID**&#x200B;と&#x200B;**場所またはパス**&#x200B;を入力する必要があります。 [web](code-based-configuration.md#web)および[mobile](code-based-configuration.md#mobile) プラットフォームのコードベースのエクスペリエンスの設定について詳しく説明します

* プラットフォームが&#x200B;**[!UICONTROL Other]**&#x200B;の場合は、例[above](#surface-uri)のように、**サーフェス URI**&#x200B;を入力する必要があります。 [other](code-based-configuration.md#other) プラットフォームのコードベースのエクスペリエンスの設定について詳しく見る

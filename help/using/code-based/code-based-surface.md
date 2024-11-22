---
title: コードベースのサーフェス
description: コードベースのエクスペリエンスサーフェスとは
feature: Code-based Experiences, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
source-git-commit: e9181c333fb9188cdfcee3fd96c1d3bb94b8dd75
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 56%

---

# コードベースのエクスペリエンスサーフェス {#code-based-surface}

## サーフェスとは {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_uri"
>title="コンポーネント用のサーフェス URI を追加"
>abstract="実装が web、iOS、Android 向けでない場合、または特定の URI をターゲットにする必要がある場合は、サーフェス URI を入力します。これは、エクスペリエンスを配信するエンティティを指す一意の ID です。独自の実装で使用される URI と一致するサーフェス URI を入力していることを確認します。"
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/code-based-experience/configure-code-based-channel/code-based-configuration#other" text="他のプラットフォーム用のコードベースのエクスペリエンス設定の作成"

コードベースのエクスペリエンス **サーフェス** は、ユーザーまたはシステムインタラクション用に設計された任意のエンティティで、[URI](#surface-uri) によって一意に識別されます。 サーフェスは、[ アプリケーション実装 ](code-based-prerequisites.md#implementation-prerequisites) で指定され、[ コードベースのエクスペリエンスチャネル設定 ](code-based-configuration.md) で参照されるサーフェスと一致する必要があります。

サーフェスは、エンティティ（タッチポイント）が存在する階層の任意のレベルのコンテナと見なすことができます。

* Web ページ、モバイルアプリ、デスクトップアプリ、大きなエンティティ内の特定のコンテンツの場所（`div` など）または非標準の表示パターン（キオスクやデスクトップアプリのバナーなど）が考えられます。<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* また、非表示または抽象された表示を目的として、コンテンツ コンテナの特定の部分に拡張することもできます（サービスに配信される JSON BLOB など）。

* また、様々なクライアントサーフェス定義に一致するワイルドカードサーフェスにすることもできます（例えば、web サイトの各ページのヒーロー画像の場所を web://mydomain.com/*#hero_image のようなサーフェス URI に変換できます）。

## サーフェス識別子 {#surface-uri}

**サーフェス URI** は、アプリケーション内の個別のユーザーインターフェイス要素やコンポーネントに向ける正確な識別子として機能します。 基本的に、サーフェス URI は複数のセクションで構成されます。

1. **タイプ**：web、mobileapp、atm、kiosk、tvcd、service など。
1. **プロパティ**：ページ URL またはアプリバンドル
1. **コンテナ**：ページ／アプリアクティビティ上の場所

次の表に、様々なデバイスのサーフェス URI 定義の例を示します。

**Web およびモバイル**

| タイプ | URI | 説明 |
| --------- | ----------- | ------- | 
| Web | `web://domain.com/path/page.html#element` | 特定のドメインの特定のページ内の個々の要素を表します。要素は、次の例のようなラベル（hero_banner、top_nav、menu、footer など）にすることができます。 |
| iOS アプリ | `mobileapp://com.vendor.bundle/activity#element` | ボタンや他のビュー要素など、ネイティブアプリアクティビティ内の特定の要素を表します。 |
| Android アプリ | `mobileapp://com.vendor.bundle/#element` | ネイティブアプリ内の特定の要素を表します。 |

**その他のデバイスタイプ**

| タイプ | URI | 説明 |
| --------- | ----------- | ------- | 
| Desktop | `desktop://com.vendor.bundle/#element` | ボタン、メニュー、ヒーローバナーなど、アプリケーション内の特定の要素を表します。 |
| TV アプリ | `tvcd://com.vendor.bundle/#element` | スマート TV または TV 接続デバイスアプリ内の特定の要素（バンドル ID）を表します。 |
| サービス | `service://servicename/#element` | サーバーサイドのプロセスまたは他の手動エンティティを表します。 |
| キオスク | `kiosk://location/screen#element` | 容易に追加できる、潜在的な追加サーフェスタイプの例。 |
| ATM | `atm://location/screen#element` | 容易に追加できる、潜在的な追加サーフェスタイプの例。 |

**ワイルドカードサーフェス**

| タイプ | URI | 説明 |
| --------- | ----------- | ------- | 
| ワイルドカード web | `wildcard:web://domain.com/*#element` | ワイルドカードサーフェス - 特定のドメインの下の各ページの個々の要素を表します。 |
| ワイルドカード web | `wildcard:web://*domain.com/*#element` | ワイルドカードサーフェス - 「domain.com」で終わるすべてのドメインの各ページの個々の要素を表します。 |

## URI 構成 {#uri-composition}

ま [!DNL Journey Optimizer]、コードベースの Experience Channel では、次の 2 種類の顧客実装をサポートしています。

* Web サイトの [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} またはモバイルアプリの [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} に基づいています。
* [AEP Edge Networkサーバー API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja){target="_blank"} を使用したサーバーサイドまたはハイブリッド。

>[!NOTE]
>
>実装の前提条件について詳しくは、[ この節 ](code-based-prerequisites.md#implementation-prerequisites) を参照してください。

コードベースのエクスペリエンスを使用すると、詳細な場所 <!--(such as a specific location on a page, or inside a mobile native app)--> サーフェス URI を使用して [!DNL Journey Optimizer] で一意に識別される場所 [ でコンテンツを変更でき ](#surface-uri) す。

これらのサーフェス URI は、実装方法に応じて構成および処理されます。

* **Web/Mobile SDK**:Web/Mobile SDK は、現在の URL/アプリ ID と場所文字列に基づいてサーフェス URI を自動的に構成できるので、web/モバイル開発者は、これらの詳細な場所を簡単な文字列として定義する必要があります。

* **Edge NetworkAPI**: アプリまたはページの開発者は、完全なパスとコンテンツが使用される場所を含む完全なサーフェス URI を定義する必要があります。これは、このタイプの実装では完全な URI が必要なためです。

[ コードベースのエクスペリエンスチャネル設定 ](code-based-configuration.md) を作成する場合、選択したプラットフォームに従ってサーフェスを指定するには、次の 2 つの方法があります。

* **[!UICONTROL Web]**、**[!UICONTROL iOS]**、**[!UICONTROL Android]** のプラットフォームの場合は、**URL/アプリ ID** と **場所またはパス** を入力してサーフェスを構成する必要があります。 [web](code-based-configuration.md#web) および [ モバイル ](code-based-configuration.md#mobile) プラットフォームのコードベースのエクスペリエンス設定についての詳細を説明します

* プラットフォームが **[!UICONTROL その他]** の場合は、例 [ 上記 ](#surface-uri) のように、完全な **サーフェス URI** を入力する必要があります。 [ その他 ](code-based-configuration.md#other) プラットフォーム用のコードベースのエクスペリエンスの設定についての詳細

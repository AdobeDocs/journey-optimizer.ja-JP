---
title: コードベースのサーフェス
description: コードベースのエクスペリエンスサーフェスの内容について説明します
feature: Code-based Experiences, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
exl-id: 07ec74fb-7fbc-48c6-a8fc-f58f24a60723
source-git-commit: d3f15c09194a50b95107fb84d680606a468f8644
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 90%

---

# コードベースのエクスペリエンスサーフェス {#code-based-surface}

## サーフェスとは {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_uri"
>title="コンポーネント用のサーフェス URI を追加"
>abstract="実装が web、iOS、Android 向けでない場合、または特定の URI をターゲットにする必要がある場合は、サーフェス URI を入力します。これは、エクスペリエンスを配信するエンティティを指す一意の ID です。独自の実装で使用される URI と一致するサーフェス URI を入力していることを確認します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/code-based-experience/configure-code-based-channel/code-based-configuration#other" text="他のプラットフォーム用のコードベースのエクスペリエンス設定の作成"

コードベースのエクスペリエンス&#x200B;**サーフェス**&#x200B;とは、ユーザーやシステムの操作用に設計されたエンティティで、[URI](#surface-uri) によって一意に識別されます。サーフェスは、[アプリケーション実装](code-based-prerequisites.md#implementation-prerequisites)で指定され、[コードベースのエクスペリエンスチャネル設定](code-based-configuration.md)で参照されるサーフェスと一致する必要があります。

サーフェスは、エンティティ（タッチポイント）が存在する階層の任意のレベルのコンテナと見なすことができます。

* Web ページ、モバイルアプリ、デスクトップアプリ、大きなエンティティ内の特定のコンテンツの場所（`div` など）または非標準の表示パターン（キオスクやデスクトップアプリのバナーなど）が考えられます。<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* また、非表示または抽象された表示を目的として、コンテンツ コンテナの特定の部分に拡張することもできます（サービスに配信される JSON BLOB など）。

* また、様々なクライアントサーフェス定義に一致するワイルドカードサーフェスにすることもできます（例えば、web サイトの各ページのヒーロー画像の場所を web://mydomain.com/*#hero_image のようなサーフェス URI に変換できます）。

>[!NOTE]
>
>同じサーフェスで実行されているコードベースのエクスペリエンスアクションが複数ある場合、キャンペーンまたはジャーニーの **[!UICONTROL 優先度スコア]** によって、複数のアクションの対象となるエンドユーザーに配信される内容が決定されます。 [ 優先度スコアの詳細情報 ](../conflict-prioritization/priority-scores.md)

## サーフェス識別子 {#surface-uri}

**サーフェス URI** は、アプリケーション内の個別のユーザーインターフェイス要素またはコンポーネントを指す正確な識別子として機能します。基本的に、サーフェス URI は複数のセクションで構成されます。

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

[!DNL Journey Optimizer] では、コードベースのエクスペリエンスチャネルが次の 2 つのタイプの顧客実装をサポートしています。

* Web サイトの [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} またはモバイルアプリの [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} に基づきます。
* [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja){target="_blank"} を使用したサーバーサイドまたはハイブリッド。

>[!NOTE]
>
>実装の前提条件について詳しくは、[この節](code-based-prerequisites.md#implementation-prerequisites)を参照してください。

コードベースのエクスペリエンスを使用すると、[サーフェス URI](#surface-uri) を使用して [!DNL Journey Optimizer] によって一意に識別される詳細な場所<!--(such as a specific location on a page, or inside a mobile native app)-->のコンテンツを変更できます。

これらのサーフェス URI は、実装方法に応じて構成および処理されます。

* **Web／Mobile SDK**：Web／Mobile SDK は、現在の URL／アプリ ID と場所の文字列に基づいてサーフェス URI を自動的に構成できるので、web／モバイル開発者はこれらの詳細な場所を簡単な文字列として定義する必要があります。

* **Edge Network API**：このタイプの実装では完全な URI が必要なので、アプリ／ページ開発者は、コンテンツが使用される完全なパスと場所を含む完全なサーフェス URI を定義する必要があります。

このため、[コードベースのエクスペリエンスチャネル設定](code-based-configuration.md)を作成する際、選択したプラットフォームに応じてサーフェスを指定するには、次の 2 つの方法があります。

* **[!UICONTROL Web]**、**[!UICONTROL iOS]**、**[!UICONTROL Android]** プラットフォームの場合、サーフェスを構成するには、**URL／アプリ ID** と&#x200B;**場所またはパス**&#x200B;を入力する必要があります。コードベースのエクスペリエンスの設定について詳しくは、[web](code-based-configuration.md#web) プラットフォームおよび[モバイル](code-based-configuration.md#mobile)プラットフォームを参照してください。

* プラットフォームが&#x200B;**[!UICONTROL その他]**&#x200B;の場合は、[上記](#surface-uri)の例のように、完全な&#x200B;**サーフェス URI** を入力する必要があります。コードベースのエクスペリエンスの設定について詳しくは、[その他](code-based-configuration.md#other)のプラットフォームを参照してください。

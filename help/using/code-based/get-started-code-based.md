---
title: コードベースのエクスペリエンスの基本を学ぶ
description: Journey Optimizerでのコードベースのエクスペリエンスについて説明します
feature: Offers
topic: Content Management
role: User
level: Experienced
hide: true
hidefromtoc: true
badge: label="ベータ版"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 7%

---

# コードベースのチャネルを使い始める {#get-sarted-code-based}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* **[コードベースのチャネルを使い始める](get-started-code-based.md)**
* [コードベースの前提条件](code-based-prerequisites.md)
* [コードベースの実装サンプル](code-based-implementation-samples.md)
* [コードベースのエクスペリエンスの作成](create-code-based.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>コードベースのエクスペリエンスチャネルは、現在、一部のユーザーに対してのみベータ版として利用できます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。

[!DNL Journey Optimizer] を使用すると、Web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマートテレビ、キオスク、ATM、音声アシスタント、IoT デバイスなど、すべてのタッチポイントで顧客に提供するエクスペリエンスをパーソナライズおよびテストできます。

を使用 **コードベースのエクスペリエンス** 機能を使用すると、シンプルで直感的な非ビジュアルエディターを使用して、インバウンドエクスペリエンスを定義できます。 アプリや Web ページの個々のより詳細な場所で、コンテンツ全体に変更を適用する代わりに、アプリや Web ページのタイプに関係なく、特定の要素を挿入および編集できます。

<!--[!DNL Journey Optimizer] allows you to compose and deliver content on any inbound surface in a developer-focused workflow. You can leverage all the personalization capabilities, and preview what will be published. The content can be static (images, text, JSON, HTML) or dynamic (offers, decisions, recommendations). You can also insert custom content actions in your omni-channel journeys.-->

次の場合： [キャンペーンの作成](../campaigns/create-campaign.md#configure)を選択します。 **コードベースのエクスペリエンス（ベータ版）** をアクションとして追加し、基本設定を定義します。

>[!NOTE]
>
>Web エクスペリエンスを初めて作成する場合は、[こちらのセクション](code-based-prerequisites.md)に記載されている前提条件を必ず満たすようにしてください。

<!--Discover the detailed steps to create a code-based campaign in this video.-->

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="#how-it-works">
<img alt="リード" src="../assets/do-not-localize/privacy-audit.jpeg">
</a>
<div><a href="#how-it-works"><strong>仕組み</strong>
</div>
<p>
</td>
<td>
<a href="code-based-prerequisites.md">
<img alt="検証" src="../assets/do-not-localize/web-prerequisites.jpg">
</a>
<div>
<a href="code-based-prerequisites.md"><strong>前提条件</strong></a>
</div>
<p>
</td>
<td>
<a href="create-code-based.md#create-code-based-campaign">
<img alt="低頻度" src="../assets/do-not-localize/web-create.jpg">
</a>
<div>
<a href="create-code-based.md#create-code-based-campaign"><strong>コードベースのエクスペリエンスの作成</strong></a>
</div>
<p></td>
<td>
<a href="create-code-based.md#edit-code">
<img alt="検証" src="../assets/do-not-localize/web-design.jpg">
</a>
<div>
<a href="create-code-based.md#edit-code"><strong>コードを編集</strong></a>
</div>
<p>
</td>
</tr></table>



<!--[Learn how to create a code-based campaign in this video](#video)-->

## コードベースのチャネルと他のチャネルを使用する場合 {#code-based-vs-other-channels}

### コードベースのチャネルと他のチャネルの比較

他の [!DNL Journey Optimizer] チャネル？

* Web ブラウザーやモバイルアプリを通じてデジタルプロパティにアクセスできない場合は、コードベースのエクスペリエンスの使用を検討できます。その場合は、 [!DNL Journey Optimizer] [web チャネル](../web/get-started-web.md){target="_blank"} or the [!DNL Journey Optimizer] [in-app messaging](../in-app/get-started-in-app.md){target="_blank"} チャネル。

* コードベースのチャネルを [!DNL Journey Optimizer] web サイトを [web ビジュアルエディター](../web/author-web.md){target="_blank"} or if you cannot use the [browser extension](../web/web-prerequisites.md#visual-authoring-prerequisites){target="_blank"} を使用すれば、web チャネルの視覚的なオーサリングが可能になります。

* また、コードベースのチャネルを [!DNL Journey Optimizer] API ベース、ヘッドレスまたはサーバー側の実装がある場合は、Web またはアプリ内チャネルを使用します。

### コードベースのチャネルと Web チャネルの比較

Web の使用例を実行するには、Web チャネルまたはコードベースのエクスペリエンスを使用できますが、コンテキストに応じて、どちらか一方が適切です。 主な違いを次に示します。これにより、何を使用するかを十分な情報に基づいて決定できます。

**Web**
* 次を使用してコンテンツを編集： [ビジュアルエディター](../web/author-web.md){target="_blank"}.
* 必要なのは [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} implementation and the [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} extension installed on your web browser. [Learn more](../web/web-prerequisites.md){target="_blank"}
* Web チャネルを使用すると、ページ上のすべての項目を変更でき、変更に使用できる事前定義済みのアクションのリストが表示されます。 [詳細情報](../web/author-web.md){target="_blank"}
* 簡単に設定して、速く進むことができます。
* マーケティング担当者向けです。

**コードベースのエクスペリエンス**
* 次を使用してコンテンツを編集： [コードエディター](create-code-based.md#edit-code).
* コードベースのエクスペリエンスでは、によってエッジに公開されたコンテンツをサーフェスが解釈して配信できるように、実装に関する以前の開発作業が必要です。 [!DNL Journey Optimizer] を使用します。 [詳細情報](#surface-definition)
* より多くの計画が必要で、開発者が指定した内容だけを変更できます。 したがって、 パーソナライゼーションやテストのために変更が必要なサーフェス上に表示され、変更の処理に必要な実装を開発チームと協力して構築します。
* JSON コードコンテンツを使用できます。
* 開発者向けのペルソナに特化したものです。

## 仕組み {#how-it-works}

>[!CAUTION]
>
>この機能は、開発者のペルソナや経験豊富なユーザー向けです。 表面実装と初期設定が開発チームで処理される限り、マーケターはコードを記述するスキルを持ち、これを使用できます。

を使用してコンテンツを編集するには [!DNL Journey Optimizer] コードベースのエクスペリエンス機能を使用する場合は、ページやアプリを実装する必要があります。 これをおこなうには、個々の場所 ([サーフェス](#surface-definition)&quot;) コンテンツを挿入または置換する場所<!--HOW??-->.

>[!NOTE]
>
>現在、サーフェスに関連付けられているコンテンツは、HTMLまたは JSON のみです。 <!--WILL COME LATER: text, image or another format depending on the application-->

コードベースのキャンペーンを実装するための主な手順を次に示します。

1. を定義 [表面](#surface-definition)：基本的には、コードベースのエクスペリエンスを追加し、 [!DNL Journey Optimizer] このサーフェスを使用します。 [方法についてはこちらを参照](create-code-based.md#create-code-based-campaign)

1. 選択したサーフェスのコンテンツを次を使用して指定し、エクスペリエンスを構成する [!DNL Journey Optimizer] コードエディター。 [方法についてはこちらを参照](create-code-based.md#edit-code)

1. アプリ実装チームは、明示的な API または SDK 呼び出しをおこなって、「バナーテキスト」や「Recommendationsトレイ 1」などの名前付きサーフェスや、アプリケーション内の UI 関連以外の決定ポイント（「検索アルゴリズムパラメーター」など）のコンテンツを取得します。 この場合、実装チームは、返されたコンテンツをレンダリングするか、その他の方法で解釈し、それに基づいて操作する必要があります。<!--TBC with Robert - should link to a new section with API/SDK call samples-->

## サーフェスとは {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_code_based_surface"
>title="コードベースのエクスペリエンスサーフェスを定義する"
>abstract="コードベースのサーフェスとは、ユーザーやシステムの操作のために設計されたエンティティで、URI によって一意に識別されます。"

A **コードベースのエクスペリエンスサーフェス** は、ユーザーまたはシステムの操作のために設計されたエンティティです。<!--ask Robert to explain further-->は、 **URI**.

つまり、サーフェスは、存在するエンティティ（タッチポイント）を持つ任意のレベルの階層でコンテナと見なすことができます。<!--good idea to illustrate how it can be seen, but to clarify-->

* Web ページ、モバイルアプリ、デスクトップアプリ、大きなエンティティ内の特定のコンテンツの場所 ( 例えば、 `div`) または非標準の表示パターン（キオスクやデスクトップアプリのバナーなど）に置き換えることができます。<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* また、非表示または抽象表示用に、特定のコンテンツコンテナに拡張することもできます（例えば、サービスに配信される JSON BLOB）。

* また、様々なクライアントとサーフェスの定義に一致するワイルドカードサーフェスを指定することもできます ( 例えば、Web サイトの各ページのヒーロー画像の場所をweb://mydomain.com/*#hero_imageのようなサーフェス URI で変換できます )。

基本的に、サーフェス URI は複数のセクションで構成されます。
1. **タイプ**:web、mobileapp、service、kiosk、tvcd など。
1. **プロパティ**：ドメインまたはアプリバンドル
1. **パス**：ページ/アプリアクティビティ±ページ/アプリアクティビティ上の場所 <!--to clarify-->

次の表に、様々なデバイスのサーフェス URI 定義の例を示します。

| タイプ | URI | 説明 |
| --------- | ----------- | ------- |   
| Web | web://domain.com/path/page.html | Web サイトの個々のパスおよびページを表します。 |
| Web | web://domain.com/path/page.html#element | 特定のドメインの特定のページ内の個々の要素を表します。 |
| Web | web://domain.com/*#element | ワイルドカード表面 — 特定のドメインの下の各ページの個々の要素を表します。 |
| Desktop | desktop://com.vendor.bundle | 特定のデスクトップアプリケーションを表します。 |
| Desktop | desktop://com.vendor.bundle#element | ボタン、メニュー、ヒーローバナーなど、アプリ内の特定の要素を表します。 |
| iOS アプリ | ios://com.vendor.bundle | 単一のプラットフォーム向けの特定のモバイルアプリケーション ( この場合はiOSアプリ ) を表します。 |
| iOS アプリ | ios://com.vendor.bundle/activity | モバイルアプリケーション内の特定のアクティビティ（ビュー）を表します。 |
| iOS アプリ | ios://com.vendor.bundle/activity#element | ボタンや他のビュー要素など、アクティビティ内の特定の要素を表します。 |
| Android アプリ | android://com.vendor.bundle | 単一のプラットフォーム（この場合は Android アプリ）用の特定のモバイルアプリを表します。 |
| tvOS アプリ | tvos://com.vendor.bundle | 特定の tvOS アプリを表します。 |
| TV アプリ | tvcd://com.vendor.bundle | 特定のスマート TV または TV 接続デバイスアプリ — バンドル ID を表します。 |
| サービス | service://servicename | サーバー側のプロセスまたは他の手動エンティティを表します。 |
| キオスク | kiosk://location/screen | 追加が容易な潜在的な追加サーフェスタイプの例。 |
| ATM | atm://location/screen | 追加が容易な潜在的な追加サーフェスタイプの例。 |
---
title: コードベースのエクスペリエンスの基本を学ぶ
description: Journey Optimizer でのコードベースのエクスペリエンスについて学ぶ
feature: Code-based Experiences
topic: Content Management
role: User, Developer, Admin
level: Experienced
exl-id: 987de2bf-cebe-4753-98b4-01eb3fded492
source-git-commit: 3c9952f2e57c45d5bbd78d70ae7d401bc4555abe
workflow-type: tm+mt
source-wordcount: '1121'
ht-degree: 82%

---

# コードベースチャネルの基本を学ぶ {#get-sarted-code-based}

[!DNL Journey Optimizer] を使用すると、web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、音声アシスタント、IoT デバイスなど、すべてのタッチポイントで顧客に提供するエクスペリエンスをパーソナライズしてテストできます。

**コードベースのエクスペリエンス**&#x200B;機能を使用すると、シンプルで直感的な非ビジュアルエディターを使用して、インバウンドエクスペリエンスを定義できます。これにより、コンテンツ全体に変更を適用する代わりに、アプリケーションの種類に関係なく、アプリや web ページの個別のより詳細な場所で、特定の要素を挿入および編集できます。

<!--[!DNL Journey Optimizer] allows you to compose and deliver content on any inbound surface in a developer-focused workflow. You can leverage all the personalization capabilities, and preview what will be published. The content can be static (images, text, JSON, HTML) or dynamic (offers, decisions, recommendations). You can also insert custom content actions in your omni-channel journeys.-->

>[!NOTE]
>
>* コードベースのエクスペリエンスを初めて作成する場合は、 [この節](code-based-prerequisites.md).
>
>* 現在、[!DNL Journey Optimizer] では、**キャンペーン**&#x200B;を使用してコードベースエクスペリエンスのみを作成できます。
>
>>* コードベースのエクスペリエンスチャネルは、Adobeを購入した組織では使用できません **医療用盾** および **プライバシーとセキュリティシールド** アドオンサービス。

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
<a href="create-code-based.md#create-code-based-campaign"><strong>コードベースのエクスペリエンスを作成</strong></a>
</div>
<p></td>
<td>
<a href="code-based-implementation-samples.md">
<img alt="検証" src="../assets/do-not-localize/web-design.jpg">
</a>
<div>
<a href="code-based-implementation-samples.md"><strong>実装サンプル</strong></a>
</div>
<p>
</td>
</tr></table>

<!--[Learn how to create a code-based campaign in this video](#video)-->

## コードベースのチャネルと他のチャネルを使用する場合 {#code-based-vs-other-channels}

### コードベースのチャネルと他のチャネルの比較

他の [!DNL Journey Optimizer] チャネルではなく、コードベースのチャネルを使用するのはどのような場合ですか？

* デジタル プロパティに web ブラウザーやモバイルアプリを通じてアクセスできない場合はいつでも、コードベースのエクスペリエンスの使用を検討してください。この場合は、[!DNL Journey Optimizer] [web チャネル](../web/get-started-web.md){target="_blank"} or the [!DNL Journey Optimizer] [in-app messaging](../in-app/get-started-in-app.md){target="_blank"}を使用したほうがよいでしょう。

* [web デザイナー](../web/edit-web-content.md#work-with-web-designer){target="_blank"} visual editor or if you cannot use the [browser extension](../web/web-prerequisites.md#visual-authoring-prerequisites){target="_blank"}に web サイトを読み込めない場合は、[!DNL Journey Optimizer] web チャネルの代わりにコードベースのチャネルを使用すると、web チャネルのビジュアルオーサリングが強化されます。

* また、API ベース、ヘッドレス、またはサーバーサイド実装がある場合は、[!DNL Journey Optimizer] web チャネルやアプリ内チャネルの代わりにコードベースのチャネルを使用することもできます。

### コードベースのチャネルと web チャネルの比較

Web の使用例を実行するには、web チャネルまたはコードベースのエクスペリエンスを使用できますが、コンテキストに応じて、どちらか一方が適切です。いつ何を使用するかを十分な情報に基づいて決定できるように、主な違いを以下に示します。

**Web**
* [Web デザイナー](../web/edit-web-content.md#work-with-web-designer){target="_blank"}ビジュアルエディターを使用してコンテンツを編集します。
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} implementation and the [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} extension installed on your web browser. [Learn more](../web/web-prerequisites.md){target="_blank"} が必要です。
* Web チャネルを使用すると、ページ上のすべての項目を変更でき、変更に使用できるアクションの事前定義済みのリストが表示されます。[詳細情報](../web/edit-web-content.md#work-with-web-designer){target="_blank"}
* 簡単に設定して、すぐに使い始めることができます。
* マーケティング担当者向けです。

**コードベースのエクスペリエンス**
* [式エディター](create-code-based.md#edit-code)を使用して、コンテンツを編集します。
* コードベースのエクスペリエンスでは、[!DNL Journey Optimizer] によってエッジに公開されたコンテンツをサーフェスが解釈して配信できるように、実装に対する事前の開発作業が必要です。[詳細情報](#surface-definition)
* より詳細な計画が必要で、開発者が指定した内容だけを変更できます。したがって、パーソナライゼーションやテストのために変更が必要なサーフェス上のコンポーネント（ホームバナー、ヒーロー画像、メニューバーなど）を特定し、開発チームと協力してこれらの変更処理に必要な実装を構築することが重要です。
* JSON コードコンテンツを使用できます。
* 開発担当者向けです。

## 仕組み {#how-it-works}

>[!CAUTION]
>
>この機能は、開発担当者や経験豊富なユーザー向けです。サーフェス実装と初期設定が開発チームで処理される限り、ある程度のコード作成スキルを持つマーケターでも使用できます。

[!DNL Journey Optimizer] コードベースのエクスペリエンス機能を使用してコンテンツを編集するには、ページやアプリを実装する必要があります。これを行うには、コンテンツを挿入または置換する特定の個々の場所（「[サーフェス](#surface-definition)」と呼ばれる）を事前に宣言する必要があります<!--HOW??-->。

>[!NOTE]
>
>現在、サーフェスに関連付けられているコンテンツは、HTMLまたは JSON のみです。<!--WILL COME LATER: text, image or another format depending on the application-->

コードベースのキャンペーンを実装するための主な手順を以下に示します。

1. [サーフェス](#surface-definition)を定義します。サーフェスは、基本的にコードベースのエクスペリエンスを追加する場所で、このサーフェスを使用して [!DNL Journey Optimizer] でキャンペーンを作成します。[方法についてはこちらを参照](create-code-based.md#create-code-based-campaign)

1. [!DNL Journey Optimizer] 式エディターを使用して、選択したサーフェスのコンテンツを指定してエクスペリエンスを作成します。[方法についてはこちらを参照](create-code-based.md#edit-code)

1. アプリ実装チームは、明示的な API または SDK 呼び出しを行って、「バナーテキスト」や「Recommendations トレイ 1」などの名前付きサーフェスや、アプリケーション内の UI 関連以外の決定ポイント（「検索アルゴリズムパラメーター」など）のコンテンツを取得します。この場合、実装チームは返されたコンテンツをレンダリングするか、その他の方法で解釈し、それに基づいて行動する責任があります。<!--TBC with Robert - should link to a new section with API/SDK call samples-->

## サーフェスとは {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_code_based_surface"
>title="コードベースのエクスペリエンスサーフェスを定義"
>abstract="コードベースのサーフェスとは、ユーザーやシステムの操作用に設計されたエンティティで、URI によって一意に識別されます。"

**コードベースのエクスペリエンスサーフェス**&#x200B;とは、ユーザーやシステムの操作用に設計されたエンティティで<!--ask Robert to explain further-->、**URI** によって一意に識別されます。

つまり、サーフェスは、エンティティ（タッチポイント）が存在する階層の任意のレベルのコンテナと見なすことができます。<!--good idea to illustrate how it can be seen, but to clarify-->

* Web ページ、モバイルアプリ、デスクトップアプリ、大きなエンティティ内の特定のコンテンツの場所（`div` など）または非標準の表示パターン（キオスクやデスクトップアプリのバナーなど）が考えられます。<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* また、非表示または抽象された表示を目的として、コンテンツ コンテナの特定の部分に拡張することもできます（サービスに配信される JSON BLOB など）。

* また、様々なクライアントサーフェス定義に一致するワイルドカードサーフェスにすることもできます（例えば、web サイトの各ページのヒーロー画像の場所を web://mydomain.com/*#hero_image のようなサーフェス URI に変換できます）。

基本的に、サーフェス URI は複数のセクションで構成されます。
1. **タイプ**:web、mobileapp、atm、kiosk、tvcd、service など。
1. **プロパティ**：ページ URL またはアプリバンドル
1. **コンテナ**：ページ/アプリアクティビティ上の場所

次の表に、様々なデバイスのサーフェス URI 定義の例を示します。

**Web およびモバイル**

| タイプ | URI | 説明 |
| --------- | ----------- | ------- | 
| Web | web://domain.com/path/page.html#element | 特定のドメインの特定のページ内の個々の要素を表します。要素は、次の例のようなラベルにすることができます。 hero_banner、top_nav、menu、footer など。 |
| iOS アプリ | mobileapp://com.vendor.bundle/activity#element | ボタンや他の表示要素など、ネイティブアプリアクティビティ内の特定の要素を表します。 |
| Android アプリ | mobileapp://com.vendor.bundle#element | ネイティブアプリ内の特定の要素を表します。 |

**その他のデバイスタイプ**

| タイプ | URI | 説明 |
| --------- | ----------- | ------- | 
| Desktop | desktop://com.vendor.bundle#element | ボタン、メニュー、ヒーローバナーなど、アプリケーション内の特定の要素を表します。 |
| TV アプリ | tvcd://com.vendor.bundle#element | スマート TV または TV 接続デバイスアプリ内の特定の要素を表します（バンドル ID）。 |
| サービス | service://servicename#element | サーバーサイドのプロセスまたは他の手動エンティティを表します。 |
| キオスク | kiosk://location/screen#element | 容易に追加できる、潜在的な追加サーフェスタイプの例。 |
| ATM | atm://location/screen#element | 容易に追加できる、潜在的な追加サーフェスタイプの例。 |

**ワイルドカードサーフェス**

| タイプ | URI | 説明 |
| --------- | ----------- | ------- | 
| ワイルドカード Web | ワイルドカード:web://domain.com/`*`#element | ワイルドカードサーフェス - 特定のドメインの下の各ページの個々の要素を表します。 |
| ワイルドカード Web | ワイルドカード:web://`*`domain.com/`*`#element | ワイルドカードサーフェス — 「domain.com」で終わるすべてのドメイン下の各ページの個々の要素を表します。 |



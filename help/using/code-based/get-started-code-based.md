---
title: コードベースのエクスペリエンスの基本を学ぶ
description: Journey Optimizer でのコードベースのエクスペリエンスについて学ぶ
feature: Code-based Experiences
topic: Content Management
role: User, Developer, Admin
level: Experienced
exl-id: 987de2bf-cebe-4753-98b4-01eb3fded492
source-git-commit: e3c597f66436e8e0e22d06f1905fc7ca9a9dd570
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 83%

---

# コードベースチャネルの基本を学ぶ {#get-sarted-code-based}

[!DNL Journey Optimizer] を使用すると、web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、音声アシスタント、IoT デバイスなど、すべてのタッチポイントで顧客に提供するエクスペリエンスをパーソナライズしてテストできます。

**コードベースのエクスペリエンス**&#x200B;機能を使用すると、シンプルで直感的な非ビジュアルエディターを使用して、インバウンドエクスペリエンスを定義できます。これにより、コンテンツ全体に変更を適用する代わりに、アプリケーションの種類に関係なく、アプリや web ページの個別のより詳細な場所で、特定の要素を挿入および編集できます。

<!--[!DNL Journey Optimizer] allows you to compose and deliver content on any inbound device in a developer-focused workflow. You can leverage all the personalization capabilities, and preview what will be published. The content can be static (images, text, JSON, HTML) or dynamic (offers, decisions, recommendations). You can also insert custom content actions in your omni-channel journeys.-->

>[!IMPORTANT]
>
>コードベースのエクスペリエンスに関する特定のガードレールおよびレコメンデーションについて詳しくは、[このページ](code-based-prerequisites.md)を参照してください。


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
<a href="code-based-prerequisites.md"><strong>ガードレールと前提条件</strong></a>
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

* デジタルプロパティに web ブラウザーやモバイルアプリを通じてアクセスできない場合はいつでも、コードベースのエクスペリエンスの使用を検討してください。この場合は、[!DNL Journey Optimizer] [web チャネル](../web/get-started-web.md){target="_blank"}または [!DNL Journey Optimizer] [アプリ内メッセージング](../in-app/get-started-in-app.md){target="_blank"}チャネルを使用したほうがよいでしょう。

* [Web デザイナー](../web/edit-web-content.md#work-with-web-designer){target="_blank"}ビジュアルエディターに web サイトを読み込めない場合、またはビジュアルオーサリングを強化する[ブラウザー拡張機能](../web/web-prerequisites.md#visual-authoring-prerequisites){target="_blank"}を使用できない場合は、[!DNL Journey Optimizer] web チャネルの代わりにコードベースチャネルを使用できます。

* また、API ベース、ヘッドレス、またはサーバーサイド実装がある場合は、[!DNL Journey Optimizer] web チャネルやアプリ内チャネルの代わりにコードベースのチャネルを使用することもできます。

### コードベースのチャネルと web チャネルの比較 {#code-based-vs-web}

Web の使用例を実行するには、web チャネルまたはコードベースのエクスペリエンスを使用できますが、コンテキストに応じて、どちらか一方が適切です。いつ何を使用するかを十分な情報に基づいて決定できるように、主な違いを以下に示します。

**Web**

* [Web デザイナー](../web/edit-web-content.md#work-with-web-designer){target="_blank"}ビジュアルエディターを使用してコンテンツを編集します。
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} を実装し、[Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} 拡張機能を web ブラウザーにインストールしている必要があります。[詳細情報](../web/web-prerequisites.md){target="_blank"}
* Web チャネルを使用すると、ページ上のすべての項目を変更でき、変更に使用できるアクションの事前定義済みのリストが表示されます。[詳細情報](../web/edit-web-content.md#work-with-web-designer){target="_blank"}
* 簡単に設定して、すぐに使い始めることができます。
* マーケティング担当者向けです。

**コードベースのエクスペリエンス**

* [パーソナライゼーションエディター](create-code-based.md#edit-code)を使用して、コンテンツを編集します。
* コードベースのエクスペリエンスでは、アプリケーションがこれらの場所の [!DNL Journey Optimizer] によってエッジに公開されたコンテンツを解釈して配信できるように、実装に対する事前の開発作業が必要です。[詳細情報](code-based-configuration.md#surface-definition)
* より詳細な計画が必要で、開発者が指定した内容だけを変更できます。したがって、パーソナライゼーションやテストのために変更が必要なサーフェス上のコンポーネント（ホームバナー、ヒーロー画像、メニューバーなど）を特定し、開発チームと協力してこれらの変更処理に必要な実装を構築することが重要です。
* JSON コードコンテンツを使用できます。
* 開発担当者向けです。

## 仕組み {#how-it-works}

>[!CAUTION]
>
>この機能は、開発担当者や経験豊富なユーザー向けです。チャネル設定と初期設定が開発チームによって処理されている限り、コード作成のスキルを持つマーケターが使用できます。

[!DNL Journey Optimizer] コードベースのエクスペリエンス機能を使用してコンテンツを編集するには、ページやアプリを実装する必要があります。これを行うには、コンテンツを挿入または置換する特定の個々の場所（「[ サーフェス ](code-based-configuration.md#surface-definition)」と呼ばれます）を事前に宣言する必要があります。

>[!NOTE]
>
>現在、設定に関連付けられているコンテンツは、HTMLまたは JSON のみです。

コードベースのキャンペーンを実装する主な手順を次に示します。

1. アプリケーション実装に [ サーフェス ](code-based-configuration.md#surface-definition) を定義します。これは、基本的にコードベースのエクスペリエンスを追加する場所です。そして、その場所を参照するコードベースのエクスペリエンスチャネル設定を作成します。 [方法について詳しくは、こちらを参照してください](code-based-configuration.md#create-code-based-configuration)

1. この設定を使用して、[!DNL Journey Optimizer] でジャーニーまたはキャンペーンを作成します。 [方法について詳しくは、こちらを参照してください](create-code-based.md#create-code-based-campaign)

1. [!DNL Journey Optimizer] パーソナライゼーションエディターを使用して、選択した設定のコンテンツを指定してエクスペリエンスを作成します。[方法についてはこちらを参照](create-code-based.md#edit-code)

1. アプリ実装チームは、明示的な API または SDK 呼び出しを行って、「バナーテキスト」や「Recommendations トレイ 1」などの名前付きサーフェスや、アプリケーション内の UI 関連以外の決定ポイント（「検索アルゴリズムパラメーター」など）のコンテンツを取得します。この場合、実装チームは、返されたコンテンツのレンダリングまたはその他の方法で解釈および操作する責任を負います。 [詳細情報](code-based-implementation-samples.md)

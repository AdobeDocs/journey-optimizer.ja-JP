---
title: コードベースのエクスペリエンスの基本を学ぶ
description: Journey Optimizer でのコードベースのエクスペリエンスについて学ぶ
feature: Code-based Experiences
topic: Content Management
role: User, Developer, Admin
level: Experienced
exl-id: 987de2bf-cebe-4753-98b4-01eb3fded492
source-git-commit: 4d7ad2c3ed71801298f1afe31d0e29d7bb1d5c7f
workflow-type: ht
source-wordcount: '771'
ht-degree: 100%

---

# コードベースチャネルの基本を学ぶ {#get-sarted-code-based}

[!DNL Journey Optimizer] を使用すると、web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、音声アシスタント、IoT デバイスなど、すべてのタッチポイントで顧客に提供するエクスペリエンスをパーソナライズしてテストできます。

**コードベースのエクスペリエンス**&#x200B;機能を使用すると、シンプルで直感的な非ビジュアルエディターを使用して、インバウンドエクスペリエンスを定義できます。これにより、コンテンツ全体に変更を適用する代わりに、アプリケーションの種類に関係なく、アプリや web ページの個別のより詳細な場所で、特定の要素を挿入および編集できます。

<!--[!DNL Journey Optimizer] allows you to compose and deliver content on any inbound device in a developer-focused workflow. You can leverage all the personalization capabilities, and preview what will be published. The content can be static (images, text, JSON, HTML) or dynamic (offers, decisions, recommendations). You can also insert custom content actions in your omni-channel journeys.-->

>[!IMPORTANT]
>
>コードベースのエクスペリエンスに関する特定のレコメンデーションについて詳しくは、[このページ](code-based-prerequisites.md)を参照してください。


<!--Discover the detailed steps to create a code-based campaign in this video.-->

<!--[Learn how to create a code-based campaign in this video](#video)-->

➡️ コンテンツ実験を使用してコードベースのエクスペリエンスチャネルと決定を比較する方法を示すエンドツーエンドのユースケースについて詳しくは、[この節](../experience-decisioning/experience-decisioning-uc.md)を参照してください。

## コードベースのチャネルと他のチャネルを使用する場合 {#code-based-vs-other-channels}

### コードベースのチャネルと他のチャネルの比較

他の [!DNL Journey Optimizer] チャネルではなく、コードベースのチャネルを使用するのはどのような場合ですか？

* デジタルプロパティに web ブラウザーやモバイルアプリを通じてアクセスできない場合はいつでも、コードベースのエクスペリエンスの使用を検討してください。この場合は、[!DNL Journey Optimizer] [web チャネル](../web/get-started-web.md){target="_blank"}または [!DNL Journey Optimizer] [アプリ内メッセージング](../../rp_landing_pages/in-app-landing-page.md){target="_blank"}チャネルを使用したほうがよいでしょう。

<!--* You can use the code-based channel as an alternative to the [!DNL Journey Optimizer] web channel if your website cannot be loaded into the [web designer](../web/web-visual-editor.md){target="_blank"} visual editor or if you cannot use the [browser extension](../web/web-prerequisites.md#visual-authoring-prerequisites){target="_blank"} that powers visual authoring for web channel.-->

* API ベース、ヘッドレスまたはサーバーサイドの実装がある場合は、[!DNL Journey Optimizer] web チャネルやアプリ内チャネルの代わりにコードベースのチャネルを使用できます。

* また、モーダル、ポップアップ、オーバーレイを表示する代わりにネイティブアプリ内のコンテンツを変更する場合は、アプリ内チャネルの代わりにネイティブモバイルアプリケーションでコードベースのチャネルを活用することもできます。

### コードベースのチャネルと web チャネルの比較 {#code-based-vs-web}

Web の使用例を実行するには、web チャネルまたはコードベースのエクスペリエンスを使用できますが、コンテキストに応じて、どちらか一方が適切です。いつ何を使用するかを十分な情報に基づいて決定できるように、主な違いを以下に示します。

**Web**

* [Web designer](../web/web-visual-editor.md){target="_blank"} のビジュアルエディターまたは web [非ビジュアルエディター](../web/web-non-visual-editor.md)を使用してコンテンツを編集します。
* クライアントサイドの実装である [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} が必要です。
  <!--* You need the [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} extension installed on your web browser. [Learn more](../web/web-prerequisites.md){target="_blank"}-->
* Web チャネルを使用すると、ページ上のすべての項目を変更でき、変更に使用できるアクションの事前定義済みのリストが表示されます。[詳細情報](../web/web-visual-editor.md){target="_blank"}
* 簡単に設定して、すぐに使い始めることができます。
* マーケティング担当者向けです。

**コードベースのエクスペリエンス**

* [パーソナライゼーションエディター](create-code-based.md#edit-code)を使用して、コンテンツを編集します。
* クライアントサイドの実装である [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} またはサーバーサイドの実装である [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja){target="_blank"} のいずれかが必要です。
* コードベースのエクスペリエンスでは、アプリケーションがこれらの場所の [!DNL Journey Optimizer] によってエッジに公開されたコンテンツを解釈して配信できるように、実装に対する事前の開発作業が必要です。[詳細情報](code-based-surface.md)
* より詳細な計画が必要で、開発者が指定した内容だけを変更できます。したがって、パーソナライゼーションやテストのために変更が必要なアプリケーション上のコンポーネント（ホームバナー、ヒーロー画像、メニューバーなど）を特定し、開発チームと協力してこれらの変更処理に必要な実装を構築することが重要です。
* JSON コードコンテンツを使用できます。
* 開発担当者向けです。

## 仕組み {#how-it-works}

>[!CAUTION]
>
>この機能は、開発担当者や経験豊富なユーザー向けです。チャネル設定と初期設定が開発チームで処理される限り、ある程度のコード作成スキルを持つマーケターでも使用できます。

[!DNL Journey Optimizer] コードベースのエクスペリエンス機能を使用してコンテンツを編集するには、ページやアプリを実装する必要があります。これを行うには、コンテンツを挿入または置換する特定の個々の場所（「[サーフェス](code-based-surface.md)」と呼ばれる）を事前に宣言する必要があります。

>[!NOTE]
>
>現在、設定に関連付けられているコンテンツは、HTML または JSON のみです。

コードベースのエクスペリエンスを作成および提供するための主な手順を以下に示します。

1. チャネル固有の前提条件に従っていることを確認します。[詳細情報](code-based-prerequisites.md)

1. アプリケーション実装で[サーフェス](code-based-surface.md#surface-definition)を定義します。基本的に、サーフェスはエクスペリエンスを追加する場所です。

1. その場所を参照するコードベースのチャネル設定を作成します。[方法について詳しくは、こちらを参照してください](code-based-configuration.md#create-code-based-configuration)

1. この設定を使用して、[!DNL Journey Optimizer] でジャーニーまたはキャンペーンを作成します。[方法について詳しくは、こちらを参照してください](create-code-based.md#create-code-based-campaign)

1. [!DNL Journey Optimizer] パーソナライゼーションエディターを使用して、選択した設定のコンテンツを指定してエクスペリエンスを作成します。[方法について詳しくは、こちらを参照してください](create-code-based.md#edit-code)

1. コードベースのエクスペリエンスをテストします。[方法について詳しくは、こちらを参照してください](test-code-based.md)

1. 公開します。[方法について詳しくは、こちらを参照してください](publish-code-based.md)

1. コードベースのエクスペリエンスジャーニーまたはキャンペーンを公開したら、コンテンツを取得して表示するために、サーフェスのコンテンツをリクエストするアプリまたはページの実装を配置する必要があります。

   >[!INFO]
   >
   >これを確実に行うために、アプリ実装チームは、明示的な API または SDK 呼び出しを行って、「バナーテキスト」や「Recommendations トレイ 1」などのコードベースの設定で定義したサーフェスのコンテンツや、アプリケーション内の UI に関連しない決定ポイント（「検索アルゴリズムパラメーター」など）のコンテンツを取得します。<!--In this case, the implementation team is responsible for rendering or otherwise interpreting and acting on the returned content.--> [詳細情報](code-based-implementation-samples.md)


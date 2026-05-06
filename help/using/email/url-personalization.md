---
solution: Journey Optimizer
product: journey optimizer
title: メールのURLのパーソナライズ
description: トラッキングの信頼性を維持しながらURLを動的に生成するためのベストプラクティスと制限事項について説明します
feature: Email Design, Monitoring
topic: Content Management
role: User
level: Intermediate, Experienced
keywords: url、リンク、パーソナライゼーション、トラッキング、エンコード、中括弧
source-git-commit: 36fad8d6c200118210794249fa12263ae70e5422
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 14%

---

# メールのURLのパーソナライズ {#url-personalization}

パーソナライズされたURLを使用すると、受信者固有のリンクの生成や動的パラメーターの追加など、[!DNL Journey Optimizer]電子メールメッセージを通じてコンテクストに即したエクスペリエンスを提供できます。

プロファイル属性に応じて、受信者をweb サイトの特定のページやパーソナライズされたマイクロサイトに誘導します。

## URLのパーソナライズ {#personalize-url}

URLをパーソナライズするには、次の手順に従います。

1. 電子メール Designerで、コンテンツ内の要素を選択し、コンテキストツールバーを使用して[ リンクを挿入](message-tracking.md#insert-links)します。

   >[!IMPORTANT]
   >
   >Personalizationは、**[!UICONTROL 外部リンク]**、**[!UICONTROL 購読解除リンク]**&#x200B;および&#x200B;**[!DNL Opt-Out]**&#x200B;でのみ使用できます。 適切なリンクタイプを選択してください。

1. パーソナライゼーションアイコンを選択します。

   ![](assets/message-tracking-insert-link-perso.png)

1. パーソナライゼーションエディターを使用して、URLをパーソナライズするプロファイル属性を追加します。

1. 変更を保存します。

パーソナライズされたURLの例を次に示します。

* `https://www.adobe.com/users/{{profile.person.name.lastName}}`
* `https://www.adobe.com/users?uid={{profile.person.name.firstName}}`
* `https://www.adobe.com/usera?uid={{context.journey.technicalProperties.journeyUID}}`
* `https://www.adobe.com/users?uid={{profile.person.crmid}}&token={{context.token}}`

>[!NOTE]
>
>パーソナライゼーションエディターでは、パーソナライズされた URL を編集する際、セキュリティ上の理由から、ヘルパー関数とオーディエンスメンバーシップが無効になります。
>
>スペースは、URL 内で使用されるパーソナライゼーショントークンではサポートされていません。

信頼性の高いレンダリングとトラッキングを行うには、以下の[ ベストプラクティスとガードレール ](#best-practices)に従ってください。

## 完全/ベース URLのパーソナライズ {#personalize-complete-base-url}

Journey Optimizerでは、URLの&#x200B;**entire** URLまたは&#x200B;**base domain**&#x200B;のパーソナライズもサポートしています。例：

```html
<a href="{{profile.social.link}}" />
<a href="{{profile.social.baseUrl}}/profile" />
<a href="https://{{profile.social.baseUrl}}/profile" />
```

>[!IMPORTANT]
>
>URLの完全なパーソナライズまたはベースのパーソナライズを有効にするには、Adobeに連絡し、許可されたドメインのリストを提供します。 これは、安全でないリダイレクトを防ぐために必要です。

## URL トラッキングパラメーターのパーソナライズ {#personalize-url-tracking-parameters}

[URL トラッキング ](url-tracking.md)はチャネル設定レベルで管理され、メッセージコンテンツに含まれるすべてのURLに適用されます。 電子メールDesignerでは、個々のリンクのURL トラッキングパラメーターをパーソナライズすることもできます。 これにより、受信者固有のパラメーターを1つのリンクに追加できます（例えば、Web分析ツールに識別子を渡すために）。

これを行うには、[ リンクを挿入](message-tracking.md#insert-links)し、パーソナライゼーションアイコンを選択し、URL トラッキングパラメーターを追加して、[ パーソナライゼーションエディター](../personalization/personalization-build-expressions.md)から選択したプロファイル属性を選択します。

![](assets/message-tracking-perso-parameter.png)

このトラッキングパラメーターを追加する各リンクに対して、上記の手順を繰り返します。

これで、メールが送信されると、このパラメーターがURLの最後に自動的に追加されます。 その後、このパラメーターを web 分析ツールまたはパフォーマンスレポートで取得できます。

>[!NOTE]
>
>最終的な URL を確認するには、[配達確認を送信](../content-management/proofs.md)し、配達確認を受信したらメールのコンテンツにあるリンクをクリックします。 URL にはトラッキングパラメーターを表示する必要があります。 例：<https://luma.enablementadobe.com/content/luma/us/en.html?utm_contact=profile.userAccount.contactDetails.homePhone.number>

## ベストプラクティスとガードレール {#best-practices}

リンクを有効にし、クリック可能にし、追跡できるようにするには、以下のベストプラクティスとガードレールに従ってください。

### 動的URLの中括弧 {#use-braces}

パーソナライゼーションを含むURLを挿入する場合は、URLの動的な部分に3つの中括弧（`{{{ ... }}}`）を使用します。 これにより、特殊文字（`/`や`+`など）の変更によるエスケープを防ぎ、壊れたURL、誤ったリダイレクト、トラッキングの問題を回避できます。

次に例を示します。

```html
<a href="https://example.com/path/{{{profile.person.customSlug}}}?ref={{{context.system.source.id}}}">View details</a>
```

>[!IMPORTANT]
>
>生の出力（`{{{ ... }}}`）を使用すると、値がそのまま挿入されます。 信頼できる値で、URLが安全であることを意図した値（例えば、アップストリームで生成または検証する値）でのみ使用します。

### 正しいURL トラッキング {#enable-url-tracking}

* パーソナライゼーションを使用してURLを生成する場合、解決済みの値が受信者ごとに`http`/`https`で始まることを確認します。 そうでない場合、トラッキングが適用されず、リンクが期待どおりに動作しない可能性があります。

* `let`、`each`、`if`などの動的ロジックを、パーソナライゼーションエディターのURL フィールドで直接使用しないでください。 セキュリティ上の理由から、これらは無効になっています。

* シナリオでパーソナライズされたURLを生成するための複雑なロジックが含まれる場合は、そのロジックをパーソナライゼーションエディターのURL フィールドに直接配置しないでください。 代わりに：
   * URL フィールドの上または近くのHTML コンテンツに、必要なロジックとステートメントを追加します。
   * パーソナライズされた属性を個別に生成して保存し、メールコンテンツで参照できます。

### URL エンコーディングと長さ {#encoding}

* URI構文ルール （[RFC 3986 standard](https://datatracker.ietf.org/doc/html/rfc3986){target="_blank"}）は、メールコンテンツのすべてのURLに適用されます。 ただし、パーソナライズされたURLでは、受信者固有の値によって予約文字（クエリパラメーターなど）が導入されるため、エンコードの問題が発生する可能性が高くなります。 したがって、動的な値がURL エンコードされていることを確認し（特にスペース、`&`、`#`、`%`、および`+`）、クエリ値に`+`を使用しないでください。

* 非常に長いURLは、ブラウザー、メールクライアント、またはダウンストリームシステムによって切り捨てられるか、拒否される可能性があります。 例えば、ランタイムのパーソナライゼーションが重い場合、ミラーページのURLは大幅に増加する可能性があります。 パーソナライズされたペイロードを小さく抑え、大きなオブジェクトをURLに埋め込まないようにします。

### 推奨される検証手順 {#validation}

ジャーニーまたはキャンペーンをアクティブ化する前に、以下の推奨事項に従ってください。

* [ プルーフ ](../content-management/proofs.md)を送信し、リンクをクリックして、解決されたURLが`http`/`https`で始まり、想定される構造を維持することを確認します。
* トラッキングパラメーターが追加されている場合は、最終的なURLにそれらを含めることを確認します（設定レベルのURL トラッキングまたはリンクごとのトラッキングパラメーターを使用）。


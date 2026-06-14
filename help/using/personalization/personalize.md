---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer でのコンテンツのパーソナライズ
description: パーソナライゼーションの基本を学ぶ
feature: Personalization
topic: Personalization
role: Developer
level: Beginner
keywords: 式, エディター, 開始, パーソナライゼーション
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
feature_v2: id: fda7be7c-b81e-42c0-95a9-616e5b893c03
subfeature_v2: id: a757b957-83f3-4a4d-9775-a93854f84f77id: cb09dcb7-3367-4b63-b02c-8a1356eb876e
source-git-commit: 378c98d4dc9552de3eed68eda59d9917c2b56347
workflow-type: tm+mt
source-wordcount: 710
ht-degree: 78%

---

# パーソナライゼーションの概要{#add-personalization}

>[!BEGINSHADEBOX]

**このページ：** パーソナライゼーションエディターの仕組み、使用できるプロファイルデータ、学習プレイグラウンド、インライン編集など、Adobe Journey Optimizerでのパーソナライゼーションの基本を学びます。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_homepage_card5"
>title="エクスペリエンスのパーソナライズ"
>abstract="**Adobe Journey Optimizer** を使用すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます。 名前、興味、住所、購入品などの情報です。"

[!DNL Adobe Journey Optimizer] のパーソナライゼーション機能を使用すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます。 名前、興味、住所、購入品などの情報です。

## パーソナライゼーションの仕組み

**パーソナライゼーションエディター**&#x200B;を使用すると、すべてのデータを選択、整理、カスタマイズ、検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成したり、ヘルパー関数や事前定義済みの式などの様々なツールを活用してメッセージを効果的に調整したりできます。

Journey Optimizer では、ハンドルバーに基づいたインラインのパーソナライゼーション構文を使用します。この構文を使用すると、コンテンツを二重の中括弧 **`{{}}`** で囲んだ式を作成できます。

Journey Optimizer は、メッセージを処理する際に、式を Experience Platform データセットに含まれるデータで置き換えます。 例えば、`Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` は動的に `Hello John Doe` になります。 この構文を使用すると、メールの件名、メッセージ本文、プッシュ通知、URL など、複数のフィールドをまたいでメッセージをパーソナライズできます。

## パーソナライゼーションに使用するデータ

パーソナライゼーションは、**XDM 個人プロファイル**&#x200B;スキーマ（Adobe Experience Platform で定義）で管理されるプロファイルデータに基づいています。 **XDM 個人版プロファイル**&#x200B;スキーマは、[!DNL Journey Optimizer] でコンテンツをパーソナライズするのに使用できる唯一のスキーマです。 詳しくは、[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}を参照してください。

また、**計算属性**&#x200B;を利用して、コンテンツをパーソナライズすることもできます。 計算属性を使用すると、個々の行動イベントを、Adobe Experience Platform で使用可能な計算プロファイル属性に要約できます。 [詳しくは、計算属性の操作方法を参照してください。](../audience/computed-attributes.md)

さらに、[!DNL Journey Optimizer] を使用すると、パーソナライゼーションエディターで Adobe Experience Platform のデータを利用して、コンテンツをパーソナライズすることができます。 これを行うには、まず、API 呼び出しを通じて参照パーソナライゼーションに必要なデータセットを有効にする必要があります。 完了したら、そのデータを使用して、コンテンツを Journey Optimizer にパーソナライズできます。 この機能は現在ベータ版で使用可能です。 [詳細情報](../personalization/aep-data-perso.md)

## パーソナライズ機能の学習と実験 {#playground}

**[!DNL Adobe Journey Optimizer]** には、パーソナライズ機能の学習と実験に役立つように設計されたインタラクティブなツールが含まれています。

このプレイグラウンドは、ライブデータセットを必要とせずに、サンプルデータを使用してパーソナライゼーションコードを記述およびテストするためのシミュレーション環境を提供します。 定義済みコードサンプルの活用、ダミーのプロファイルペイロードの編集、パーソナライゼーションコードの出力のリアルタイムプレビューを行うことができます。

![パーソナライゼーションプレイグラウンド](assets/playground.png)

➡️ [パーソナライゼーションプレイグラウンドへのアクセス](https://experienceleague.adobe.com/ja/apps/journey-optimizer/ajo-personalization){target="_blank"}

## パーソナライゼーション式用 AI アシスタント {#ai-personalization-expressions}

**[!UICONTROL Personalization Editor]**&#x200B;またはメール Designer ツールバー（**[!UICONTROL 式を追加]**）から、**[!UICONTROL AI アシスタント]**&#x200B;は、自然言語から新しい式を生成し、既存のコードの機能を説明し、選択範囲の問題を修正し、意図に一致したときに出力を適用するのに役立ちます。

![](../content-management/assets/ai-perso-generate.png)

➡️ [Personalization エクスプレッションのAI アシスタントの操作方法を学ぶ](../content-management/generative-personalization-expressions.md)

## プロファイル属性のインライン編集 {#inline-personalization}

**電子メール Designer**&#x200B;または&#x200B;**プッシュチャネル** エディターでコンテンツを編集する際に、完全なパーソナライゼーションエディターを開かずに、プロファイル属性式を直接挿入できます。

それには、次の手順に従います。

1. 任意のテキストフィールドに`{{`と入力します。 インライン自動補完ドロップダウンがカーソル位置で開きます。
1. 入力を開始して、使用可能なプロファイル属性をフィルタリングします。
1. 必要な属性を選択します。カーソル位置にパーソナライゼーショントークンとして挿入されます。

![](assets/inline-profile-attributes.png)

## さらに深く掘り下げましょう

これで、**[!DNL Journey Optimizer]** のパーソナライゼーションについて理解できたので、これらのドキュメントの節で詳しく説明し、この機能の使用を開始します。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="personalization-build-expressions.md">
<img alt="パーソナライゼーションの追加" src="assets/do-not-localize/add.png">
</a>
<div>
<a href="personalization-build-expressions.md"><strong>パーソナライゼーションの追加</strong></a>
</div>
<p>
</td>
<td>
<a href="../personalization/personalization-syntax.md">
<img alt="リード" src="assets/do-not-localize/syntax.png">
</a>
<div><a href="../personalization/personalization-syntax.md"><strong>パーソナライゼーション構文</strong>
</div>
<p>
</td>
<td>
<a href="../personalization/functions/functions.md">
<img alt="低頻度" src="assets/do-not-localize/functions.png">
</a>
<div>
<a href="../personalization/functions/functions.md"><strong>ヘルパー関数リスト</strong></a>
</div>
<p></td>
<td>
<a href="../personalization/personalization-recipes.md">
<img alt="低頻度" src="assets/do-not-localize/uc.png">
</a>
<div>
<a href="../personalization/personalization-recipes.md"><strong>Personalization レシピ </strong></a>
</div>
<p></td>
<td>
<a href="../personalization/personalization-use-case.md">
<img alt="低頻度" src="assets/do-not-localize/uc.png">
</a>
<div>
<a href="../personalization/personalization-use-case.md"><strong>パーソナライゼーションのユースケース</strong></a>
</div>
<p></td>
</tr></table>

## チュートリアルビデオ{#video-perso}

ジャーニーのコンテキストイベント情報を使用してメッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

プロファイルベースのパーソナライゼーションをメッセージに追加する方法と、オーディエンスメンバーシップをパーソナライゼーションブロックの前提条件として使用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)

パーソナライゼーションエディタープレイグラウンドを活用し、サンプルデータを使用してパーソナライゼーションコードを記述およびテストする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3457868?quality=12)

パーソナライゼーションの機能とベストプラクティスに関するその他のビデオチュートリアルについて詳しくは、[パーソナライゼーションチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/personalize-content/personalization-editor-overview){target="_blank"}を参照してください。

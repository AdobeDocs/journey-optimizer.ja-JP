---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer でのコンテンツのパーソナライズ
description: パーソナライゼーションの基本を学ぶ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Beginner
keywords: 式, エディター, 開始, パーソナライゼーション
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# パーソナライゼーションの基本を学ぶ{#add-personalization}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card5"
>title="エクスペリエンスのパーソナライズ"
>abstract="**Adobe Journey Optimizer** を使用すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます。名前、興味、住所、購入品などの情報です。"

[!DNL Adobe Journey Optimizer] のパーソナライゼーション機能を理解すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます。名前、興味、住所、購入品などの情報です。

➡️ [こちらのビデオでメッセージをパーソナライズする方法を学ぶ](#video-perso)
➡️ [パーソナライゼーションを活用したユースケースを確認する](personalization-use-case.md)

## 専用の構文を使用したパーソナライゼーション式の作成 {#syntax}

[!DNL Journey Optimizer] ではハンドルバーに基づいた、**インライン**&#x200B;のシンプルなパーソナライゼーション構文を使用します。この構文を使用すると、コンテンツを二重の中括弧 **{{}}** で囲んだ式を作成することができます。同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。[パーソナライゼーション構文の詳細情報](personalization-syntax.md)。

**例：**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`
* `Hello {{profile.person.name.fullName}}`

メッセージ（メールおよびプッシュ）を処理する際に、Journey Optimizer は式を、Experience Platform データベースに含まれるデータに置き換えます。`Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` は “Hello John Doe” となります。

## プロファイルデータを活用したメッセージのパーソナライズ {#data}

パーソナライゼーションは、**XDM 個人プロファイル**&#x200B;スキーマ（Adobe Experience Platform で定義）で管理されるプロファイルデータに基づいています。詳しくは、[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}を参照してください。

>[!CAUTION]
>**XDM 個人版プロファイル**&#x200B;スキーマは、[!DNL Journey Optimizer] でコンテンツをパーソナライズするために使用できる唯一のスキーマです。

さらに、**計算属性**&#x200B;を利用して、コンテンツをパーソナライズすることもできます。計算属性は、Adobe Experience Platform に取り込まれたプロファイル対応のエクスペリエンスイベントデータセットに基づいており、個々の行動イベントを要約する顧客プロファイル内に保存される集計データポイントとして機能します。[計算属性の使用方法を学ぶ](../audience/computed-attributes.md)

## パーソナライゼーションエディターの操作 {#editor}

[!DNL Journey Optimizer] では、パーソナライゼーションエディターを使用すると、すべてのデータを選択、整理、カスタマイズ、および検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。パーソナライゼーションコンテンツの作成に役立つツール（ヘルパー関数、事前定義された式ライブラリ、お気に入りの属性など）がいくつか用意されています。

* [パーソナライゼーションエディターの操作方法を学ぶ](personalization-build-expressions.md)
* [パーソナライゼーションを実行できる場所について説明します](personalization-contexts.md)。

## チュートリアルビデオ{#video-perso}

ジャーニーのコンテキストイベント情報を使用してメッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

プロファイルベースのパーソナライゼーションをメッセージに追加する方法と、オーディエンスメンバーシップをパーソナライゼーションブロックの前提条件として使用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)


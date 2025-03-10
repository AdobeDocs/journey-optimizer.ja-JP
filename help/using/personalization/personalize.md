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
source-git-commit: 78c1464ccddec75e4827cbb1877d8fab5ac08b90
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 38%

---

# パーソナライゼーションの基本を学ぶ{#add-personalization}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card5"
>title="エクスペリエンスのパーソナライズ"
>abstract="**Adobe Journey Optimizer** を使用すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます。名前、興味、住所、購入品などの情報です。"

パーソナライゼーション機能を使用すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます [!DNL Adobe Journey Optimizer] 名前、興味、住所、購入品などの情報です。

## パーソナライゼーションの仕組み

**パーソナライゼーションエディター** を使用すると、すべてのデータを選択、整理、カスタマイズ、検証してコンテンツ用にカスタマイズされたパーソナライゼーションを作成でき、ヘルパー関数や事前定義済み式などの様々なツールを活用してメッセージを効果的にカスタマイズできます。

Journey Optimizerでは、ハンドルバーに基づいたインラインパーソナライゼーション構文を使用します。この構文を使用すると、コンテンツを二重の中括弧 **{{}}** で囲んだ式を作成することができます。

メッセージの処理時に、Journey Optimizerは式をExperience Platform データセットに含まれるデータで置き換えます。 例えば、`Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` は動的に `Hello John Doe` になります。

この構文を使用すると、メールの件名、メッセージ本文、プッシュ通知、URL など、複数のフィールドをまたいでメッセージをパーソナライズできます。

## パーソナライゼーションに使用するデータ

Personalizationは、**XDM 個人プロファイル** スキーマ（Adobe Experience Platformで定義）で管理されるプロファイルデータに基づいています。 **XDM 個人版プロファイル** スキーマは、[!DNL Journey Optimizer] でコンテンツをパーソナライズするために使用できる唯一のスキーマです。 詳しくは、[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}を参照してください。

また、**計算済み属性** を利用して、コンテンツをパーソナライズすることもできます。 計算属性を使用すると、個々の行動イベントを、Adobe Experience Platform で使用可能な計算プロファイル属性に要約できます。[ 計算済み属性の操作方法を学ぶ ](../audience/computed-attributes.md)

さらに、パーソナライゼーショ [!DNL Journey Optimizer] エディターでAdobe Experience Platformのデータを活用して、コンテンツをパーソナライズできます。 これを行うには、まず、API 呼び出しを通じて参照パーソナライゼーションに必要なデータセットを有効にする必要があります。完了したら、そのデータを使用してコンテンツをJourney Optimizerにパーソナライズできます。 この機能は現在、ベータ版で利用できます。 [詳細情報](../personalization/lookup-aep-data.md)

## さらに深く掘り下げましょう

これで **[!DNL Journey Optimizer]** のパーソナライゼーションを理解できたので、ドキュメントの節で詳しく説明し、この機能の使用を開始します。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="personalization-build-expressions.md">
<img alt="パーソナライゼーションを追加" src="assets/do-not-localize/add.png">
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
<div><a href="../personalization/personalization-syntax.md"><strong>Personalization構文 </strong>
</div>
<p>
</td>
<td>
<a href="../personalization/functions/functions.md">
<img alt="低頻度" src="assets/do-not-localize/functions.png">
</a>
<div>
<a href="../personalization/functions/functions.md"><strong> ヘルパー関数のリスト </strong></a>
</div>
<p></td>
<td>
<a href="../personalization/personalization-use-case.md">
<img alt="低頻度" src="assets/do-not-localize/uc.png">
</a>
<div>
<a href="../personalization/personalization-use-case.md"><strong>Personalizationのユースケース </strong></a>
</div>
<p></td>
</tr></table>

## チュートリアルビデオ{#video-perso}

ジャーニーのコンテキストイベント情報を使用してメッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

プロファイルベースのパーソナライゼーションをメッセージに追加する方法と、オーディエンスメンバーシップをパーソナライゼーションブロックの前提条件として使用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)


---
solution: Journey Optimizer
product: journey optimizer
title: 旅のオプティマイザーでのコンテンツのパーソナライズ
description: パーソナライズについて学習します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Beginner
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
source-git-commit: 6014088011c41fd5f673eb3d36fb0609c4a01270
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# パーソナル化の開始{#add-personalization}

[!DNL Adobe Journey Optimizer]個人情報を利用して、その受信者にメッセージを表示することができます。これには、名前、関心事項、住んでいる場所、購入したもの、その他を指定することができます。

➡️ [ では、これらのビデオ ](#video-perso) でメッセージをカスタマイズする方法について説明しています。
パーソナライズを活用したユースケースの➡️ [ 発見](personalization-use-case.md)

## 専用のシンタックスを使用したパーソナル化式の作成 {#syntax}

[!DNL Journey Optimizer] では、 **Handlebars に基づいてインライン** の単純なパーソナル化構文を使用します。これにより、内容が含まれている式を二重中かっこ **{{}}** で囲むことができます。 制限なしに、同じコンテンツまたはフィールド内に複数のエクスプレッションを追加することができます。 パーソナル化の構文 ](personalization-syntax.md) に [ ついて詳しく説明します。

**例**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`
* `Hello {{profile.person.name.fullName}}`

メッセージの処理 (電子メールとプッシュ) 時に、その式はエクスペリエンスプラットフォームデータベース  `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` に格納されているデータに置き換えられます。これは「Hello 太郎 Doe」となります。

## プロファイルデータを活用したメッセージのカスタマイズ {#data}

パーソナル化は、Adobe エクスペリエンスプラットフォームで定義された XDM の個別の **プロファイル** スキーマによって管理されるプロファイルデータに基づいています。 Adobe エクスペリエンス Platform のデータモデル (XDM) マニュアル ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) (「target =」 _blank 「}」を [ 参照してください。

>[!CAUTION]
>**XDM の個別のプロファイル** スキーマは、で [!DNL Journey Optimizer] コンテンツをパーソナライズするために使用できる唯一のスキーマです。

## 異なるコンテキストでのパーソナル化の追加 {#contexts}

[!DNL Journey Optimizer] では、様々な方法でコンテンツを表示し、メッセージを表示することができます。 この節 ](personalization-contexts.md) で [ は、パーソナル化を実行できるコンテキストについて詳しく説明します。

## エクスプレッションエディターを使用した操作 {#editor}

[!DNL Journey Optimizer] には、すべてのデータを選択、配置、カスタマイズ、検証して、コンテンツのカスタマイズされたパーソナル化を作成する式エディターが用意されています。

ヘルパー関数、事前に定義された式ライブラリ、属性 favouriting など) を作成するために使用できるツールはいくつかあります。

このセクションのエクスプレッションエディターについて詳しくは、こちらを [ 参照して [!DNL Journey Optimizer] ください。](personalization-build-expressions.md)

## 操作方法についてのビデオ{#video-perso}

状況に応じて、状況に応じたイベント情報を使用してメッセージをカスタマイズする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

プロファイルベースのパーソナライズをメッセージに追加する方法と、セグメントメンバーシップを事前条件として使用して、個人用設定ブロックを作成する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)

---
title: Journey Optimizer でのコンテンツのパーソナライズ
description: パーソナライゼーションの概要。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Beginner
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 100%

---

# パーソナライゼーションの基本を学ぶ{#add-personalization}

[!DNL Adobe Journey Optimizer] のパーソナライゼーション機能を理解すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます。名前、興味、住所、購入品などの情報です。

➡️ [こちらのビデオでメッセージをパーソナライズする方法を学ぶ](#video-perso)
➡️ [パーソナライゼーションを活用したユースケースを確認する](personalization-use-case.md)

## 専用の構文を使用したパーソナライゼーション式の作成 {#syntax}

[!DNL Journey Optimizer] ではハンドルバーに基づいた、**インライン**&#x200B;のシンプルなパーソナライゼーション構文を使用します。この構文を使用すると、コンテンツを二重の中括弧 **{{}}** で囲んだ式を作成することができます。同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。詳しくは、[パーソナライゼーション構文](personalization-syntax.md)を参照してください。

**例：**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`
* `Hello {{profile.person.name.fullName}}`

メッセージ（メールおよびプッシュ）を処理する際に、Journey Optimizer は式を、 Experience Platform データベースに含まれるデータに置き換えます。`Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` は “Hello John Doe” となります。

## プロファイルデータを活用したメッセージのパーソナライズ {#data}

パーソナライゼーションは、**XDM 個人プロファイル**&#x200B;スキーマ（Adobe Experience Platform で定義）で管理されるプロファイルデータに基づいています。詳しくは、[Adobe Experience Platform データモデル（XDM）のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

>[!CAUTION]
>**XDM 個人版プロファイル**&#x200B;スキーマは、[!DNL Journey Optimizer] でコンテンツをパーソナライズするために使用できる唯一のスキーマです。

## 様々なコンテキストでのパーソナライゼーションの追加 {#contexts}

[!DNL Journey Optimizer] を使用すると、メッセージのコンテンツと表示を複数の異なる方法でパーソナライズできます。[この節](personalization-contexts.md)では、パーソナライゼーションを実行できるコンテキストについて詳しく説明します。

## 式エディターの操作 {#editor}

[!DNL Journey Optimizer] では、式エディターを使用すると、すべてのデータを選択、整理、カスタマイズ、および検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。

パーソナライゼーションコンテンツの作成に役立つツールがいくつか用意されています（ヘルパー関数、事前定義された式ライブラリ、お気に入りの属性など）。

[!DNL Journey Optimizer] 式エディターについて詳しくは、[この節](personalization-build-expressions.md)を参照してください

## ハウツービデオ{#video-perso}

ジャーニーのコンテキストイベント情報を使用してメッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

ジャーニーのコンテキストイベント情報を使用してメッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)

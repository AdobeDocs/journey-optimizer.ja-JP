---
title: Journey Optimizerでコンテンツをパーソナライズ
description: 個人設定を使用する
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 5%

---

# はじめに {#add-personalization}

![](../assets/do-not-localize/badge.png)

Journey Optimizerの場合、パーソナライゼーションとは、メッセージに関するデータや情報を利用して、特定の加入者に対するメッセージをターゲット化する操作です。 彼の名、関心、住む場所などにもなる。

Journey Optimizerでは、ハンドルバーに基づく&#x200B;**インライン**&#x200B;簡単なパーソナライゼーション構文を使用します。この構文を使用すると、重複の中括弧&#x200B;**{{}}**&#x200B;で囲まれた内容を含む式を作成できます。 同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。 [パーソナライゼーション構文](personalization-syntax.md)を参照してください。

パーソナライゼーションは、Adobe Experience Platformで定義されている&#x200B;**XDM Individualプロファイル**&#x200B;スキーマで管理されるプロファイルデータに基づいています。 詳しくは、[Adobe Experience Platformデータモデル(XDM)ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。

>[!CAUTION]
>**XDM個人プロファイル**&#x200B;スキーマは、Journey Optimizerでコンテンツをパーソナライズするために使用できる唯一の方法です。

**例：**

```
Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}

Hello {{profile.person.gender}} {{profile.person.name.fullName}}
```

**メッセージ処理**（電子メールおよびプッシュ）中に、式はExperience Cloudプラットフォームデータベースに含まれるデータに置き換えられます。

```
Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}} becomes “Hello John Doe”.
```

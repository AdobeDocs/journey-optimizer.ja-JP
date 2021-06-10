---
title: Journey Optimizer でのコンテンツのパーソナライズ
description: パーソナライゼーションの概要
source-git-commit: 8c58dd667ea59a17833bbe3482b1a233ac2e28fe
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 51%

---

# パーソナライゼーションの基本を学ぶ{#add-personalization}

![](../assets/do-not-localize/badge.png)

ジャーニーオプティマのパーソナライゼーション機能を見つけ、ユーザーに関するデータと情報を活用して、特定の受信者に合わせてメッセージを調整します。 彼の名、興味、住んでいる場所、買ったものなどになる。

Journey Optimizer では、ハンドルバーに基づいた&#x200B;**インライン**&#x200B;のシンプルなパーソナライゼーション構文を使用します。この構文を使用すると、コンテンツを二重の中括弧（**{{}}**）で囲んだ式を作成することができます。同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。詳しくは、[パーソナライゼーション構文](personalization-syntax.md)を参照してください。

パーソナライゼーションは、**XDM 個人版プロファイル**&#x200B;スキーマ（Adobe Experience Platform で定義）で管理されるプロファイルデータに基づいています。詳しくは、[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。

>[!CAUTION]
>**XDM Individual Profile**&#x200B;スキーマは、Journey Optimizerでコンテンツをパーソナライズするために使用できる唯一のスキーマです。

**例：**

```
Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}

Hello {{profile.person.gender}} {{profile.person.name.fullName}}
```

Journey Optimizerは、メッセージ（Eメールおよびプッシュ）を処理する際に、式をEメールプラットフォームデータベースに含まれるExperience Cloudで置き換えます。

```
Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}} becomes “Hello John Doe”.
```

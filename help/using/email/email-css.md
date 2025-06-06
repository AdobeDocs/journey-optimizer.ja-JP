---
solution: Journey Optimizer
product: journey optimizer
title: メールコンテンツへのカスタム CSS の追加
description: Journey OptimizerのメールDesigner内でメールコンテンツに直接カスタム CSS を追加する方法を説明します
feature: Email Design
topic: Content Management
role: User
level: Intermediate
keywords: css, エディター，概要，メール
source-git-commit: feb3576c230f2fb28ab031f87cc5f99263329b57
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 3%

---

# メールコンテンツへのメタデータの追加 {#email-metadata}

>[!CONTEXTUALHELP]
>id="ac_edition_css"
>title="カスタム CSS を追加"
>abstract="xxx."

メールをデザインする際に、独自のカスタム CSS を [!DNL Journey Optimizer] [ メールDesigner](get-started-email-design.md) 内に直接追加できます。

「カスタム CSS を追加」テキスト領域に表示されるのは、有効な CSS 文字列です。

![](assets/email-body-css.png)

利用条件

カスタム CSS の追加機能は、エディターでコンテンツが定義されている場合にのみ使用できます。 カスタム CSS の追加セクションを表示するには、ユーザーがエディターでコンテンツを追加する必要があります。 ユーザーがすべてのコンテンツを削除すると、セクションが消え、カスタム css は適用されません。 ユーザーがコンテンツを追加し直すと、セクションが使用可能になり、カスタム css が適用されます。

**無効な CSS 入力の例**

無効な CSS は保存できません。CSS が無効な場合は、CSS を保存できなかったことを示す赤いトーストが表示されます。

`<style>` は受け付けられません。


```
<style type="text/css">
  .acr-Form {
    width: 100%;
    padding: 20px 100px;
    border-spacing: 0px 8px;
    box-sizing: border-box;
    margin: 0;
  }
</style>
```


見つからない括弧は無効です

```
body {
 background: red; 
```

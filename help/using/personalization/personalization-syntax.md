---
title: パーソナライゼーションの構文
description: パーソナライゼーション構文の使用方法を説明します。
translation-type: tm+mt
source-git-commit: e73b47ab6243b13f82aa1503bd8c751f976f29ee
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 3%

---

# パーソナライゼーションの構文{#personalization-syntax}

![](../assets/do-not-localize/badge.png)

## 概要

Journey Optimizerのパーソナライゼーションは、Handlebarsと呼ばれるテンプレート構文に基づいています。
Handlebars構文の詳細については、[HandlebarsJS](https://handlebarsjs.com/)を参照してください。

テンプレートと入力オブジェクトを使用して、HTMLや他のテキスト形式を生成します。 ハンドルバーテンプレートは、埋め込まれたハンドルバー式を含む標準のテキストのように見えます。

単純な式のサンプル：

```
{{profile.person.name}}
```

各パラメーターの意味は次のとおりです。

* **** profileは名前空間です。
* **person.** nameは、属性で構成されるトークンです。属性構造は、Adobe Experience PlatformXDMスキーマで定義されます。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja).

## 構文の一般的な規則

識別子には、次を除く任意のUnicode文字を使用できます。

```
Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
```

構文では大文字と小文字が区別されます。

**true**、**false**、**null**、**undefined**&#x200B;という語は、パス式ーの最初の部分でのみ使用できます。

ハンドルバーでは、{{式}}から返される値は&#x200B;**HTMLエスケープ**&#x200B;です。 式に&amp;が含まれる場合、返されるHTMLエスケープ出力は&amp;として生成されます。 ハンドルバーの値をエスケープしない場合は、「トリプルスタッシュ」を使用します。

## プロファイル

この名前空間を使用すると、[Adobe Experience Platformデータモデル(XDM)ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)で説明されているプロファイルスキーマで定義されているすべての属性を参照できます。

属性は、Journey Optimizerのパーソナライゼーションブロックで参照する前に、スキーマで定義する必要があります。

すべての参照は、プロファイルスキーマに対して検証されます。検証メカニズムには、[ここ](personalization-validation.md)で説明します。

**サンプルリファレンス：**

* ```{{profile.person.name.fullName}}```
* ```{{profile.person.name.firstName}}```
* ```{{profile.person.gender}}```
* ```{{profile.personalEmail.address}}```
* ```{{profile.mobilePhone.number}}```
* ```{{profile.homeAddress.city}}```
* ```{{profile.faxPhone.number}}```

**電子メールアドレスの拡張子**:

```
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
{%else if contains(profile.personalEmail.address, ".org")%}
<a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
{%else%}
<a href="https://www.adobe.com/users">Checkout our page</a>
{%/if%}
```

## セグメント

Segmentation and Segmentationサービスの詳細については、[セクション](../segment/about-segments.md)を参照してください。

**セグメントのメンバーシップに基づいて異なるコンテンツをレンダリング**:

```
{%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
  Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
{%else%} if 'profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"'%}
  Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
{%/if%}
```

**プロファイルが既にメンバーであるかどうかを確認します**。

```
{%#if profile.segmentMembership.get(segments.`123e4567-e89b-12d3-a456-426614174000`.id)%}
    You're a member!
{%else%}
    You should be a member! Sign up now!
{%/if%}
```

## オファー

この名前空間では、既存のオファーの判断を参照できます。
オファーを参照するには、オファーを定義する別の情報を使用してパスを宣言する必要があります。

このパスは次の構造を持ちます。
0 - &#39;オファー&#39;:オファー名前空間に属するパス式を識別します。
1 — タイプ：は、オファー表示域のタイプを決定します。 有効な値は「image」、「html」および「text」です
2 — 配置ID
3 -アクティビティID
4 -オファー固有の属性。 オファータイプに応じて、サポートされている属性を使用できます。 例えば、`deliveryUrl`画像の場合です。

Decisions APIについて詳しくは、[ページ](https://experienceleague.adobe.com/docs/offer-decisioning/using/api-reference/offer-delivery/deliver-offers.html?lang=en#deliver-offers-using-the-decisions-api)を参照してください。

オファー表現の詳細については、[ページ](https://experienceleague.adobe.com/docs/offer-decisioning/using/api-reference/offer-delivery/deliver-offers.html?lang=en#accept-and-content-type-headers)を参照してください。

すべての参照は、オファースキーマに対して検証されます。検証メカニズムについては、[ここ](personalization-validation.md)で説明します。

**サンプルリファレンス：**

* 画像がホストされる場所：

```offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl```

* ターゲットをクリックしたときの画像URL:

```offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl```

* 判定エンジンからのオファーのテキストコンテンツ：

```offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content```

* 判定エンジンからのオファーのHTMLコンテンツ：

```offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content```


## Helpers

ハンドルバーヘルパーは、パラメーターの後に続く単純な識別子です。
各パラメータはHandlebars式です。 これらのヘルパーは、テンプレート内の任意のコンテキストからアクセスできます。

これらのブロックヘルパーは、ヘルパー名の前に#が付いていて、同じ名前の一致する終了/が必要です。
ブロックとは、ブロックの開き({{# }})と閉じ({{/}})を持つ式です。

### If

**if**ヘルパーを使用して、条件付きブロックを定義します。
式の評価がtrueを返す場合、ブロックはレンダリングされます。trueを返さない場合はスキップされます。

```
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

**if**&#x200B;ヘルパーの後に、**else**ステートメントを入力して、同じ条件がfalseの場合に実行するコードのブロックを指定できます。
**else if**&#x200B;ステートメントは、最初のステートメントがfalseを返した場合にテストする新しい条件を指定します。

**条件付き式に基づいて異なるストアリンクをレンダリングする**:

```
{%#if profile.homeAddress.countryCode = "FR"%}
  <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
{%else%}
  <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
{%/if%}
```

### ただし

**#** unleshelperは、条件付きブロックの定義に使用します。**#if**&#x200B;ヘルパーとは異なり、式評価がfalseを返した場合、ブロックがレンダリングされます。

**電子メールアドレスの拡張子に基づいてコンテンツをレンダリングする**:

```
{%#unless endsWith(profile.personalEmail.address, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content Content
{%/unless%}
```

### 各

**各**ヘルパーは、配列に対して反復処理を行うために使用します。
ヘルパーの構文は```{{#each ArrayName}}``` YourContent {{/each}}です
個々の配列項目は、ブロック内でキーワード**this**&#x200B;を使用して参照できます。 配列の要素のインデックスは、{{@index}}を使用してレンダリングできます。

例：

```
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
    </br>
{{/each}}
```

```
{{#each profile.homeAddress.city}}
  {{@index}} : {{this}}<br>
{{/each}}
```

**このユーザーが買い物かごに入れている商品のリストをレンダリングします**。

```
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
   </br>
{{/each}}
```

###  

template-partの評価トークンの変更には、**#with**&#x200B;ヘルパーを使用します。

例：

```
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

**#with**&#x200B;ヘルパーは、ショートカット変数も定義する場合に役立ちます。

**長い変数名を短い変数名にエイリアシングする場合に使用します**。

```
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```


## 制限事項

* **xEvent**&#x200B;変数は、パーソナライズ式では使用できません。 xEventを参照すると、検証エラーが発生します。

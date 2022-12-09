---
title: ヘルパー
description: ヘルパー
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: b08dc0f8-c85f-4aca-85eb-92dc76b0e588
source-git-commit: 44e87553b5a001414f28a972ec5c61947decdf55
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# ヘルパー {#gs-helpers}

## デフォルトのフォールバック値{#default-value}

`Default Fallback Value`このヘルパーは、属性が空または null の場合にデフォルトのフォールバック値を返すために使用されます。このメカニズムは、プロファイル属性と旅イベントに対して機能します。

**?**

```sql
Hello {%=profile.personalEmail.name.firstName ?: "there" %}!
```

この例では、このプロファイルの属性が空または null である場合 `firstName` 、値 `there` が表示されます。

## 下{#if-function}

ヘルパーは、 `if` 条件ブロックを定義するために使用されます。式の評価が true を返した場合は、ブロックがレンダリングされ、それ以外の場合はスキップされます。

**?**

```sql
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

`if`ヘルパーに従うと、同じ条件が偽である場合に、実行するコードブロックを指定するためのステートメントを入力 `else` することができます。`elseif`ステートメントには、最初のステートメントが false を返すかどうかをテストするための新しい条件を指定します。


**書式**

```sql
{
    {
        {%#if condition1%} element_1 
        {%else if condition2%} element_2 
        {%else%} default_element 
        {%/if%}
    }
}
```

**例**

1. **条件式に基づいて異なるストアリンクをレンダリングする**

   ```sql
   {%#if profile.homeAddress.countryCode = "FR"%}
   <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
   {%else%}
   <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
   {%/if%}
   ```

1. **電子メールアドレスの拡張機能の確認**

   ```sql
   {%#if contains(profile.personalEmail.address, ".edu")%}
   <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
   {%else if contains(profile.personalEmail.address, ".org")%}
   <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
   {%else%}
   <a href="https://www.adobe.com/users">Checkout our page</a>
   {%/if%}
   ```

1. **条件付きリンクの追加**

   次の操作を実行すると、「www.adobe.com/academia」 web サイトの「edu」電子メールアドレスにリンクが追加されます。 &#39; .org &#39; 電子メールアドレスを使用してプロファイルの「www.adobe.com/org」 web サイトに、その他すべてのプロファイルに対する初期設定の URL &#39; &#39; が表示されます。

   ```sql
   {%#if contains(profile.personalEmail.address, ".edu")%}
   <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
   {%else if contains(profile.personalEmail.address, ".org")%}
   <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
   {%else%}
   <a href="https://www.adobe.com/users">Checkout our page</a>
   {%/if%}
   ```

1. **セグメントメンバーシップに基づいた条件付きコンテンツ**

   ```sql
   {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
   Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
   {%else%} if 'profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"'%}
   Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
   {%/if%}
   ```

1. **プロファイルが既に属しているかどうかを確認する**

   ```sql
   {%#if profile.segmentMembership.get(segments.`123e4567-e89b-12d3-a456-426614174000`.id)%}
       You're a member!
   {%else%}
       You should be a member! Sign up now!
   {%/if%}
   ```

>[!NOTE]
>
>セグメンテーションとセグメンテーションのサービスについて詳しくは、次 [ の項 ](../../segment/about-segments.md) を参照してください。


## ない限り{#unless}

ヘルパーは、 `unless` 条件ブロックを定義するために使用されます。 式の評価が false を返す場合、ヘルパーと反対 `if`  に、このブロックはレンダリングされます。

**?**

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**一**

電子メールアドレスの拡張機能に基づいて、次のようにコンテンツをレンダリングします。

```sql
{%#unless endsWith(profile.personalEmail.address, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content Content
{%/unless%}
```

## 相互{#each}

ヘルパーは、配列に対して `each` 繰り返し処理を実行するために使用されます。ヘルパーのシンタックスは、コンテンツ {{/each}} を示し ```{{#each ArrayName}}``` ます。
ブロック内部のキーワード **this** を使用して、個々の配列項目を参照できます。配列のエレメントのインデックスは、を使用 {{@index}} してレンダリングできます。

**?**

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
    </br>
{{/each}}
```

**一**

```sql
{{#each profile.homeAddress.city}}
  {{@index}} : {{this}}<br>
{{/each}}
```

**一**

このユーザーがカートにある製品のリストを表示します。

```sql
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
   </br>
{{/each}}
```

## With{#with}

`with`ヘルパーは、テンプレートパーツの評価トークンを変更するために使用されます。

**?**

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

ヘルパーは、 `with` ショートカット変数を定義する場合にも便利です。

**一**

With を使用して、長い変数名をより短い名前にエイリアスする方法を示します。

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

## Let{#let}

この関数を使用して、 `let` 式を変数として格納し、後で使用することができます。

**?**

```sql
{% let variable = expression %} {{variable}}
```

**一**

次の例では、合計が $100 より大きく $1000 よりも大きい場合に、トランザクションを使用してすべての製品合計の合計を USD で指定します。

```sql
{% let variable = expression %} {{variable}}
```

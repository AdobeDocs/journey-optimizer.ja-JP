---
title: ヘルパー
description: ヘルパー
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 60%

---


# ヘルパー {#gs-helpers}

![](../../assets/do-not-localize/badge.png)


## 条件{#if-function}

`if` ヘルパーは、条件ブロックを定義します。
式の評価が true を返す場合、ブロックはレンダリングされます。true を返さない場合はスキップされます。

**構文**

```sql
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

`if` ヘルパーの後に、`else` ステートメントを入力して、同じ条件が false の場合に実行するコードのブロックを指定できます。
`elseif` ステートメントは、最初のステートメントが false を返した場合にテストする新しい条件を指定します。


**形式**

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

1. **条件式に基づいて異なるストアリンクをレンダリング**

   ```sql
   {%#if profile.homeAddress.countryCode = "FR"%}
   <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
   {%else%}
   <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
   {%/if%}
   ```

1. **Eメールアドレスの拡張を決定する**

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

   次の操作では、「.edu」のEメールアドレスを持つプロファイルの場合のみ、「www.adobe.com/org&#39;」のWebサイトへのリンクを「.org」のEメールアドレスを持つプロファイルの場合は、その他のすべてのプロファイルの場合は、デフォルトURL「www.adobe.com/users&#39;」に追加します。

   ```sql
   {%#if contains(profile.personalEmail.address, ".edu")%}
   <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
   {%else if contains(profile.personalEmail.address, ".org")%}
   <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
   {%else%}
   <a href="https://www.adobe.com/users">Checkout our page</a>
   {%/if%}
   ```

1. **セグメントメンバーシップに基づく条件付きコンテンツ**

   ```sql
   {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
   Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
   {%else%} if 'profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"'%}
   Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
   {%/if%}
   ```

1. **プロファイルが既にメンバーであるかどうかを確認する**

   ```sql
   {%#if profile.segmentMembership.get(segments.`123e4567-e89b-12d3-a456-426614174000`.id)%}
       You're a member!
   {%else%}
       You should be a member! Sign up now!
   {%/if%}
   ```

>[!NOTE]
>
>セグメント化とセグメント化サービスの詳細については、こちらの[節](../../segment/about-segments.md)を参照してください。


## Unless{#unless}

`unless` ヘルパーは、条件ブロックを定義します。
`if`ヘルパーとの対立により、式の評価がfalseを返した場合、ブロックがレンダリングされます。

**構文**

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**例**

メールアドレスの拡張子に基づいてコンテンツをレンダリングする：

```sql
{%#unless endsWith(profile.personalEmail.address, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content Content
{%/unless%}
```

## Each{#each}

`each` ヘルパーは、配列に対して反復処理をおこなうために使用します。
ヘルパーの構文は ```{{#each ArrayName}}``` YourContent {{/each}}です
個々の配列項目は、ブロック内でキーワード **this** を使用して参照できます。配列の要素のインデックスは、{{@index}} を使用してレンダリングできます。

**構文**

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
    </br>
{{/each}}
```

**例**

```sql
{{#each profile.homeAddress.city}}
  {{@index}} : {{this}}<br>
{{/each}}
```

**例**

このユーザーが買い物かごに入れている商品のリストをレンダリングする：

```sql
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
   </br>
{{/each}}
```

## With{#with}

template-partの評価トークンを変更するには、 `with`ヘルパーを使用します。

**構文**

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

`with`ヘルパーは、ショートカット変数を定義する場合にも役立ちます。

**例**

長い変数名を短い変数名にエイリアシングする場合に使用する：

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

## Let{#let}

`let` 関数を使用すると、式を変数として保存し、後からクエリで使用できます。

**構文**

```sql
{% let variable = expression %} {{variable}}
```

**例**

次の例では、合計が$100以上$1,000未満のトランザクションでの製品合計の合計をすべて米ドルで示します。

```sql
{% let variable = expression %} {{variable}}
```

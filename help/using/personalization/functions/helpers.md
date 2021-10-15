---
title: ヘルパー
description: ヘルパー
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: b08dc0f8-c85f-4aca-85eb-92dc76b0e588
source-git-commit: 5df4856c7be31a75116d906320ae50cd5dc6a2dc
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 100%

---

# ヘルパー {#gs-helpers}

## デフォルトのフォールバック値{#default-value}

`Default Fallback Value` ヘルパーは、属性が空または null の場合にデフォルトのフォールバック値を返すために使用されます。 このメカニズムは、プロファイル属性とジャーニーイベントで機能します。

**構文**

```sql
Hello {%=profile.personalEmail.name.firstName ?: 'there' %}!
```

この例では、このプロファイルの `firstName` 属性が空または null の場合、`there` という値が表示されます。

## 条件{#if-function}

`if` ヘルパーを使用して、条件ブロックを定義します。
式の評価結果が true の場合、ブロックはレンダリングされます。true でない場合はスキップされます。

**構文**

```sql
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

`if` ヘルパーの後に、`else` ステートメントを入れて、その条件の結果が false の場合に実行するコードのブロックを指定することもできます。
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

1. **条件式に基づいて異なるストアのリンクをレンダリングする**

   ```sql
   {%#if profile.homeAddress.countryCode = "FR"%}
   <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
   {%else%}
   <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
   {%/if%}
   ```

1. **メールアドレスの拡張子の判断**

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

   次の操作では、メールアドレスが「.edu」のプロファイルについては web サイト「www.adobe.com/academia」へのリンク、メールアドレスが「.org」のプロファイルについては「www.adobe.com/org」へのリンク、その他のすべてのプロファイルについてはデフォルトの URL「www.adobe.com/users」へのリンクを追加します。

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

1. **プロファイルがすでにメンバーであるか判断する**

   ```sql
   {%#if profile.segmentMembership.get(segments.`123e4567-e89b-12d3-a456-426614174000`.id)%}
       You're a member!
   {%else%}
       You should be a member! Sign up now!
   {%/if%}
   ```

>[!NOTE]
>
>セグメント化とセグメント化サービスの詳細については、[この節](../../segment/about-segments.md)を参照してください。


## Unless{#unless}

`unless` ヘルパーを使用して、条件ブロックを定義します。`if` ヘルパーとは異なり、式の評価結果が false の場合にブロックがレンダリングされます。

**構文**

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**例**

メールアドレスの拡張子に基づいてコンテンツをレンダリングする。

```sql
{%#unless endsWith(profile.personalEmail.address, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content Content
{%/unless%}
```

## Each{#each}

`each` ヘルパーを使用して、配列に対して反復処理を行います。
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

ユーザーが買い物かごに入れた商品のリストをレンダリングする。

```sql
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
   </br>
{{/each}}
```

## With{#with}

`with` ヘルパーを使用して、template-part の評価トークンを変更します。

**構文**

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

`with` ヘルパーは、ショートカット変数を定義する場合にも使用できます。

**例**

with は、長い変数名に短い別名を付ける場合にも使用できます。

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

次の例では、合計が $100 以上 $1,000 未満のトランザクションで、すべての製品合計を米ドルで示します。

```sql
{% let variable = expression %} {{variable}}
```

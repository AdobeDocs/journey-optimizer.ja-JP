---
title: ヘルパー
description: ヘルパー
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: b08dc0f8-c85f-4aca-85eb-92dc76b0e588
source-git-commit: 221368c7766e942143639fcd554b32f9de5ab0c9
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 94%

---

# ヘルパー {#gs-helpers}

## デフォルトのフォールバック値{#default-value}

`Default Fallback Value` ヘルパーは、属性が空または null の場合にデフォルトのフォールバック値を返すために使用されます。このメカニズムは、プロファイル属性とジャーニーイベントで機能します。

**構文**

```sql
Hello {%=profile.personalEmail.name.firstName ?: "there" %}!
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

1. **オーディエンスメンバーシップに基づく条件付きコンテンツ**

   ```sql
   {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
   Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
   {%else if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"%}
   Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
   {%/if%}
   ```

>[!NOTE]
>
>オーディエンスとセグメント化サービスについて詳しくは、[この節](../../audience/about-audiences.md)を参照してください。


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
Some edu specific content
{%/unless%}
```

## Each{#each}

`each` ヘルパーを使用して、配列に対して反復処理を行います。
ヘルパーの構文は ```{{#each ArrayName}}``` YourContent `{{/each}}` です。
個々の配列項目は、ブロック内でキーワード **this** を使用して参照できます。配列の要素のインデックスは、`{{@index}}` を使用してレンダリングできます。

**構文**

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
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
{{/each}}
```

>[!NOTE]
>
>また、`each` ヘルパーを使用して、カスタムアクション応答から返された配列に対して反復処理を行うこともできます。 カスタムアクション応答からネストされた配列を反復する例については、[&#x200B; ネイティブチャネルでのカスタムアクション応答の使用 &#x200B;](../../action/action-response.md#response-in-channels) を参照してください。

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

次の例では、買い物かご内の価格が 100～1000 の製品の合計価格を計算できます。

```sql
{% let sum = 0%}
    {{#each profile.productsInCart as |p|}}
        {%#if p.price>100 and p.price<1000%}
            {%let sum = sum + p.price %}
        {%/if%}
    {{/each}}
{{sum}}
```

## 実行メタデータ {#execution-metadata}

>[!AVAILABILITY]
>
>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。

`executionMetadata` ヘルパーを使用すると、カスタムのキーと値のペアを動的にキャプチャして、メッセージ実行コンテキストに保存できます。

**構文**

```
{{executionMetadata key="your_key" value="your_value"}}
```

この構文では、`key` はメタデータ名を参照し、`value` は保持するメタデータです。

**ユースケース**

この関数を使用すると、キャンペーンやジャーニーの任意のネイティブアクションにコンテキスト情報を追加できます。これにより、トラッキング、分析、パーソナライゼーション、ダウンストリーム処理などの様々な目的で、リアルタイム配信のコンテキストデータを外部システムに書き出すことができます。

>[!NOTE]
>
>実行メタデータ関数は、[カスタムアクション](../../action/action.md)ではサポートされていません。

例えば、実行メタデータヘルパーを使用して、各プロファイルに送信される各配信に特定の ID を追加できます。 この情報は実行時に生成され、強化された実行メタデータは外部レポートプラットフォームとのダウンストリームの紐付けのためにエクスポートできます。

**仕組み**

キャンペーンまたはジャーニー内のチャネルコンテンツから任意の要素を選択し、パーソナライゼーションエディターを使用して、この要素に `executionMetadata` ヘルパーを追加します。

>[!NOTE]
>
>コンテンツ自体が表示される場合、実行メタデータ関数は表示されません。


実行時に、次のスキーマの追加と共に、メタデータ値が既存の&#x200B;**[!UICONTROL メッセージフィードバックイベントデータセット]**&#x200B;に追加されます。

```
"_experience": {
  "customerJourneyManagement": {
    "messageExecution": {
      "metadata": {
        "your_key": "your_value"
      }
    }
  }
}
```

>[!NOTE]
>
>データセットについて詳しくは、[この節](../../data/get-started-datasets.md)を参照してください。

**制限事項**

アクションごとのキーと値のペアには 2 kb の上限があります。

2Kb の制限を超えた場合、メッセージは引き続き配信されますが、キーと値のペアのいずれかが切り捨てられる場合があります。

**例**

```
{{executionMetadata key="firstName" value=profile.person.name.firstName}}
```

この例では、`profile.person.name.firstName` = &quot;Alex&quot; と想定すると、結果のエンティティは次のようになります。

```
{
  "key": "firstName",
  "value": "Alex"
}
```


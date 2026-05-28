---
title: 配列関数ライブラリ
description: 配列関数ライブラリ
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: dfe611fb-9c50-473c-9eb7-b983e1e6f01e
TQID: https://experienceleague.adobe.com/CUiT5GFH9o4q-oOSWuKC8ZyLbRbH9lj88M92LhMIX9E
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
feature_v2: id: fda7be7c-b81e-42c0-95a9-616e5b893c03
subfeature_v2: []
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 742
ht-degree: 79%

---

# 配列およびリスト関数 {#arrays}

これらの関数を使用すると、配列、リスト、および文字列の操作が容易になります。

## null のみをカウント {#count-only-null}

この `countOnlyNull` 関数は、リスト内の null 値の数をカウントするために使用されます。

**構文**

```sql
{%= countOnlyNull(array) %}
```

**例**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

3 を返します。

## null でカウント {#count-with-null}

この `countWithNull` 関数は、null 値を含むリストのすべての要素をカウントするために使用されます。

**構文**

```sql
{%= countWithNull(array) %}
```

**例**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

6 を返します。

## 個別{#distinct}

`distinct` 関数は、重複値を削除して配列またはリストから値を取得するために使用します。

**構文**

```sql
{%= distinct(array) %}
```

**例**

次の操作は、複数の店舗で注文した人物を特定します。

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

## nullを持つ個別カウント {#distinct-count-with-null}

この `distinctCountWithNull` 関数は、null 値を含むリスト内の異なる値の数をカウントするために使用されます。

**構文**

```sql
{%= distinctCountWithNull(array) %}
```

**例**

```sql
{%= distinctCountWithNull([10,2,10,null]) %}
```

3 を返します。

## 最初の項目{#head}

`head` 関数は、配列またはリスト内の最初の項目を返すために使用されます。

**構文**

```sql
{%= head(array) %}
```

**例**

次の操作は、最も金額が高い注文の上位 5 件のうち最初の項目を返します。 `topN` 関数の詳細については、[配列の最初の `n`](#first-n)の節を参照してください 。

```sql
{%= head(topN(orders,price, 5)) %}
```

## 配列の最初の N 個を並べ替えて取得 {#first-n}

`topN` 関数は、指定した数値式に基づいて配列を降順に並べ替えて、最初の `N` 個の項目を返します。 配列のサイズが `N` 個未満の場合は、並べ替えられた配列全体を返します。

この関数
**構文**

```sql
{%= topN(array, value, amount) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{ARRAY}` | 並べ替えるリストまたは配列。 |
| `{VALUE}` | 配列またはリストを並べ替えるプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の操作は、最も金額が低い注文の最初の 5 件を返します。

```sql
{%= topN(orders,price, 5) %}
```

## 次に含まれる{#in}

`in` 関数は、項目が配列またはリストのメンバーであるかどうかを判断するために使用されます。

**構文**

```sql
{%= in(value, array) %}
```

**例**

次の操作は、誕生日が 3 月、6 月または 9 月の人を定義します。

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

## 次を含む{#includes}

`includes` 関数は、配列またはリストに特定の項目が含まれているかどうかを判断るために使用されます。

**構文**

```sql
{%= includes(array,item) %}
```

**例**

次の操作は、お気に入りの色に赤が含まれる人物を定義します。

```sql
{%= includes(person.favoriteColors,"red") %}
```

## 交わり{#intersects}

`intersects` 関数は、2つの配列またはリストに、共通メンバーが 1 つ以上あるかどうかを判断するために使用されます。

**構文**

```sql
{%= intersects(array1, array2) %}
```

**例**

次の操作は、お気に入りの色に赤、青、緑のうち 1 つ以上が含まれる人を定義します。

```sql
{%= intersects(person.favoriteColors,["red", "blue", "green"]) %}
```


<!--
## Intersection{#intersection}

The `intersection` function is used to determine the common members of two arrays or lists.

**Syntax**

```sql
intersection({ARRAY},{ARRAY})
```

**Example**

The following operation defines if person 1 and person 2 both have favorite colors of red, blue, and green.

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```
-->

## 配列の最後の N 個を並べ替えて取得 {#last-n}

`bottomN` 関数は、指定した数値式に基づいて配列を昇順に並べ替えて、最初の `N` 個の項目を返します。 配列のサイズが `N` 個未満の場合は、並べ替えられた配列全体を返します。

**構文**

```sql
{%= bottomN(array, value, amount) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{ARRAY}` | 並べ替えるリストまたは配列。 |
| `{VALUE}` | 配列またはリストを並べ替えるプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の操作は、最も金額が高い注文の最後の 5 件を返します。

```sql
{%= bottomN(orders,price, 5) %}
```

## 次に含まれない{#notin}

`notIn` 関数は、項目が配列またはリストのメンバーでないかどうかを判断するために使用されます。

>[!NOTE]
>
>この`notIn` 関数は&#x200B;*また*、どの値も NULL ではないことを保証します。 したがって、結果は `in` 関数の完全な否定ではありません。

**構文**

```sql
{%= notIn(value, array) %}
```

**例**

次の操作は、誕生日が 3 月、6 月または 9 月でない人を定義します。

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```


## サブセット{#subset}

`subsetOf` 関数は、特定の配列（配列 A）が別の配列（配列 B）のサブセットであるかを判断するために使用されます。 つまり、配列 A 内のすべての要素が配列 B の要素であるということです。

**構文**

```sql
{%= subsetOf(array1, array2) %}
```

**例**

次の操作は、お気に入りの都市をすべて訪問した人を定義します。

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

## スーパーセット{#superset}

`supersetOf` 関数は、特定の配列（配列 A）が別の配列（配列 B）のスーパーセットであるかを判断するために使用されます。 つまり、その配列 Aには配列 B のすべての要素が含まれます。

**構文**

```sql
{%= supersetOf(array1, array2) %}
```

**例**

次の操作は、寿司とピザを 1 回以上食べたことがある人を定義しています。

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"]) %}
```

## 配列の繰り返し {#each-loop}

Handlebars `{{#each}}` ブロックヘルパーを使用して、配列をループし、**パーソナライズされたコンテンツ** （電子メール、SMS、プッシュ）の各項目のコンテンツをレンダリングします。

>[!NOTE]
>
>`{{#each}}`は、**パーソナライゼーションエディター**&#x200B;でのみ利用できます（メール本文、SMS、プッシュコンテンツ）。 ジャーニー条件アクティビティでは&#x200B;**not**&#x200B;がサポートされています。 ジャーニー条件内の配列から項目をフィルタリングまたは一致させるには、代わりに[ コレクション管理関数](../../building-journeys/expression/collection-management-functions.md)を使用します。

**構文**

```handlebars
{{#each arrayAttribute}}
  {{this}}
{{/each}}
```

+++例 – 配列内のすべての項目のリスト

```handlebars
{{#each profile.purchases.items}}
  - {{this.name}}: {{this.price}}€
{{/each}}
```

出力（例）:

```
- Running shoes: 89€
- Water bottle: 15€
- Gym bag: 45€
```

+++

+++例 – ループインデックスへのアクセス

`@index`を使用して、現在のループ位置（0 ベース）にアクセスします。

```handlebars
{{#each profile.preferences.languages}}
  {{@index}}: {{this}}
{{/each}}
```

出力（例）:

```
0: English
1: French
2: Spanish
```

+++

+++例 – ループ内の条件付きレンダリング

条件が満たされたときにのみコンテンツをレンダリングするには、`{{#each}}`内の`{%#if%}` ブロックを使用します。

>[!NOTE]
>
>`{% if %}` / `{% endif %}`はサポートされていません。 代わりに`{%#if%}` / `{%/if%}`を使用してください。 また、`this.<field>`はPQL条件式では機能しません。属性名（`order.status`など）を使用してフィールドを直接参照してください。

```handlebars
{{#each profile.orders as |order|}}
  {%#if order.status = "pending"%}
  Your order {{order.id}} is still pending.
  {%/if%}
{{/each}}
```

これは、「条件付きブレーク」をシミュレートするために推奨されるパターンです。条件に一致する項目のみが出力を生成します。

+++

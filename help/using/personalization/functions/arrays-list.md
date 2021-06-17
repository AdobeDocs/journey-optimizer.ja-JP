---
title: 配列関数ライブラリ
description: 配列関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 66%

---

# 配列およびリスト関数 {#arrays}

これらの関数を使用すると、配列、リスト、文字列とのやり取りが容易になります。

## Distinct{#distinct}

`distinct`関数は、重複値が削除された配列またはリストから値を取得するために使用されます。

**形式**

```sql
{%= distinct(array) %}
```

**例**

次の操作は、複数の店舗で注文した人を指定します。

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

## First item{#head}

`head` 関数は、配列またはリスト内の最初の項目を返すために使用されます。

**形式**

```sql
{%= head({array}) %}
```

**例**

次の演算は、最も高い価格を持つ上位5件の注文の最初の値を返します。 `topN` 関数の詳細については、[配列の最初の `n` 個](#first-n)の節を参照してください 。

```sql
{%= head(topN(orders,price, 5)) %}
```

## 配列の`n`最初の {#first-n}

`topN` 関数は、指定した数値式に基づいて昇順で並べ替えられた場合、配列の最初の `N` 項目を返すために使用します。

**形式**

```sql
{%= topN(array, value, amount) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{ARRAY}` | 並べ替えるリストまたは配列。 |
| `{VALUE}` | 配列またはリストを並べ替えるプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の操作は、最も高い価格の上位5件の注文を返します。

```sql
{%= topN(orders,price, 5) %}
```

## In{#in}

`in` 関数は、項目が配列またはリストのメンバーであるかどうかを判断するために使用されます。

**形式**

```sql
{%= in(value, array) %}
```

**例**

次の操作は、誕生日が3月、6月または9月の人を定義します。

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

## Includes{#includes}

`includes` 関数は、配列またはリストに特定の項目が含まれているかどうかを判断るために使用されます。

**形式**

```sql
{%= includes(array,item) %}
```

**例**

次の操作は、お気に入りの色に赤が含まれる人を定義します。

```sql
{%= includes(person.favoriteColors,"red") %}
```

## Intersects{#intersects}

`intersects` 関数は、2つの配列またはリストに、共通メンバーが 1 つ以上あるかどうかを判断するために使用されます。

**形式**

```sql
{%= intersects(array1, array2) %}
```

**例**

次の操作は、お気に入りの色に赤、青、緑の少なくとも1つが含まれる人を定義します。

```sql
{%= intersects(person.favoriteColors,["red", "blue", "green"]) %}
```


<!-- ## Intersection{#intersection}

The `intersection` function is used to determine the common members of two arrays or lists.

**Format**

```sql
intersection({ARRAY},{ARRAY})
```

**Example**

The following operation defines if person 1 and person 2 both have favorite colors of red, blue, and green.

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```
-->

## Last `n` in array{#last-n}

`bottomN` 関数は、指定した数値式に基づいて昇順で並べ替えられた場合、配列の最後の `N` 項目を返すために使用します。

**形式**

```sql
{%= bottomN(array, value, amount) %}
```

| 引数 | 説明 |
| --------- | ----------- | 
| `{ARRAY}` | 並べ替えるリストまたは配列。 |
| `{VALUE}` | 配列またはリストを並べ替えるプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の操作は、最も安い価格の上位5件の注文を返します。

```sql
{%= bottomN(orders,price, 5) %}
```


## Not in{#notin}

`notIn` 関数は、項目が配列またはリストのメンバーでないかどうかを判断するために使用されます。

>[!NOTE]
>
>この`notIn` 関数は&#x200B;*また*、どの値も NULL ではないことを保証します。したがって、結果は `in` 関数の完全な否定ではありません。

**形式**

```sql
{%= notIn(value, array) %}
```

**例**

次の操作は、誕生日が3月、6月または9月でない人を定義します。

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```


## Subset of{#subset}

`subsetOf` 関数は、特定の配列（配列 A）が別の配列（配列 B）のサブセットであるかを判断するために使用されます。つまり、配列 A 内のすべての要素が配列 B の要素であるということです。

**形式**

```sql
{%= subsetOf(array1, array2) %}
```

**例**

次の操作は、お気に入りの都市をすべて訪問した人を定義します。

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

## Superset of{#superset}

`supersetOf` 関数は、特定の配列（配列 A）が別の配列（配列 B）のスーパーセットであるかを判断するために使用されます。つまり、その配列 Aには配列 B のすべての要素が含まれます。

**形式**

```sql
{%= supersetOf(array1, array2) %}
```

**例**

寿司とピザを1回以上食べた人を定義する。

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"] %}
```








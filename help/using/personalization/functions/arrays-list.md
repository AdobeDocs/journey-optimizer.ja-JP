---
title: 関数ライブラリ
description: 関数ライブラリ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 96%

---

# 配列とリスト関数{#arrays}

![](../../assets/do-not-localize/badge.png)

[!DNL Profile Query Language] (PQL)オファーは、配列、リスト、文字列とのやり取りを容易にするために機能します。

## In

`in` 関数は、項目が配列またはリストのメンバーであるかどうかを判断するために使用されます。

**形式**

```sql
in ({VALUE},{ARRAY})
```

**例**

次の PQL クエリは、誕生日が 3 月、6 月または 9 月の人を定義します。

```sql
in (person.birthMonth, [3, 6, 9])
```

## Not in

`notIn` 関数は、項目が配列またはリストのメンバーでないかどうかを判断するために使用されます。

>[!NOTE]
>
> `notIn`また&#x200B;*、* 関数は、いずれの値も null に等しくないことを確認します。したがって、結果は `in` 関数の完全な否定ではありません。

**形式**

```sql
notIn ({VALUE},{ARRAY})
```

**例**

次の PQL クエリは、誕生日が 3 月、6 月または 9 月でない人を定義します。

```sql
notIn (person.birthMonth ,[3, 6, 9])
```

## Intersects

`intersects` 関数は、2つの配列またはリストに、共通メンバーが 1 つ以上あるかどうかを判断するために使用されます。

**形式**

```sql
intersects({ARRAY},{ARRAY})
```

**例**

次の PQL クエリは、お気に入りの色に赤、青、緑の1 つ以上が含まれる人を定義します。

```sql
intersects(person.favoriteColors,["red", "blue", "green"])
```

## Intersection

`intersection` 関数は、2 つの配列またはリストの共通メンバーを判断するために使用されます。

**形式**

```sql
intersection({ARRAY},{ARRAY})
```

**例**

次の PQL クエリは、人物 1 と人物 2 の両方が、お気に入りの色を赤、青、および緑としているかどうかを定義します。

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```

## Subset of

`subsetOf` 関数は、特定の配列（配列 A）が別の配列（配列 B）のサブセットであるかを判断するために使用されます。つまり、配列 A 内のすべての要素が配列 B の要素であるということです。

**形式**

```sql
subsetOf({ARRAY},{ARRAY})
```

**例**

次の PQL クエリは、お気に入りの都市をすべて訪問した人を定義します。

```sql
subsetOf(person.favoriteCities,person.visitedCities)
```

## Superset of

`supersetOf` 関数は、特定の配列（配列 A）が別の配列（配列 B）のスーパーセットであるかを判断するために使用されます。つまり、その配列 Aには配列 B のすべての要素が含まれます。

**形式**

```sql
supersetOf({ARRAY},{ARRAY})
```

**例**

次の PQL クエリは、寿司とピザを 1 回以上食べたことがある人を定義しています。

```sql
supersetOf(person.eatenFoods,["sushi", "pizza"])
```

## Includes

`includes` 関数は、配列またはリストに特定の項目が含まれているかどうかを判断るために使用されます。

**形式**

```sql
includes({ARRAY},{ITEM})
```

**例**

次の PQL クエリは、お気に入りの色に赤が含まれる人物を定義します。

```sql
includes(person.favoriteColors,"red")
```

## Distinct

`distinct` 関数は、配列またはリストから重複値を削除するために使用されます。

**形式**

```sql
distinct({ARRAY})
```

**例**

次の PQL クエリは、複数の店舗で注文した人物を指定します。

```sql
distinct(person.orders.storeId).count() > 1
```

## First `n` in array {#first-n}

`topN` 関数は、指定した数値式に基づいて昇順で並べ替えられた場合、配列の最初の `N` 項目を返すために使用します。

**形式**

```sql
topN({ARRAY},{VALUE}, {AMOUNT})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{ARRAY}` | 並べ替えるリストまたは配列。 |
| `{VALUE}` | 配列またはリストを並べ替えるプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の PQL クエリは、最も金額が高い注文上位 5 件を返します。

```sql
topN(orders,price, 5)
```

## Last `n` in array

`bottomN` 関数は、指定した数値式に基づいて昇順で並べ替えられた場合、配列の最後の `N` 項目を返すために使用します。

**形式**

```sql
bottomN({ARRAY},{VALUE}, {AMOUNT})
```

| 引数 | 説明 |
| --------- | ----------- | 
| `{ARRAY}` | 並べ替えるリストまたは配列。 |
| `{VALUE}` | 配列またはリストを並べ替えるプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の PQL クエリは、最も金額が低い注文上位 5 件を返します。

```sql
bottomN(orders,price, 5)
```

## First item

`head` 関数は、配列またはリスト内の最初の項目を返すために使用されます。

**形式**

```sql
head({ARRAY})
```

**例**

次の PQL クエリは、最も金額が高い注文上位 5 件の最初の項目を返します。`topN` 関数の詳細については、[first `n` in array](#first-n) の節を参照してください 。

```sql
head(topN(orders,price, 5))
```

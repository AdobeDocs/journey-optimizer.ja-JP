---
title: 配列関数ライブラリ
description: 配列関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: dfe611fb-9c50-473c-9eb7-b983e1e6f01e
source-git-commit: 2160d52f24af50417cdcf8c6ec553b746a544c2f
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# 配列とリスト関数 {#arrays}

これらの関数を使用して、配列、リスト、ストリングの操作を容易にすることができます。

## Count null のみ {#count-only-null}

`countOnlyNull`この関数は、リスト内の null 値の数をカウントするために使用されます。

**書式**

```sql
{%= countOnlyNull(array) %}
```

**一**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

3を返します。

## 数が Null の場合 {#count-with-null}

`countWithNull`この関数を使用して、null 値を含むリストのすべてのエレメントを数えます。

**書式**

```sql
{%= countWithNull(array) %}
```

**一**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

6を返します。

## 異なっ{#distinct}

この関数は、 `distinct` 重複した値が削除された配列またはリストから値を取得するために使用されます。

**書式**

```sql
{%= distinct(array) %}
```

**一**

次の例では、複数のストアに注文を出した人物を指定します。

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

## Null 値を持つ個別カウント {#distinct-count-with-null}

`distinctCountWithNull`この関数を使用して、null 値を含むリスト内の異なる値の数を数えます。

**書式**

```sql
{%= distinctCountWithNull(array) %}
```

**一**

```sql
{%= distinctCountWithNull([10,2,10,null]) %}
```

3を返します。

## 最初の項目{#head}

`head`この関数は、配列またはリストの最初のアイテムを返すために使用されます。

**書式**

```sql
{%= head(array) %}
```

**一**

次の例では、上位5番目の注文のうち、最も高い価格の最初の注文を返します。 この関数について詳しくは、配列 ](#first-n) の最初 `n` の [ 項を参照して `topN` ください。

```sql
{%= head(topN(orders,price, 5)) %}
```

## 最初 `n` の配列 {#first-n}

`topN`この関数は、指定された数値式に基づいて昇順にソートした場合に、配列内の最初 `N` のアイテムを返すために使用されます。

**書式**

```sql
{%= topN(array, value, amount) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{ARRAY}` | 並べ替えの対象となる配列またはリストを指定します。 |
| `{VALUE}` | 配列またはリストの並べ替えを行うプロパティ。 |
| `{AMOUNT}` | 返される項目の数を指定します。 |

**一**

次の例では、最も高い価格の上位5件の注文を返します。

```sql
{%= topN(orders,price, 5) %}
```

## 単位{#in}

この関数は、項目が配列またはリストのいずれかに属して `in` いるかどうかを判別するために使用されます。

**書式**

```sql
{%= in(value, array) %}
```

**一**

次の操作では、3月、6月、9月の誕生日が含まれるユーザーを定義します。

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

## あり{#includes}

この関数は、 `includes` 配列またはリストに特定のアイテムが含まれているかどうかを調べるために使用されます。

**書式**

```sql
{%= includes(array,item) %}
```

**一**

次の操作は、好きな色が赤で表示される人を定義します。

```sql
{%= includes(person.favoriteColors,"red") %}
```

## 交わる{#intersects}

この関数は、2つの `intersects` 配列またはリストに共通のメンバーが少なくとも1つあるかどうかを判別するために使用されます。

**書式**

```sql
{%= intersects(array1, array2) %}
```

**一**

次の操作では、赤、青、緑のうち、少なくとも1つを含む色を含むユーザーを定義します。

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

## 最後 `n` の配列{#last-n}

`bottomN`この関数を使用して、指定した数値式に基づいて、配列内の最後 `N` の項目を返します。

**書式**

```sql
{%= bottomN(array, value, amount) %}
```

| 指定 | つい |
| --------- | ----------- | 
| `{ARRAY}` | 並べ替えの対象となる配列またはリストを指定します。 |
| `{VALUE}` | 配列またはリストの並べ替えを行うプロパティ。 |
| `{AMOUNT}` | 返される項目の数を指定します。 |

**一**

次の例では、価格が最も低い上位5件の注文を返します。

```sql
{%= bottomN(orders,price, 5) %}
```

## ではありません{#notin}

この関数は、 `notIn` 項目が配列またはリストのメンバーでないかどうかを判別するために使用されます。

>[!NOTE]
>
>この関数 ** では、 `notIn` どちらの値も null とは見なされません。そのため、結果は関数の `in` 厳密な否定にはなりません。

**書式**

```sql
{%= notIn(value, array) %}
```

**一**

次の操作では、3月、6月、9月以外の誕生日が含まれるユーザーを定義します。

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```


## サブセット{#subset}

この関数を使用して `subsetOf` 、特定の配列 (Array a) が別の配列のサブセットであるかどうか (配列 B) を判断します。 つまり、配列 A のすべてのエレメントは、配列 B のエレメントになります。

**書式**

```sql
{%= subsetOf(array1, array2) %}
```

**一**

以下の操作によって、お気に入りの都市をすべて訪れたことのある人物が定義されます。

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

## のスーパーセット{#superset}

この関数を使用して `supersetOf` 、特定の配列 (配列 a) が別の配列のスーパーセットであるかどうかを確認します (配列 B)。 つまり、配列 A には配列 B のすべてのエレメントが含まれています。

**書式**

```sql
{%= supersetOf(array1, array2) %}
```

**一**

次の操作は、少なくとも1回は eaten sushi およびピザを持っているユーザーを定義します。

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"] %}
```

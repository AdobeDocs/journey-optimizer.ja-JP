---
title: 関数ライブラリ
description: 関数ライブラリ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 99%

---

# 演算子 {#operators}

![](../../assets/do-not-localize/badge.png)

## And

`and` 関数は、論理積を作成するために使用されます。

**形式**

```sql
{QUERY} and {QUERY}
```

**例**

次の PQL クエリは、住んでいる国がカナダで、生まれた年が 1985 年のすべての人を返します。

```sql
homeAddress.countryISO = "CA" and person.birthYear = 1985
```

## Or

`or` 関数は、論理和を作成するために使用されます。

**形式**

```sql
{QUERY} or {QUERY}
```

**例**

次の PQL クエリは、住んでいる国がカナダか、生まれた年が 1985 年のすべての人を返します。

```sql
homeAddress.countryISO = "CA" or person.birthYear = 1985
```

## Not

`not`（または `!`）関数は、論理否定を作成するために使用されます。

**形式**

```sql
not ({QUERY})
!({QUERY})
```

**例**

次の PQL クエリは、住んでいる国がカナダでないすべての人を返します。

```sql
not (homeAddress.countryISO = "CA")
```

## If

`if` 関数は、指定した条件が true かどうかに応じて式を解決するために使用されます。

**形式**

```sql
if ({TEST_EXPRESSION}, {TRUE_EXPRESSION}, {FALSE_EXPRESSION})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{TEST_EXPRESSION}` | テストされているブール式。 |
| `{TRUE_EXPRESSION}` | `{TEST_EXPRESSION}` が true の場合に値が使用される式。 |
| `{FALSE_EXPRESSION}` | `{TEST_EXPRESSION}` が false の場合に値が使用される式。 |

**例**

次の PQL クエリは、住んでいる国がカナダの場合は値を `1` に設定し、住んでいる国がカナダでない場合は `2` に設定します。

```sql
if (homeAddress.countryISO = "CA", 1, 2)
```

## Equals

`=`（equals）関数は、ある値または式が別の値または式と等しいかどうかを確認します。

**形式**

```sql
{EXPRESSION} = {VALUE}
```

**例**

次の PQL クエリは、自宅住所の国がカナダにあるかどうかを確認します。

```sql
homeAddress.countryISO = "CA"
```

## Not equal

`!=`（not equal）関数は、ある値または式が別の値または式と等しく&#x200B;**ない**&#x200B;かどうかを確認します。

**形式**

```sql
{EXPRESSION} != {VALUE}
```

**例**

次の PQL クエリは、自宅住所の国がカナダにないかどうかを確認します。

```sql
homeAddress.countryISO != "CA"
```

## Greater than

`>`（greater than）関数は、最初の値が 2 番目の値より大きいかどうかを確認するために使用します。

**形式**

```sql
{EXPRESSION} > {EXPRESSION} 
```

**例**

次の PQL クエリでは、1 月または 2 月に誕生日が該当しない人を定義します。

```sql
person.birthMonth > 2
```

## Greater than or equal to

`>=`（greater than or equal to）は、1 つ目の値が 2 つ目の値以上かどうかを確認するために使用されます。

**形式**

```sql
{EXPRESSION} >= {EXPRESSION} 
```

**例**

次の PQL クエリでは、誕生日が 1 月または 2 月に該当しない人を定義します。

```sql
person.birthMonth >= 3
```

## Less than

`<`（less than）比較関数は、最初の値が 2 番目の値より小さいかどうかを調べるために使用されます。

**形式**

```sql
{EXPRESSION} < {EXPRESSION} 
```

**例**

次の PQL クエリは、誕生日が 1 月に該当する人を定義します。

```sql
person.birthMonth < 2
```

## Less than or equal to

`<=`（less than or equal to）比較関数は、最初の値が 2 番目の値以下かどうかを確認するために使用されます。

**形式**

```sql
{EXPRESSION} <= {EXPRESSION} 
```

**例**

次の PQL クエリは、誕生日が 1 月または 2 月に該当する人を定義します。

```sql
person.birthMonth <= 2
```

## 加算

`+`（加算）関数は、2 つの引数式の合計を見つけるために使用されます。

**形式**

```sql
{NUMBER} + {NUMBER}
```

**例**

次の PQL クエリは、2 つの異なる製品の価格を合計します。

```sql
product1.price + product2.price
```

## 乗算

`*`（乗算）関数は、2 つの引数式の積を求めるために使用されます。

**形式**

```sql
{NUMBER} * {NUMBER}
```

**例**

次の PQL クエリは、在庫の製品と製品の価格を見つけて、製品の総額を見つけます。

```sql
product.inventory * product.price
```

## 減算

`-`（減算）関数は、2 つの引数式の違いを見つけるために使用されます。

**形式**

```sql
{NUMBER} - {NUMBER}
```

**例**

次の PQL クエリは、2 つの異なる製品の価格の違いを見つけます。

```sql
product1.price - product2.price
```

## 除算

`/`（除算）関数は、2 つの引数式の商を見つけるために使用されます。

**形式**

```sql
{NUMBER} / {NUMBER}
```

**例**

次の PQL クエリは、品目ごとの平均コストを確認するために、販売された製品の合計と獲得された合計金額の比率を求めます。

```sql
totalProduct.price / totalProduct.sold
```

## 剰余

`%`（モジュロ/剰余）関数は、2 つの引数式を除算した後の剰余を見つけるために使用されます。

**形式**

```sql
{NUMBER} % {NUMBER}
```

**例**

次の PQL クエリは、年齢が 5 で割り切れるかどうかを確認します。

```sql
person.age % 5 = 0
```

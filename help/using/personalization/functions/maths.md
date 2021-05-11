---
title: 関数ライブラリ
description: 関数ライブラリ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 90%

---

# 数学関数{#math}

![](../../assets/do-not-localize/badge.png)

演算関数は、[!DNL Profile Query Language] (PQL)の値に対して基本的な演算を行うのに使用されます。

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

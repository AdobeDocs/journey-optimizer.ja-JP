---
title: 演算関数ライブラリ
description: 演算関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 48%

---

# 演算関数 {#maths}

![](../../assets/do-not-localize/badge.png)

演算関数 は、値に対して基本的な計算を実行するために使用します。

## 加算{#add}

`+`（加算）関数は、2 つの引数式の合計を見つけるために使用されます。

**形式**

```sql
{%= double + double %}
```

**例**

次の操作は、2つの異なる製品の価格を合計します。

```sql
{%= product1.price + product2.price %}
```

## 乗算{#multiply}

`*`（乗算）関数は、2 つの引数式の積を求めるために使用されます。

**形式**

```sql
{%= double * double %}
```

**例**

次の操作では、在庫の製品と製品の価格を検索して、製品の総額を見つけます。

```sql
{%= product.inventory * product.price %}
```

## 減算{#substract}

`-`（減算）関数は、2 つの引数式の違いを見つけるために使用されます。

**形式**

```sql
{%= double - double %}
```

**例**

次の操作は、2つの異なる製品の価格の違いを見つけます。

```sql
{%= product1.price - product2.price %}
```

## 除算{#divide}

`/`（除算）関数は、2 つの引数式の商を見つけるために使用されます。

**形式**

```sql
{%= double / double %}
```

**例**

次の操作では、販売された製品の合計と獲得された合計金額の比率を求め、品目ごとの平均コストを確認します。

```sql
{%= totalProduct.price / totalProduct.sold %}
```

## 剰余{#remainder}

`%`（モジュロ/剰余）関数は、2 つの引数式を除算した後の剰余を見つけるために使用されます。

**形式**

```sql
{%= double % double %}
```

**例**

次の操作は、年齢が5で割り切れるかどうかを確認します。

```sql
{%= person.age % 5 = 0 %}
```

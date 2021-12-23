---
title: 演算関数ライブラリ
description: 演算関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 21ef8f50-8389-4675-a8e5-0438a3eee592
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: ht
source-wordcount: '180'
ht-degree: 100%

---

# 演算関数 {#maths}

演算関数は、値に対する基本的な計算を実行するために使用します。

## 加算{#add}

`+`（加算）関数は、2 つの引数式の合計を見つけるために使用されます。

**形式**

```sql
{%= double + double %}
```

**例**

次の操作は、2 つの異なる製品の価格を合計します。

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

次の操作は、在庫製品と製品価格を検索して、製品の総価値を算出します。

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

次の操作は、2 つの異なる製品の価格の違いを見つけます。

```sql
{%= product1.price - product2.price %}
```

## Divide{#divide}

`/`（除算）関数は、2 つの引数式の商を見つけるために使用されます。

**形式**

```sql
{%= double / double %}
```

**例**

次の操作は、販売された製品の合計と獲得した合計金額の比率を求めて、品目ごとの平均コストを算出します。

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

次の操作は、年齢が 5 で割り切れるかどうかを確認します。

```sql
{%= person.age % 5 = 0 %}
```

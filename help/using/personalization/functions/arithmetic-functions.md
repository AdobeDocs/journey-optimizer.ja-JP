---
title: 数学関数ライブラリ
description: 数学関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 21ef8f50-8389-4675-a8e5-0438a3eee592
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---

# 算術関数 {#maths}

算術関数は、値に基づいて基本的な計算を実行するために使用されます。

## 付ける{#add}

`+`(加算) 関数を使用して、2つの引数式の合計を求めます。

**書式**

```sql
{%= double + double %}
```

**一**

次の操作を実行すると、2つの異なる製品の価格が計算されます。

```sql
{%= product1.price + product2.price %}
```

## 合わせ{#multiply}

`*`(乗算) 関数を使用すると、2つの引数式の積が検索されます。

**書式**

```sql
{%= double * double %}
```

**一**

次の操作を行うと、製品の在庫価格と製品価格の積が検索されます。

```sql
{%= product.inventory * product.price %}
```

## 引き{#substract}

`-`(引き算) 関数を使用して、2つの引数式の違いを検索します。

**書式**

```sql
{%= double - double %}
```

**一**

次の例では、2つの異なる製品間の価格の違いを検索します。

```sql
{%= product1.price - product2.price %}
```

## 分割{#divide}

(除算) 関数を使用して、 `/` 2 つの引数式の商を求めます。

**書式**

```sql
{%= double / double %}
```

**一**

次の操作を実行すると、販売数と合計金額の間の商が検索され、品目あたりの平均原価が表示されます。

```sql
{%= totalProduct.price / totalProduct.sold %}
```

## 割り算{#remainder}

`%`(モジュロ/余り) 関数を使用して、2つの引数式を割った余りが検索されます。

**書式**

```sql
{%= double % double %}
```

**一**

次の例では、人物の年齢が5で割り切れるかどうかをチェックします。

```sql
{%= person.age % 5 = 0 %}
```

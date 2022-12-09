---
title: 集計関数ライブラリ
description: 集計関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: a029f716-ea1e-4d79-82b7-59770f05161b
source-git-commit: 284d95976ab1b58aaea2a4c41db20a3ea5a9b761
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# 集計関数 {#aggregation}

集計関数を使用して、複数の値をグループ化して1つの集約値を作成します。

## 所要{#average}

この関数は `average` 、配列内の選択されたすべての値の算術平均を返します。

**書式**

```sql
{%= average(array) %}
```

**一**

次の例では、すべての注文の平均価格を返します。

```sql
{%=average(orders.order.price)%}
```

## ティック{#count}

この関数は `count` 、指定された配列内のエレメントの数を返します。

**書式**

```sql
{%= count(array) %}
```

**一**

次の操作を実行すると、配列内の注文数が返されます。

```sql
{%= count(orders) %}
```

## 値{#max}

この関数は `max` 、配列内の選択されたすべての値のうち、最大の値を返します。

**書式**

```sql
{%= max(array) %}
```

**一**

次の操作を実行すると、すべての注文の最高価格が返されます。

```sql
{%=max(orders.order.price)%}
```

## 最小{#min}

この関数は `min` 、配列内の選択されているすべての値のうち、最小の値を返します。

**書式**

```sql
{%= min(array) %}
```

**一**

次の操作を実行すると、すべての注文の最低価格が返されます。

```sql
{%=min(orders.order.price) %}
```

## 総額{#sum}

この関数は `sum` 、配列内の選択されたすべての値の合計を返します。

**書式**

```sql
{%= sum(array) %}
```

**一**

次の例では、すべての注文の価格の合計を返します。

```sql
{%=sum(orders.order.price)%}
```

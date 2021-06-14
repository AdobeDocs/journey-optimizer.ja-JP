---
title: 集計関数ライブラリ
description: 集計関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 52%

---

# 集計関数 {#aggregation}

![](../../assets/do-not-localize/badge.png)

集計関数は、複数の値をグループ化して単一の要約値を形成するために使用します。

## Count{#count}

`count` 関数は、渡された配列内の要素数を返します。

**形式**

```sql
{%= count(array) %}
```

**例**

次の操作は、配列内の注文数を返します。

```sql
{%= count(orders) %}
```

## Sum{#sum}

`sum` 関数は、配列内の選択された値すべての合計を返します。

**形式**

```sql
{%= sum(array) %}
```

**例**

次の操作は、すべての注文の価格の合計を返します。

```sql
{%=sum(orders.order.price)%}
```

## Average{#average}

`average` 関数は、配列内の選択された値すべての算術平均を返します。

**形式**

```sql
{%= average(array) %}
```

**例**

次の操作は、すべての注文の平均価格を返します。

```sql
{%=average(orders.order.price)%}
```

## Minimum{#min}

`min` 関数は、配列内の選択された値すべての最小値を返します。

**形式**

```sql
{%= min(array) %}
```

**例**

次の操作は、すべての注文の最低価格を返します。

```sql
{%=min(orders.order.price)%}
```

## Maximum{#max}

`max` 関数は、配列内の選択された値すべての最大値を返します。

**形式**

```sql
{%= max(array) %}
```

**例**

次の操作は、すべての注文の最高価格を返します。

```sql
{%=max(orders.order.price)%}
```

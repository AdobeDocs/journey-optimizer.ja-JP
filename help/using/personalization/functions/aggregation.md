---
title: 関数ライブラリ
description: 関数ライブラリ
source-git-commit: 8c58dd667ea59a17833bbe3482b1a233ac2e28fe
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 54%

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

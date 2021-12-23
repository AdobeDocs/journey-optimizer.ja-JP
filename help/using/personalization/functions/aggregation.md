---
title: 集計関数ライブラリ
description: 集計関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: a029f716-ea1e-4d79-82b7-59770f05161b
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---

# 集計関数 {#aggregation}

集計関数は、複数の値をまとめて 1 つの値に要約するために使用します。

## Count{#count}

`count` 関数は、渡された配列内の要素数を返します。

**形式**

```sql
{%= count(array) %}
```

**例**

次の操作は、配列内の注文の数を返します。

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

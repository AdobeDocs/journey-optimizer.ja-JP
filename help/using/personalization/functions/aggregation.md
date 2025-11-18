---
title: 集計関数ライブラリ
description: 集計関数ライブラリ
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: a029f716-ea1e-4d79-82b7-59770f05161b
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---

# 集計関数 {#aggregation}

集計関数は、複数の値をまとめて 1 つの値に要約するために使用します。

## 平均{#average}

`average` 関数は、配列内の選択された値すべての算術平均を返します。

**構文**

```sql
{%= average(array) %}
```

**例**

次の操作は、すべての注文の平均価格を返します。

```sql
{%=average(orders.order.price)%}
```

## カウント{#count}

`count` 関数は、渡された配列内の要素数を返します。

**構文**

```sql
{%= count(array) %}
```

**例**

次の操作は、配列内の注文の数を返します。

```sql
{%= count(orders) %}
```

## 最大{#max}

`max` 関数は、配列内の選択された値すべての最大値を返します。

**構文**

```sql
{%= max(array) %}
```

**例**

次の操作は、すべての注文の最高価格を返します。

```sql
{%=max(orders.order.price)%}
```

## 最小{#min}

`min` 関数は、配列内の選択された値すべての最小値を返します。

**構文**

```sql
{%= min(array) %}
```

**例**

次の操作は、すべての注文の最低価格を返します。

```sql
{%=min(orders.order.price) %}
```

## 合計{#sum}

`sum` 関数は、配列内の選択された値すべての合計を返します。

**構文**

```sql
{%= sum(array) %}
```

**例**

次の操作は、すべての注文の価格の合計を返します。

```sql
{%=sum(orders.order.price)%}
```

---
title: 関数ライブラリ
description: 関数ライブラリ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 85%

---

# 集計関数{#aggregation}

![](../../assets/do-not-localize/badge.png)

集約関数は、[!DNL Profile Query Language] (PQL)配列内の複数の値をグループ化して単一の要約値を形成するために使用されます。

## Count

`count` 関数は、渡された配列内の要素数を返します。

**形式**

```sql
count({ARRAY})
```

**例**

次の PQL クエリは、配列内の注文の数を返します。

```sql
count(orders)
```

## Sum

`sum` 関数は、配列内の選択された値すべての合計を返します。

**形式**

```sql
sum({ARRAY})
```

**例**

次の PQL クエリは、すべての注文の価格の合計を返します。

```sql
sum(orders.order.price)
```

## Average

`average` 関数は、配列内の選択された値すべての算術平均を返します。

**形式**

```sql
average({ARRAY})
```

**例**

次の PQL クエリは、すべての注文の平均価格を返します。

```sql
average(orders.order.price)
```

## Minimum

`min` 関数は、配列内の選択された値すべての最小値を返します。

**形式**

```sql
min({ARRAY})
```

**例**

次の PQL クエリは、すべての注文の最低価格を返します。

```sql
min(orders.order.price)
```

## Maximum

`max` 関数は、配列内の選択された値すべての最大値を返します。

**形式**

```sql
max({ARRAY})
```

**例**

次の PQL クエリは、すべての注文の最高価格を返します。

```sql
max(orders.order.price)
```

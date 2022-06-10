---
title: 数学関数ライブラリ
description: 数学関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
source-git-commit: 284d95976ab1b58aaea2a4c41db20a3ea5a9b761
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 8%

---

# 数学関数 {#math}

式エディターで数学関数を使用する方法を説明します。

## 絶対パス {#absolute}

この `absolute` 関数は、数値の絶対値を変換するために使用されます。

**形式**

```sql
{%= absolute(int) %}: int
```

## ランダム {#random}

この `random` 関数は、0 ～ 1 の間のランダムな値を返すために使用されます。

**形式**

```sql
{%= random() %}: double
```

## 切り捨て {#round-down}

この `roundDown` 関数は、数値を切り捨てるために使用されます。

**形式**

```sql
{%= roundDown(double) %}: double
```

## 切り上げ {#round-up}

この `Count only null` 関数は、数値を切り上げて使用されます。

**形式**

```sql
{%= roundUp(double) %}: double
```

## 割合に {#to-percentage}

この `toPercentage` 関数は、数値をパーセンテージに変換するために使用されます。

**形式**

```sql
{%= toPercentage(double) %}: string
```

## 精度に {#to-precision}

この `toPrecision` 関数は、数値を必要な精度に変換するために使用されます。

**形式**

```sql
{%= toPrecision(double,int) %}: string
```

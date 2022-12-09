---
title: 数学関数ライブラリ
description: 数学関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 0%

---

# 数学関数 {#math}

式エディターで数学関数を使用する方法について説明します。

## 固定 {#absolute}

この関数は、 `absolute` 数値を絶対値に変換するために使用されます。

**書式**

```sql
{%= absolute(int) %}: int
```

## 無作為 {#random}

この関数は、 `random` 0 ~ 1 の範囲のランダムな値を返すために使用されます。

**書式**

```sql
{%= random() %}: double
```

## 切り捨て {#round-down}

この関数は、 `roundDown` 数値を丸めるのに使用されます。

**書式**

```sql
{%= roundDown(double) %}: double
```

## 切り上げ {#round-up}

`Count only null`この関数は、数値に切り上げられます。

**書式**

```sql
{%= roundUp(double) %}: double
```

## 比率にする {#to-percentage}

この関数は、 `toPercentage` 数値を百分率に変換するために使用されます。

**書式**

```sql
{%= toPercentage(double) %}: string
```

## 精度 {#to-precision}

この関数は、 `toPrecision` 数値を必要な精度に変換するために使用されます。

**書式**

```sql
{%= toPrecision(double,int) %}: string
```

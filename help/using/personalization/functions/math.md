---
title: 数学関数ライブラリ
description: 数学関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: b9149ad6-2be7-4bdf-82eb-7ab52780cb4e
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: ht
source-wordcount: '243'
ht-degree: 100%

---

# 数学関数 {#math}

パーソナライゼーションエディターで数学関数を使用する方法を説明します。

## 絶対パス {#absolute}

`absolute` 関数は、数値をその絶対値を変換するために使用されます。

**構文**

```sql
{%= absolute(int) %}: int
```

## formatNumber {#format-number}

この `formatNumber` 関数は、任意の数値を言語依存の表現に書式設定するために使用されます。

ロケールを表す数値および文字列を受け入れて、目的のロケールで書式設定された数値の文字列を返します。

**構文**

```sql
{%= formatNumber(number/double,string) %}: string
```

[Oracle ドキュメント](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)と[サポートされているロケール](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html)にまとめられている書式設定と有効なロケールを使用できます{_blank}

**例**

このクエリは、123456.789 に対応するアラビア語で書式設定された文字列を入力番号として返します。

```sql
{%= formatNumber(123456.789, "ar_EG") %}
```

## ランダム {#random}

`random` 関数は、0 ～ 1 の間のランダムな値を返すために使用されます。

**構文**

```sql
{%= random() %}: double
```

## 切り捨て {#round-down}

`roundDown` 関数は、数値を切り捨てるために使用されます。

**構文**

```sql
{%= roundDown(double) %}: double
```

## 切り上げ {#round-up}

`Count only null` 関数は、数値を切り上げるために使用されます。

**構文**

```sql
{%= roundUp(double) %}: double
```

## 16 進文字列に {#to-hex-string}

この `toHexString` 関数は、任意の数を 16 進文字列に変換します。

**構文**

```sql
{%= toHexString(number) %}: string
```

**例**

このクエリは、158 の 16 進数値、つまり 9e を返します。

```sql
{%= toHexString(158) %}
```

## ToInt {#to-int}

`toInt` 関数は、これらの型（number、double、int、long、float、short、byte、boolean、string）のいずれかを整数に変換するために使用されます。

**構文**

```sql
{%= toInt(<valueToConvert>) %}: integer
```

**例**

このクエリは、42.6 の 整数値、つまり 42 を返します。

```sql
{%= toInt(42.6) %}: integer
```

## パーセンテージに {#to-percentage}

`toPercentage` 関数は数値をパーセンテージに変換するために使用されます。

**構文**

```sql
{%= toPercentage(double) %}: string
```

## 精度に {#to-precision}

`toPrecision` 関数は、数値を必要な精度に変換するために使用されます。

**構文**

```sql
{%= toPrecision(double,int) %}: string
```

## toString {#to-string}

**toString** 関数は、任意の数値を文字列表現に変換します。

**構文**

```sql
{%= toString(string) %}: string
```

**例**

このクエリは「12」を返します。

```sql
{%= toString(12) %} 
```

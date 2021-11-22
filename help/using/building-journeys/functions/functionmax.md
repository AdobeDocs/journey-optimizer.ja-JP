---
product: adobe campaign
title: max
description: 関数 max の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 5c792d33-32b9-4b1b-ab99-3ebfac391678
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 8%

---

# 最大{#max}

一覧または 2 つの式に指定された、一連の式の中の最大値を返します。 Null 値は無視されます。

## カテゴリ

集計

## 関数の構文

`max(<parameter>)`

## パラメーター

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* duration
* 整数
* decimal
* dateTime
* dateTimeOnly

## 署名と戻り値の型

`max(<listDuration>)`

期間を返します。

`max(<listInteger>)`

期間を返します。

`max(<listDateTimeOnly>)`

タイムゾーンを考慮せずに、日時を返します。

`max(<listDateTime>)`

日時を返します。

`max(<listDateOnly>)`

日付を返します。

`max(<listDecimal>)`

小数を返します。

`max(<decimal>,<decimal>)`

小数を返します。

`max(<duration>,<duration>)`

期間を返します。

`max(<dateTime>,<dateTime>)`

日時を返します。

`max(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを考慮せずに、日時を返します。

`max(<integer>,<integer>)`

整数を返します。

## 例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

10 を返します。

`max([10,null,8])`

10 を返します。

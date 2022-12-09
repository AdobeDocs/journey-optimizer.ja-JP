---
product: journey optimizer
title: 分
description: Min 関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1c425d1d-08b4-446b-83ce-db376b2bf39f
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---

# 分 {#min}

指定された式のセット間での最小値を返します。この関数は、list または two という式を使用することもできます。 Null 値は無視されます。

## 項目

総計

## 関数のシンタックス

`min(<parameters>)`

## パラメーター

* listDuration
* listInteger
* リスト10進数
* listDateTime
* listDateTimeOnly
* listDateOnly
* 持続
* 整数
* 形式
* dateTime
* dateTimeOnly

## シグネチャと戻り値の型

`min(<listDuration>)`

期間を返します。

`min(<listInteger>)`

期間を返します。

`min(<listDateTimeOnly>)`

タイムゾーンを考慮せずに日付時刻を返します。

`min(<listDateTime>)`

Datetime を返します。

`min(<listDateOnly>)`

日付を返します。

`min(<listDecimal>)`

10進数を返します。

`min(<decimal>,<decimal>)`

10進数を返します。

`min(<duration>,<duration>)`

期間を返します。

`min(<dateTime>,<dateTime>)`

Datetime を返します。

`min(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを考慮せずに日付時刻を返します。

`min(<integer>,<integer>)`

整数値を返します。

## 例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

3を返します。

`min([10,null,8])`

8を返します。

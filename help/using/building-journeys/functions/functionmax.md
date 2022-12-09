---
product: journey optimizer
title: 最大
description: 関数の最大値について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 5c792d33-32b9-4b1b-ab99-3ebfac391678
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---

# 最大{#max}

指定された式のセット間での最大値を返します。この関数は、list または two という式を使用しています。 Null 値は無視されます。

## 項目

総計

## 関数のシンタックス

`max(<parameter>)`

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

`max(<listDuration>)`

期間を返します。

`max(<listInteger>)`

期間を返します。

`max(<listDateTimeOnly>)`

タイムゾーンを考慮せずに日付時刻を返します。

`max(<listDateTime>)`

Datetime を返します。

`max(<listDateOnly>)`

日付を返します。

`max(<listDecimal>)`

10進数を返します。

`max(<decimal>,<decimal>)`

10進数を返します。

`max(<duration>,<duration>)`

期間を返します。

`max(<dateTime>,<dateTime>)`

Datetime を返します。

`max(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを考慮せずに日付時刻を返します。

`max(<integer>,<integer>)`

整数値を返します。

## 例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

10を返します。

`max([10,null,8])`

10を返します。

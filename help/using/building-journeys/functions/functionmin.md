---
product: journey optimizer
title: min
description: min 関数について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: min, 関数, 式, ジャーニー
exl-id: 1c425d1d-08b4-446b-83ce-db376b2bf39f
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 100%

---

# min {#min}

リストまたは 2 つの式のいずれかで指定された一連の式の中の最小値を返します。null 値は無視されます。

## カテゴリ

集計

## 関数の構文

`min(<parameters>)`

## パラメーター

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* 期間
* 整数
* 小数
* 日時
* 日時のみ

## シグネチャと戻り値のタイプ

`min(<listDuration>)`

期間を返します。

`min(<listInteger>)`

期間を返します。

`min(<listDateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`min(<listDateTime>)`

日時を返します。

`min(<listDateOnly>)`

日付を返します。

`min(<listDecimal>)`

小数を返します。

`min(<decimal>,<decimal>)`

小数を返します。

`min(<duration>,<duration>)`

期間を返します。

`min(<dateTime>,<dateTime>)`

日時を返します。

`min(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`min(<integer>,<integer>)`

整数を返します。

## 例

`min(@event{BarBeacon.inventory},5)`

`min([10,3,8])`

3 を返します。

`min([10,null,8])`

「8」を返します。

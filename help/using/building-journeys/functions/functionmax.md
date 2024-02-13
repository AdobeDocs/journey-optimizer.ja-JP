---
product: journey optimizer
title: max
description: max 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: max, 関数, 式, ジャーニー
exl-id: 5c792d33-32b9-4b1b-ab99-3ebfac391678
source-git-commit: cb1fed2460ddbf3b226fe191b9695008970937c1
workflow-type: ht
source-wordcount: '98'
ht-degree: 100%

---

# max{#max}

リストまたは 2 つの式として指定された一連の式の中から最大値を返します。null 値は無視されます。

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
* 期間
* 整数
* 小数
* 日時
* 日時のみ

## シグネチャと戻り値のタイプ

`max(<listDuration>)`

期間を返します。

`max(<listInteger>)`

期間を返します。

`max(<listDateTimeOnly>)`

タイムゾーンを無視して日時を返します。

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

タイムゾーンを無視して日時を返します。

`max(<integer>,<integer>)`

整数を返します。

## 例

`max(@event{BarBeacon.inventory},5)`

`max([10,3,8])`

10 を返します。

`max([10,null,8])`

10 を返します。

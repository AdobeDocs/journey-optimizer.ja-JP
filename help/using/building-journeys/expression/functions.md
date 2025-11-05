---
solution: Journey Optimizer
product: journey optimizer
title: 関数
description: 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 関数, 式, エディター, ジャーニー
exl-id: 5b978eef-7d3e-41fe-bb08-0cf37c3b125d
version: Journey Orchestration
source-git-commit: 42abfcc9711d87b2dc00df47e964dad07443f0ed
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 100%

---

# 関数 {#functions}

関数は、異なるシグネチャ（順序付きパラメーターの異なるセット）を持つことができます。関数シグネチャは、0～N 個の式を順序付きパラメーターとして持つことができます。

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

関数ごとに、固有の戻り値タイプがあります。

サポートされている関数の一覧を以下に示します。

## 主な関数

| カテゴリ | 関数 |
|-------------|-----------------------|
| Adobe Experience Platform | [inAudience](../functions/functioninaudience.md) |
| 集計 | [avg](../functions/aggregation-functions.md#avg) |
| 集計 | [count](../functions/aggregation-functions.md#count) |
| 集計 | [countOnlyNull](../functions/aggregation-functions.md#countOnlyNull) |
| 集計 | [countWithNull](../functions/aggregation-functions.md#countWithNull) |
| 集計 | [distinctCount](../functions/aggregation-functions.md#distinctCount) |
| 集計 | [distinctCountWithNull](../functions/aggregation-functions.md#distinctCountWithNull) |
| 集計 | [max](../functions/aggregation-functions.md#max) |
| 集計 | [min](../functions/aggregation-functions.md#min) |
| 集計 | [sum](../functions/aggregation-functions.md#sum) |
| 変換 | [toBool](../functions/conversion-functions.md#toBool) |
| 変換 | [toDateOnly](../functions/conversion-functions.md#toDateOnly) |
| 変換 | [toDateTime](../functions/conversion-functions.md#toDateTime) |
| 変換 | [toDateTimeOnly](../functions/conversion-functions.md#toDateTimeOnly) |
| 変換 | [toDecimal](../functions/conversion-functions.md#toDecimal) |
| 変換 | [toDuration](../functions/conversion-functions.md#toDuration) |
| 変換 | [toInteger](../functions/conversion-functions.md#toInteger) |
| 変換 | [toString](../functions/conversion-functions.md#toString) |
| 日付 | [currentTimeInMillis](../functions/date-functions.md#currentTimeInMillis) |
| 日付 | [inLastDays](../functions/date-functions.md#inLastDays) |
| 日付 | [inLastHours](../functions/date-functions.md#inLastHours) |
| 日付 | [inLastMonths](../functions/date-functions.md#inLastMonths) |
| 日付 | [inLastYears](../functions/date-functions.md#inLastYears) |
| 日付 | [inNextDays](../functions/date-functions.md#inNextDays) |
| 日付 | [inNextHours](../functions/date-functions.md#inNextHours) |
| 日付 | [inNextMonths](../functions/date-functions.md#inNextMonths) |
| 日付 | [inNextYears](../functions/date-functions.md#inNextYears) |
| 日付 | [now](../functions/date-functions.md#now) |
| 日付 | [nowWithDelta](../functions/date-functions.md#nowWithDelta) |
| 日付 | [setHours](../functions/date-functions.md#setHours) |
| 日付 | [setDays](../functions/date-functions.md#setDays) |
| 日付 | [updateTimeZone](../functions/date-functions.md#updateTimeZone) |
| リスト | [distinct](../functions/functiondistinct.md) |
| リスト | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| リスト | [filter](../functions/functionfilter.md) |
| リスト | [getListItem](../functions/functiongetlistitem.md) |
| リスト | [in](../functions/functionin.md) |
| リスト | [intersect](../functions/functionintersect.md) |
| リスト | [limit](../functions/functionlimit.md) |
| リスト | [listSize](../functions/functionlistsize.md) |
| リスト | [serializeList](../functions/functionserializelist.md) |
| リスト | [sort](../functions/functionsort.md) |
| 数値計算 | [random](../functions/functionrandom.md) |
| 数値計算 | [round](../functions/functionround.md) |
| 文字列 | [concat](../functions/functionconcat.md) |
| 文字列 | [contain](../functions/functioncontain.md) |
| 文字列 | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 文字列 | [endWith](../functions/functionendwith.md) |
| 文字列 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 文字列 | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| 文字列 | [indexOf](../functions/functionindexof.md) |
| 文字列 | [isEmpty](../functions/functionisempty.md) |
| 文字列 | [isNotEmpty](../functions/functionisnotempty.md) |
| 文字列 | [lastIndexOf](../functions/functionlastindexof.md) |
| 文字列 | [length](../functions/functionlength.md) |
| 文字列 | [lower](../functions/functionlower.md) |
| 文字列 | [matchRegExp](../functions/functionmatchregexp.md) |
| 文字列 | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| 文字列 | [replace](../functions/functionreplace.md) |
| 文字列 | [replaceAll](../functions/functionreplaceall.md) |
| 文字列 | [split](../functions/functionsplit.md) |
| 文字列 | [startWith](../functions/functionstartwith.md) |
| 文字列 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 文字列 | [substr](../functions/functionsubstr.md) |
| 文字列 | [trim](../functions/functiontrim.md) |
| 文字列 | [upper](../functions/functionupper.md) |
| 文字列 | [uuid](../functions/functionuuid.md) |

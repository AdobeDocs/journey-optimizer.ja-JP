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
source-git-commit: d58319d687d113ce680c415524fdea0400cb38f0
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
| リスト | [distinct](../functions/list-functions.md#distinct) |
| リスト | [distinctWithNull](../functions/list-functions.md#distinctWithNull) |
| リスト | [filter](../functions/list-functions.md#filter) |
| リスト | [getListItem](../functions/list-functions.md#getListItem) |
| リスト | [in](../functions/list-functions.md#in) |
| リスト | [intersect](../functions/list-functions.md#intersect) |
| リスト | [limit](../functions/list-functions.md#limit) |
| リスト | [listSize](../functions/list-functions.md#listSize) |
| リスト | [serializeList](../functions/list-functions.md#serializeList) |
| リスト | [sort](../functions/list-functions.md#sort) |
| 数値計算 | [random](../functions/functionrandom.md) |
| 数値計算 | [round](../functions/functionround.md) |
| 文字列 | [concat](../functions/string-functions.md#concat) |
| 文字列 | [contain](../functions/string-functions.md#contain) |
| 文字列 | [containIgnoreCase](../functions/string-functions.md#containIgnoreCase) |
| 文字列 | [endWith](../functions/string-functions.md#endWith) |
| 文字列 | [endWithIgnoreCase](../functions/string-functions.md#endWithIgnoreCase) |
| 文字列 | [equalIgnoreCase](../functions/string-functions.md#equalIgnoreCase) |
| 文字列 | [indexOf](../functions/string-functions.md#indexOf) |
| 文字列 | [isEmpty](../functions/string-functions.md#isEmpty) |
| 文字列 | [isNotEmpty](../functions/string-functions.md#isNotEmpty) |
| 文字列 | [lastIndexOf](../functions/string-functions.md#lastIndexOf) |
| 文字列 | [length](../functions/string-functions.md#length) |
| 文字列 | [lower](../functions/string-functions.md#lower) |
| 文字列 | [matchRegExp](../functions/string-functions.md#matchRegExp) |
| 文字列 | [notEqualIgnoreCase](../functions/string-functions.md#notEqualIgnoreCase) |
| 文字列 | [replace](../functions/string-functions.md#replace) |
| 文字列 | [replaceAll](../functions/string-functions.md#replaceAll) |
| 文字列 | [split](../functions/string-functions.md#split) |
| 文字列 | [startWith](../functions/string-functions.md#startWith) |
| 文字列 | [startWithIgnoreCase](../functions/string-functions.md#startWithIgnoreCase) |
| 文字列 | [substr](../functions/string-functions.md#substr) |
| 文字列 | [trim](../functions/string-functions.md#trim) |
| 文字列 | [upper](../functions/string-functions.md#upper) |
| 文字列 | [uuid](../functions/string-functions.md#uuid) |

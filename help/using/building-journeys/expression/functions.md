---
solution: Journey Optimizer
product: journey optimizer
title: 業務
description: 関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 5b978eef-7d3e-41fe-bb08-0cf37c3b125d
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# 業務 {#functions}

関数には、異なるシグニチャを設定することができます。 関数のシグニチャには、0 ~ N 個のパラメーターを指定することができます。

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

各関数には、戻り値の型が指定されています。

サポートされている関数の一覧を次に示します。

## メイン関数

| 項目 | 関数 |
|-------------|-----------------------|
| Adobe エクスペリエンスプラットフォーム | [inSegment](../functions/functioninsegment.md) |
| 総計 | [平均](../functions/functionavg.md) |
| 総計 | [ティック](../functions/functioncount.md) |
| 総計 | [countOnlyNull](../functions/functioncountonlynull.md) |
| 総計 | [countWithNull](../functions/functioncountwithnull.md) |
| 総計 | [distinctCount](../functions/functiondistinctcount.md) |
| 総計 | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| 総計 | [最大](../functions/functionmax.md) |
| 総計 | [分](../functions/functionmin.md) |
| 総計 | [総額](../functions/functionsum.md) |
| 処理 | [toBool](../functions/functiontobool.md) |
| 処理 | [toDateOnly](../functions/functiontodateonly.md) |
| 処理 | [toDateTime](../functions/functiontodatetime.md) |
| 処理 | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| 処理 | [toDecimal](../functions/functiontodecimal.md) |
| 処理 | [toDuration](../functions/functiontoduration.md) |
| 処理 | [toInteger](../functions/functiontointeger.md) |
| 処理 | [toString](../functions/functiontostring.md) |
| 古い | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| 古い | [郵便日付](../functions/functioninlastdays.md) |
| 古い | [inLastHours](../functions/functioninlasthours.md) |
| 古い | [「In Lastmonths」](../functions/functioninlastmonths.md) |
| 古い | [inLastYears](../functions/functioninlastyears.md) |
| 古い | [In Nextdays](../functions/functioninnextdays.md) |
| 古い | [inNextHours](../functions/functioninnexthours.md) |
| 古い | [「、Nextmonths」](../functions/functioninnextmonths.md) |
| 古い | [「Nextyears」](../functions/functioninnextyears.md) |
| 古い | [今](../functions/functionnow.md) |
| 古い | [今すぐデルタ](../functions/functionnowwithdelta.md) |
| 古い | [setHours](../functions/functionsethours.md) |
| 古い | [setDays](../functions/functionsetdays.md) |
| 古い | [updateTimeZone](../functions/functionupdatetimezone.md) |
| 一連 | [異なっ](../functions/functiondistinct.md) |
| 一連 | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| 一連 | [フィルタ](../functions/functionfilter.md) |
| 一連 | [getListItem](../functions/functiongetlistitem.md) |
| 一連 | [単位](../functions/functionin.md) |
| 一連 | [交わる](../functions/functionintersect.md) |
| 一連 | [listSize](../functions/functionlimit.md) |
| 一連 | [listSize](../functions/functionlistsize.md) |
| 一連 | [serializeList](../functions/functionserializelist.md) |
| 一連 | [降順](../functions/functionsort.md) |
| 演算 | [無作為](../functions/functionrandom.md) |
| 演算 | [数値](../functions/functionround.md) |
| 値 | [連結](../functions/functionconcat.md) |
| 値 | [ある](../functions/functioncontain.md) |
| 値 | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 値 | [endend](../functions/functionendwith.md) |
| 値 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 値 | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| 値 | [indexOf](../functions/functionindexof.md) |
| 値 | [isEmpty](../functions/functionisempty.md) |
| 値 | [isNotEmpty](../functions/functionisnotempty.md) |
| 値 | [lastIndexOf](../functions/functionlastindexof.md) |
| 値 | [長さ](../functions/functionlength.md) |
| 値 | [古い](../functions/functionlower.md) |
| 値 | [matchRegExp](../functions/functionmatchregexp.md) |
| 値 | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| 値 | [置き](../functions/functionreplace.md) |
| 値 | [replaceAll](../functions/functionreplaceall.md) |
| 値 | [startWith](../functions/functionstartwith.md) |
| 値 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 値 | [substr](../functions/functionsubstr.md) |
| 値 | [裁断](../functions/functiontrim.md) |
| 値 | [大](../functions/functionupper.md) |
| 値 | [uuid](../functions/functionuuid.md) |

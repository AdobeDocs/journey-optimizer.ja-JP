---
product: adobe campaign
title: updateTimeZone
description: updateTimeZone 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1bf4662e-55d0-4631-af93-1430ec7ed7e2
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: ht
source-wordcount: '53'
ht-degree: 100%

---

# updateTimeZone {#updateTimeZone}

新しいタイムゾーンで、同じ瞬間の新しい日時を返します。

## カテゴリ

日付

## 関数の構文

`updateTimeZone(<parameters>)`

## パラメーター

* タイムゾーン ID：文字列
* 日時

## シグネチャと戻り値のタイプ

`updateTimeZone(<dateTime>,<timeZone id>)`

日時を返します。

## 例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17:15:30.123+02:00 を返します。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

timestamp フィールドの値が `2021-11-16T16:55:12.939318+01:00` の場合、この関数は `2021-11-17T02:55:12.942115+11:00` を返します。

---
product: journey optimizer
title: updateTimeZone
description: 関数 updateTimeZone について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1bf4662e-55d0-4631-af93-1430ec7ed7e2
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 0%

---

# updateTimeZone {#updateTimeZone}

新しい日時を返します。この場合は、同じインスタントに新しいタイムゾーンが追加されます。

## 項目

古い

## 関数のシンタックス

`updateTimeZone(<parameters>)`

## パラメーター

* タイムゾーン id: string
* dateTime

## シグネチャと戻り値の型

`updateTimeZone(<dateTime>,<timeZone id>)`

Datetime を返します。

## 例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28 T17 :15: 30.123 + 02:00 を返します。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

「タイムスタンプ」フィールドの値が `2021-11-16T16:55:12.939318+01:00` 返されると、関数は戻り `2021-11-17T02:55:12.942115+11:00` ます。

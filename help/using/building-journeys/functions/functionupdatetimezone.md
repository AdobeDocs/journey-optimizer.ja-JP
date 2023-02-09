---
product: journey optimizer
title: updateTimeZone
description: updateTimeZone 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: updateTimeZone, 関数, 式, ジャーニー
exl-id: 1bf4662e-55d0-4631-af93-1430ec7ed7e2
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '57'
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

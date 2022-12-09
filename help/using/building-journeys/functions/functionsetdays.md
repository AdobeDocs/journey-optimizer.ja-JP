---
product: journey optimizer
title: setDays
description: 関数 setDays について説明しています。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c2757e41-8206-44f7-9dbb-1fa79c0ba6e6
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 0%

---

# setDays {#setDays}

日付、時刻、日付のみを設定します。 例えば、その月の特定の日まで待つ場合は、その日に強制的に戻ることができます。

## 項目

古い

## 関数のシンタックス

`setDays(<parameter>)`

## パラメーター

| 指定 | 入力 |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮せずの日時 | dateTimeOnly |
| 稼働 | 整数 |

## シグネチャと戻り値の型

`setDays(<dateTime>,<days>)`

Datetime を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを考慮せずに日付時刻を返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01 :11: 00z を返します。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`

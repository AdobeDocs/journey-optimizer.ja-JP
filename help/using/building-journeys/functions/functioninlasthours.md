---
product: journey optimizer
title: inLastHours
description: 関数の inLastHours について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c648d711-c81b-403b-9adb-792c7e79e4e2
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 0%

---

# inLastHours {#inLastHours}

指定された日付時刻が現在から現在までの差 (デルタ時間) である場合は true を返します。

## 項目

古い

## 関数のシンタックス

`inLastHours(<dateTime>,<delta>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 日時 | dateTime |
| 増分 | 整数 |

## シグネチャと戻り値の型

`inLastHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

True を返します。

`inLastHours(@{MyEvent.timestamp}, 4)`

True を返します。

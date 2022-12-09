---
product: journey optimizer
title: inLastYears
description: 関数の inLastYears について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: cdf653d2-967e-4a1b-92e5-37dd22f379f9
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 0%

---

# inLastYears {#inLastYears}

指定された日付または日付が現在から現在までの差がある場合は true を返します。

## 項目

古い

## 関数のシンタックス

`inLastYears(<dateTime>,<delta>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 日時 | dateTime |
| 増分 | 整数 |

## シグネチャと戻り値の型

`inLastYears(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

True を返します。

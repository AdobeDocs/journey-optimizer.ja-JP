---
product: journey optimizer
title: 「、Nextmonths」
description: Nextmonths の機能について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e2e520ec-ae9e-4ed6-b50d-606fc6861d56
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 0%

---

# 「、Nextmonths」 {#inNextMonths}

指定された date または dateTime が現在から現在以降の delta 月の間にある場合は、true を返します。

## 項目

古い

## 関数のシンタックス

`inNextMonths(<dateTime>,<delta>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 日時 | dateTime |
| 増分 | 整数 |

## シグネチャと戻り値の型

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

True を返します。

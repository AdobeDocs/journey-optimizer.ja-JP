---
product: journey optimizer
title: 郵便日付
description: 最後の日付にある関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1b150568-17c2-454d-847e-17bac3d0b35d
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 0%

---

# 郵便日付 {#inLastDays}

指定された日付または日付が現在から現在までの経過日数が経過した場合は true を返します。

## 項目

古い

## 関数のシンタックス

`inLastDays(<dateTime>,<delta>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 日時 | dateTime |
| 増分 | 整数 |

## シグネチャと戻り値の型

`inLastDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

True を返します。

---
product: journey optimizer
title: 「In Lastmonths」
description: 最終月の関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4933ef43-66b8-462d-867c-03edd4c34947
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 0%

---

# 「In Lastmonths」 {#inLastMonths}

日付または日付が指定されている場合は、true を返します。

## 項目

古い

## 関数のシンタックス

`inLastMonths(<dateTime>,<delta>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 日時 | dateTime |
| 増分 | 整数 |

## シグネチャと戻り値の型

`inLastMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

True を返します。

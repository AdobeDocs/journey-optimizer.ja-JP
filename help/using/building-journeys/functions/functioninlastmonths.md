---
product: journey optimizer
title: inLastMonths
description: inLastMonths 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4933ef43-66b8-462d-867c-03edd4c34947
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# inLastMonths {#inLastMonths}

指定された日付または日時が現在の日時とその delta か月前の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inLastMonths(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inLastMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

true を返します。

---
product: journey optimizer
title: inLastYears
description: inLastYears 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: cdf653d2-967e-4a1b-92e5-37dd22f379f9
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: ht
source-wordcount: '44'
ht-degree: 100%

---

# inLastYears {#inLastYears}

指定された日付または日時が現在の日時とその delta 年前の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inLastYears(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inLastYears(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

true を返します。

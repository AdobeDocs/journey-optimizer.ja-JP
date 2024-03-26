---
product: journey optimizer
title: inLastYears
description: inLastYears 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inLastYears, 関数, 式, ジャーニー
exl-id: cdf653d2-967e-4a1b-92e5-37dd22f379f9
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: ht
source-wordcount: '48'
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

`inLastYears(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

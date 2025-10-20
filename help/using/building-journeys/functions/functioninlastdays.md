---
product: journey optimizer
title: inLastDays
description: inLastDays 関数について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: inLastDays, 関数, 式, ジャーニー
exl-id: 1b150568-17c2-454d-847e-17bac3d0b35d
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 100%

---

# inLastDays {#inLastDays}

指定された dateTime が現在の日時とその delta 日前の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inLastDays(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inLastDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

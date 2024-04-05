---
product: journey optimizer
title: inLastMonths
description: inLastMonths 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inLastMonths, 関数, 式, ジャーニー
exl-id: 4933ef43-66b8-462d-867c-03edd4c34947
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '48'
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

`inLastMonths(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

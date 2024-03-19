---
product: journey optimizer
title: inLastHours
description: inLastHours 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inLastHours, 関数l 式, ジャーニー
exl-id: c648d711-c81b-403b-9adb-792c7e79e4e2
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: ht
source-wordcount: '49'
ht-degree: 100%

---

# inLastHours {#inLastHours}

指定された日時が現在の日時とその delta 時間前の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inLastHours(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inLastHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

`inLastHours(@event{MyEvent.timestamp}, 4)`

true を返します。

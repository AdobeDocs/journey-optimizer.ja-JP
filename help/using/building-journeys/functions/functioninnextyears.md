---
product: adobe campaign
title: inNextYears
description: inNextYears 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e4597772-d53c-4e15-8237-b2460ce31170
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: ht
source-wordcount: '44'
ht-degree: 100%

---

# inNextYears {#inNextYears}

指定された日付または日時が現在の日時とその delta 年後の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextYears(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inNextYears(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

true を返します。

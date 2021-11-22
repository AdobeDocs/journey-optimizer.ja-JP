---
product: adobe campaign
title: inNextDays
description: inNextDays 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0cb3e0db-dc5b-4d4e-a057-af030d9bdb21
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextDays {#inNextDays}

指定された日付または dateTime が現在と今+デルタ日の間の場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextDays(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| デルタ | 整数 |

## 署名と戻り値の型

`inNextDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

true を返します。

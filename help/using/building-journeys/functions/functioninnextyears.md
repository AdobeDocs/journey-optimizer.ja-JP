---
product: journey optimizer
title: 「Nextyears」
description: Nextyears の機能について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e4597772-d53c-4e15-8237-b2460ce31170
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 0%

---

# 「Nextyears」 {#inNextYears}

指定された日付または日付が現在から現在までの間にある場合は true を返します。

## 項目

古い

## 関数のシンタックス

`inNextYears(<dateTime>,<delta>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 日時 | dateTime |
| 増分 | 整数 |

## シグネチャと戻り値の型

`inNextYears(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

True を返します。

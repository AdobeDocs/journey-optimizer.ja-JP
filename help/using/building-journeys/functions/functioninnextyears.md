---
product: journey optimizer
title: inNextYears
description: inNextYears 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inNextYears，関数，式，ジャーニー
exl-id: e4597772-d53c-4e15-8237-b2460ce31170
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 91%

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

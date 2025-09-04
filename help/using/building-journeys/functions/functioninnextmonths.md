---
product: journey optimizer
title: inNextMonths
description: inNextMonths 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inNextMonths, 関数, 式, ジャーニー
exl-id: e2e520ec-ae9e-4ed6-b50d-606fc6861d56
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# inNextMonths {#inNextMonths}

指定された日付または日時が現在の日時とその delta か月後の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextMonths(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextMonths(toDateTime('2023-01-12T01:11:00Z'), 4)`

true を返します。

---
product: journey optimizer
title: inNextDays
description: inNextDays 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inNextDays, 関数, 式, ジャーニー
exl-id: 0cb3e0db-dc5b-4d4e-a057-af030d9bdb21
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# inNextDays {#inNextDays}

指定された日付または日時が現在の日時とその delta 日後の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextDays(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inNextDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

---
product: journey optimizer
title: inNextMonths
description: inNextMonths 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: inNextMonths, 関数, 式, ジャーニー
exl-id: e2e520ec-ae9e-4ed6-b50d-606fc6861d56
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: ht
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

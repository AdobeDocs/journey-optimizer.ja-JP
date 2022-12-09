---
product: journey optimizer
title: 今
description: 今すぐ関数について学習します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 0%

---

# 今 {#now}

日付時刻形式で現在の日付を返します。 データ型について詳しくは、このページ ](../expression/data-types.md) を [ 参照してください。

## 項目

古い

## 関数のシンタックス

`now(<parameter>)`

## パラメーター

| 指定 | つい |
|--- |--- |
| 値 |  |

## シグネチャと戻り値の型

`now()`

`now("<timeZone id>")`

DateTime を返します。

## 例

`now()`

2019-06-03T06: 30Z を返します。

`toString(now())`

「2019-06-03T06: 30Z」を返します。

`now("Europe/Paris")`

2019-06-03T08:30 + 02:00 を返します。

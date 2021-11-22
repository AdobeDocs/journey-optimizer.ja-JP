---
product: adobe campaign
title: now
description: 関数の詳細を今すぐ表示
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 18%

---

# now {#now}

現在の日付を日時形式で返します。 データタイプについて詳しくは、 [このページ](../expression/data-types.md).

## カテゴリ

日付

## 関数の構文

`now(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 |  |

## 署名と戻り値の型

`now()`

`now("<timeZone id>")`

dateTime を返します。

## 例

`now()`

2019-06-03T06:30Z を返します。

`toString(now())`

「2019-06-03T06:30Z」を返します

`now("Europe/Paris")`

2019-06-03T08:30+02:00 を返します。

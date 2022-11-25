---
product: journey optimizer
title: now
description: now 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: ht
source-wordcount: '49'
ht-degree: 100%

---

# now {#now}

現在の日付を日時形式で返します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

日付

## 関数の構文

`now(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 |  |

## シグネチャと戻り値のタイプ

`now()`

`now("<timeZone id>")`

日時を返します。

## 例

`now()`

2019-06-03T06:30Z を返します。

`toString(now())`

「2019-06-03T06:30Z」を返します。

`now("Europe/Paris")`

2019-06-03T08:30+02:00 を返します。

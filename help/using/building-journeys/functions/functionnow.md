---
product: journey optimizer
title: now
description: now 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: now，関数，式，ジャーニー
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 94%

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

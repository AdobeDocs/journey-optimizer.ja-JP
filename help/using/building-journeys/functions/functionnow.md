---
product: journey optimizer
title: now
description: now 関数について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: now, 関数, 式, ジャーニー
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 93%

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
| 文字列 | タイムゾーン識別子（オプション） |

## シグネチャと戻り値のタイプ

`now()`

`now("<timeZone id>")`

日時を返します。

## 例

`now()`

2023-06-03T06:30Z を返します。

`toString(now())`

&quot;2023-06-03T06:30Z&quot; を返します。

`now("Europe/Paris")`

2023-06-03T08:30+02:00 を返します。

---
product: journey optimizer
title: now
description: now 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: now, 関数, 式, ジャーニー
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 77%

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

2023-06-03T06:30Z を返します。

`toString(now())`

「2023-06-03T06:30Z」を返します。

`now("Europe/Paris")`

2023-06-03T08:30+02:00 を返します。

---
product: journey optimizer
title: toDecimal
description: toDecimal 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: 小数, 関数, 式, ジャーニー
exl-id: d761fa4d-5f99-4dee-b747-3eab464c4071
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 100%

---

# toDecimal {#toDecimal}

引数の値をタイプに応じて小数値に変換します。

## カテゴリ

変換

## 関数の構文

`toDecimal(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を小数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |
| 整数 | 小数に変換します（例：1 は 1.0 になります） |

## シグネチャと戻り値のタイプ

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

## 例

`toDecimal("4.0")`

4.0 を返します。

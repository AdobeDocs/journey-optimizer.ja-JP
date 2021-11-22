---
product: adobe campaign
title: toDecimal
description: toDecimal 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d761fa4d-5f99-4dee-b747-3eab464c4071
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 15%

---

# toDecimal {#toDecimal}

引数の値を、型に応じて 10 進数値に変換します。

## カテゴリ

コンバージョン

## 関数の構文

`toDecimal(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を小数に変換します |
| dateTime | 日付をミリ秒数（エポックミリ秒）に変換します |
| ブール型 | true の場合はブール値を 1 に、false の場合は 0 に変換します |
| 整数 | を小数に変換します（例： ）。:1 は 1.0 になります ) |

## 署名と戻り値の型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

## 例

`toDecimal("4.0")`

4.0 を返します。

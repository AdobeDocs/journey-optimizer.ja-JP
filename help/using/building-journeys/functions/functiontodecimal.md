---
product: journey optimizer
title: toDecimal
description: 関数の10進数について
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d761fa4d-5f99-4dee-b747-3eab464c4071
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 0%

---

# toDecimal {#toDecimal}

引数の値を、その型に応じて10進数値に変換します。

## 項目

処理

## 関数のシンタックス

`toDecimal(<parameter>)`

## パラメーター

| 指定 | つい |
|--- |--- |
| 値 | ストリング値を10進数に変換します。 |
| dateTime | ミリ秒単位で日付を変換します (エポックミリ秒) |
| 示す | ブール値を1に設定します。 true の場合は0、false の場合は0を返します。 |
| 整数 | 10進数に変換されます (例を次に示します。: 1 が1.0 になります) |

## シグネチャと戻り値の型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

10進数を返します。

## 例

`toDecimal("4.0")`

4.0 を返します。

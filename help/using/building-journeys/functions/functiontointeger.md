---
product: journey optimizer
title: toInteger
description: toInteger 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: toInteger，関数，式，ジャーニー
exl-id: 901a91d1-13dd-4283-b87f-223196eb072f
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 94%

---

# toInteger {#toInteger}

引数の値を整数に変換します。

## カテゴリ

変換

## 関数の構文

`toInteger(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を整数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| 小数 | 小数部を削除して整数に変換します（例：1.5 は 1 になります） |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |

## シグネチャと戻り値のタイプ

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

## 例

`toInteger("4")`

4 を返します。

---
product: journey optimizer
title: toInteger
description: 関数の整数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 901a91d1-13dd-4283-b87f-223196eb072f
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# toInteger {#toInteger}

引数の値を整数に変換します。

## 項目

処理

## 関数のシンタックス

`toInteger(<parameter>)`

## パラメーター

| 指定 | つい |
|--- |--- |
| 値 | ストリング値を整数として変換します。 |
| dateTime | ミリ秒単位で日付を変換します (エポックミリ秒) |
| 形式 | 10進数部分を削除して整数に変換します (例: 1.5、1になります)。 |
| 示す | ブール値を1に設定します。 true の場合は0、false の場合は0を返します。 |

## シグネチャと戻り値の型

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

## 例

`toInteger("4")`

4を返します。

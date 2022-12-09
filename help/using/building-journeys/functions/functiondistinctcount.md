---
product: journey optimizer
title: distinctCount
description: 関数の distinctCount について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8796ba91-5c64-43c2-a444-27ac8b719c86
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 0%

---

# distinctCount{#distinctCount}

Null 値を無視して異なる値の数を数えます。

## 項目

総計

## 関数のシンタックス

`distinctCount(<listAny>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 一連 | listString |
| 一連 | listBoolean |
| 一連 | listInteger |
| 一連 | リスト10進数 |
| 一連 | listDuration |
| 一連 | listDateTime |
| 一連 | listDateTimeOnly |
| 一連 | listDateOnly |

## シグネチャと戻り値の型

`distinctCount(<listAny>)`

整数値を返します。

## 一

`distinctCount([10,2,10,null])`

2を返します。

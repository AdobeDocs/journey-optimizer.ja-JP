---
product: journey optimizer
title: listSize
description: 関数 listSize について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dd378e4d-f65a-495c-ac10-b4209d6b6b88
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 0%

---

# listSize {#listSize}

リスト内のエレメントの数を数えます。

## 項目

一連

## 関数のシンタックス

`listSize(<parameters>)`

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

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

整数を返します。

## 一

`listSize([10,2,3])`

3を返します。

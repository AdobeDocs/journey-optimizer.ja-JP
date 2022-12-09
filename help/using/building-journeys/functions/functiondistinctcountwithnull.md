---
product: journey optimizer
title: distinctCountWithNull
description: 関数の distinctCountWithNull について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2c3f629f-2220-44a4-9b0c-8aa602301098
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 0%

---

# distinctCountWithNull {#distinctCountWithNull}

Null 値を含む異なる値の数を数えます。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

## 項目

総計

## 関数のシンタックス

`distinctCountWithNull(<listAny>)`

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

`distinctCountWithNull(<listAny>)`

整数値を返します。

## 一

`distinctCountWithNull([10,2,10,null])`

3を返します。

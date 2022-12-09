---
product: journey optimizer
title: ティック
description: 関数数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6980c1ec-3afd-4fc9-ae10-76bcf7364a04
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 0%

---

# ティック {#count}

Null 値を考慮しないリストの要素を数えます。

## 項目

総計

## 関数のシンタックス

`count(<listAny>)`

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

`count(<listAny>)`

整数値を返します。

## 一

`count([10,2,10,null])`

3を返します。

---
product: journey optimizer
title: countWithNull
description: Null 値について詳しくは、ここを参照してください。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8d53b6d8-f00f-4d1a-b6df-951f84a15430
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 0%

---

# countWithNull {#countWithNull}

Null 値を含むリストのすべてのエレメントがカウントされます。

## 項目

総計

## 関数のシンタックス

`countWithNull(<listAny>)`

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

`countWithNull(<listAny>)`

整数値を返します。

## 一

`countWithNull([10,2,10,null])`

4を返します。

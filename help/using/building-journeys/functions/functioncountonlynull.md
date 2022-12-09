---
product: journey optimizer
title: countOnlyNull
description: 関数の countOnlyNull について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d06fc594-33dd-48ce-8c62-2f2892a867da
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 0%

---

# countOnlyNull {#countOnlyNull}

リスト内の null 値の数を数えます。

## 項目

総計

## 関数のシンタックス

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

整数値を返します。

## 一

`countOnlyNull([10,2,10,null])`

1を返します。

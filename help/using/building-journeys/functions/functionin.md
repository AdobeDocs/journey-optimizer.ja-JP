---
product: journey optimizer
title: 単位
description: 関数について詳しくは、
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 629b7aa3-8904-453b-ba3c-c6a333b13c81
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

---

# 単位 {#in}

1番目の引数の値がリストに含まれているかどうかをチェックします。 各引数の値に対して同じチェックが実行されます。 この関数は、引数の値が見つかった場合は true を返し、それ以外の場合は false を返します。

の型 `<expression>` はリストの項目と一致している必要があります。 リストのアイテムの種類は、アラームとして互いに一致している必要があります。

## 項目

一連

## 関数のシンタックス

`in(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 値 | 値 |
| 示す | 示す |
| 整数 | 整数 |
| 形式 | 形式 |
| 持続 | 持続 |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| 一連 | listString |
| 一連 | listBoolean |
| 一連 | listInteger |
| 一連 | リスト10進数 |
| 一連 | listDuration |
| 一連 | listDateTime |
| 一連 | listDateTimeOnly |
| 一連 | listDateOnly |

## シグネチャと戻り値の型

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

ブール値を返します。

## 一

`in(4,[4,5,3,4])`

True を返します。

`in(8,[4,5,3,4])`

False を返します。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`

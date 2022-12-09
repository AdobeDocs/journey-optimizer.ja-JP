---
product: journey optimizer
title: toDateTimeOnly
description: 関数 toDateTime について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: db54c119-5080-403a-b254-43645be6b4a8
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 0%

---

# toDateTimeOnly{#toDateTimeOnly}

引数の値を日付時刻のみの値に変換します。

## 項目

処理

## 関数のシンタックス

`toDateTimeOnly(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| ISO-8601 または「YYYY-MM-DD」形式で日付時刻 (XDM 日付フォーマット) | 値 |
| 日時 | dateTime |

## シグネチャと戻り値の型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

タイムゾーンを考慮せずに日付を返します。

## 例

`toDateTimeOnly ("2016-08-18")`

2016年 8: 00.000-08-18T00 :00:

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->

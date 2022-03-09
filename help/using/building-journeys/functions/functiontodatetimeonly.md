---
product: adobe campaign
title: toDateTimeOnly
description: toDateTime 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: db54c119-5080-403a-b254-43645be6b4a8
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 100%

---

# toDateTimeOnly{#toDateTimeOnly}

引数値を日時のみの値に変換します。

## カテゴリ

変換

## 関数の構文

`toDateTimeOnly(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601 形式つまり「YYYY-MM-DD」形式（XDM 日付形式）の日時 | 文字列 |
| 日時 | 日時 |

## シグネチャと戻り値のタイプ

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

タイムゾーンを無視して日時を返します。

## 例

`toDateTimeOnly ("2016-08-18")`

2016-08-18T00:00:00.000 を表す日時を返します。

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->

---
product: adobe campaign
title: toString
description: toString 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 06727146-2a44-4b74-aac4-be60e9e0e37c
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 9%

---

# toString {#toString}

引数の値を、型に応じて文字列値に変換します。 データタイプについて詳しくは、 [このページ](../expression/data-types.md).

## カテゴリ

コンバージョン

## 関数の構文

`toString(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| dateTime | 日付を UTC 形式に変換します |
| dateTimeOnly | 日付を UTC 形式に変換します |
| duration | ミリ秒の対応する数を文字列に変換する |
| タイムゾーン | タイムゾーン id 文字列表現 (JODA id) に変換する |
| 整数 | を値の文字列表現に変換します（1 は「1」になります） |
| decimal | を値の文字列表現に変換します（1.5 は「1.5」になります） |
| ブール型 | ブール値を true の場合は「true」、false の場合は「false」に変換します。 |

## 署名と戻り値の型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

文字列を返します。

## 例

`toString(4)`

「4」を返します。

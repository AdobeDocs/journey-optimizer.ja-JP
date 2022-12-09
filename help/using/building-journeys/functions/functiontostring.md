---
product: journey optimizer
title: toString
description: 関数 toString について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 06727146-2a44-4b74-aac4-be60e9e0e37c
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---

# toString {#toString}

引数の値を string 値に変換します。この型によって異なります。 データ型について詳しくは、このページ ](../expression/data-types.md) を [ 参照してください。

## 項目

処理

## 関数のシンタックス

`toString(<parameter>)`

## パラメーター

| 指定 | つい |
|--- |--- |
| dateTime | UTC 日付形式で日付を変換する |
| dateTimeOnly | UTC 日付形式で日付を変換する |
| 持続 | ミリ秒単位で指定した値に変換されます。 |
| 整数 | 値 (1 は &quot;1&quot; になります) のストリング表現に変換されます。 |
| 形式 | 値のストリング表現に変換されます (1.5 は、「1.5」になります)。 |
| 示す | ブール値を「true」に設定します。 true の場合は、false の場合は false になります。 |

## シグネチャと戻り値の型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

ストリングを返します。

## 一

`toString(4)`

「4」が返されます。

`toString(#{ExperiencePlatform.test_date.person.birthDate}))`

指定された &quot;dateOnly&quot; フィールドのストリング表現 (XDM 日付フィールド) を返します (例「2016-08-18」)。

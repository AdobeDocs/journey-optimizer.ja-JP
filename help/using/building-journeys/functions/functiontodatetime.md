---
product: journey optimizer
title: toDateTime
description: 関数 toDateTime について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2b487e60-593e-4bf7-9639-f469ba0f5cdc
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 0%

---

# toDateTime {#toDateTime}

タイプに応じて、パラメーターを日付時刻の値に変換します。

## 項目

処理

## 関数のシンタックス

`toDateTime(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| ISO-8601 形式の日付時刻 | 値 |
| タイムゾーン id | 値 |
| タイムゾーンのない日時 | dateTimeOnly |
| ミリ秒単位のエポックの整数値 | 整数 |

>[!NOTE]
>
>タイムゾーン id には、ストリング定数を指定する必要があります。 フィールド参照または式を指定することはできません。 データ型について詳しくは、このページ ](../expression/data-types.md) を [ 参照してください。

## シグネチャと戻り値の型

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

DateTime **を** 返します。

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## 例

`toDateTime ("2016-08-18T23:17:59.123Z")`

2016-08-18T23 :17: 59.123 z を返します。

`toDateTime(toDateTimeOnly("UTC", "2016-08-18T23:17:59.123"))`

2016-08-18T23 :17: 59.123 z を返します。

`toDateTime(1560762190189)`

2019-06-17T09 :03: 10.189 z を返します。

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->

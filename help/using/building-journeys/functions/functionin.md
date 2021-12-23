---
product: adobe campaign
title: in
description: in 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 629b7aa3-8904-453b-ba3c-c6a333b13c81
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: ht
source-wordcount: '113'
ht-degree: 100%

---

# in {#in}

最初の引数値がリストに含まれているかどうかを確認します。確認は、各引数値に対して Equal を使用して実行されます。引数の値が見つかった場合は true を返し、それ以外の場合は false を返します。

`<expression>` のタイプは、リストの項目と一致する必要があります。なお、リストの項目のタイプは互いに一致する必要があります。

## カテゴリ

リスト

## 関数の構文

`in(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| ブール値 | ブール値 |
| Integer | Integer |
| 小数 | 小数 |
| 期間 | 期間 |
| 日時 | 日時 |
| 日時のみ | 日時のみ |
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

ブール値を返します。

## 例

`in(4,[4,5,3,4])`

true を返します。

`in(8,[4,5,3,4])`

false を返します。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`

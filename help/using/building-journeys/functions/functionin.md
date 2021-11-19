---
product: adobe campaign
title: in
description: の関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: d786f3d42515d65a6574f51b6cff4b85063a0126
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 23%

---

# in {#in}

最初の引数値がリストに含まれているかどうかを確認します。 チェックは、各引数値の Equal を使用して実行されます。 引数の値が見つかった場合は true を返し、それ以外の場合は false を返します。

のタイプ `<expression>` は、リストの項目と一致する必要があります。 リマインダーとして、リストの項目のタイプが互いに一致する必要があります。

## カテゴリ

リスト

## 関数の構文

`in(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| Boolean | ブール値 |
| Integer | 整数 |
| 小数 | 小数 |
| 期間 | 期間 |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## 署名と戻り値の型

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

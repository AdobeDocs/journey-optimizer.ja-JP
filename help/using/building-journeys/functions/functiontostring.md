---
product: adobe campaign
title: toString
description: toString 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 06727146-2a44-4b74-aac4-be60e9e0e37c
source-git-commit: cca94d15da5473aa9890c67af7971f2e745d261e
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 100%

---

# toString {#toString}

引数の値を、タイプに応じて文字列値に変換します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

変換

## 関数の構文

`toString(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 日時 | 日付を UTC 日付フォーマットに変換します |
| 日時のみ | 日付を UTC 日付フォーマットに変換します |
| 期間 | 対応するミリ秒数の文字列に変換します |
| 整数 | 値の文字列表現に変換します（1 は「1」になります） |
| 小数 | 値の文字列表現に変換します（1.5 は「1.5」になります） |
| ブール値 | ブール値を true の場合は「true」、false の場合は「false」に変換します |

## シグネチャと戻り値のタイプ

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

文字列を返します。

## 例

`toString(4)`

「4」を返します。

`toString(#{ExperiencePlatform.test_date.person.birthDate}))`

例えば「2016-08-18」のように、指定された dateOnly フィールド（XDM 日付フィールド）の文字列表現を返します。

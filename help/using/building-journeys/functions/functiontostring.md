---
product: journey optimizer
title: toString
description: toString 関数について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: toString, 関数, 式, ジャーニー
exl-id: 06727146-2a44-4b74-aac4-be60e9e0e37c
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '128'
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
| 整数 | 値の文字列表現に変換します（1 は &quot;1&quot; になります） |
| 小数 | 値の文字列表現に変換します（1.5 は &quot;1.5&quot; になります） |
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

例えば「2023/08/18」のように、指定された dateOnly フィールド（XDM 日付フィールド）の文字列表現を返します。

`toString(toDuration(1520))`

「PT1.52S」を返します。

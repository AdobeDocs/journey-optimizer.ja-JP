---
product: journey optimizer
title: toDateOnly
description: toDateOnly 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1929644f-8b51-4f95-aea5-627fc1dd115d
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: ht
source-wordcount: '96'
ht-degree: 100%

---

# toDateOnly{#toDateOnly}

引数を dateOnly 型の値に変換します。データ型について詳しくは、[こちらの節](../expression/data-types.md)を参照してください。

## カテゴリ

変換

## 関数の構文

`toDateOnly(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 「YYYY-MM-DD」（XDM 形式）としての日付の文字列表現。ISO-8601 形式もサポートしています。**full-date** の部分に限り考慮されます（[RFC 3339、セクション 5.6](https://www.rfc-editor.org/rfc/rfc3339#section-5.6) | 文字列 |
| 日時 | 日時 |
| タイムゾーンを含まない日時 | 日時のみ |
| エポックのミリ秒単位の整数値 | 整数 |

## シグネチャと戻り値のタイプ

`toDateOnly(<dateTime>)`

`toDateOnly(<dateTimeOnly>)`

`toDateOnly(<string>)`

`toDateOnly(<integer>, <integer>, <integer>)`

dateOnly 型の値を返します。

## 例

`toDateOnly("2016-08-18")`

`toDateOnly("2016-08-18T00:00:00.000Z")`

`toDateOnly("2016-08-18T00:00:00")`

すべての場合、2016-08-18 を表す dateOnly オブジェクトが返されます。

`toDateOnly(#{ExperiencePlatform.ProfileFieldGroup.person.birthDate})`

dateOnly を返します。

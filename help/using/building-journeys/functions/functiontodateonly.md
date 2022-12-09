---
product: journey optimizer
title: toDateOnly
description: 関数について詳しくは、ここを参照してください。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1929644f-8b51-4f95-aea5-627fc1dd115d
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 0%

---

# toDateOnly{#toDateOnly}

引数を dateOnly 型の値に変換します。 データ型について詳しくは、ここ [ ](../expression/data-types.md) を参照してください。

## 項目

処理

## 関数のシンタックス

`toDateOnly(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 日付を「YYYY-MM-DD」 (XDM フォーマット) で表したストリング。 では、ISO-8601 形式がサポートされています。これは、完全な日付 **の部分のみ** を対象としています (RFC 3339 の5.6 項を [ 参照してください。](https://www.rfc-editor.org/rfc/rfc3339#section-5.6) | 値 |
| 日時 | dateTime |
| タイムゾーンのない日時 | dateTimeOnly |
| ミリ秒単位のエポックの整数値 | 整数 |

## シグネチャと戻り値の型

`toDateOnly(<dateTime>)`

`toDateOnly(<dateTimeOnly>)`

`toDateOnly(<string>)`

`toDateOnly(<integer>, <integer>, <integer>)`

DateOnly 型の値を返します。

## 例

`toDateOnly("2016-08-18")`

`toDateOnly("2016-08-18T00:00:00.000Z")`

`toDateOnly("2016-08-18T00:00:00")`

すべては、2016-08-18 を表す dateOnly オブジェクトを返します。

`toDateOnly(#{ExperiencePlatform.ProfileFieldGroup.person.birthDate})`

DateOnly を返します。

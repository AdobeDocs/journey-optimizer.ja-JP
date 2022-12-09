---
product: journey optimizer
title: 今すぐデルタ
description: 機能について詳しくは、「デルタ」を参照してください。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: cb1eb221-8532-4637-ac6c-8e058463ac94
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# 今すぐデルタ {#nowWithDelta}

オフセットを含む現在の日付/時刻を返します。 タイムゾーン id が指定されている場合は、タイムゾーンオフセットが適用されます。 データ型について詳しくは、このページ ](../expression/data-types.md) を [ 参照してください。

## 項目

古い

## 関数のシンタックス

`nowWithDelta(<parameters>)`

## パラメーター

| 指定 | つい |
|--- |--- |
| 増分 | 正または負の整数値 |
| 日付部分 | 年、月、日、時間、分、または秒を表すストリング |
| タイムゾーン id | タイムゾーン値を表すストリング。 詳しくは、データ型 ](../expression/data-types.md) を参照してください [ 。タイムゾーン id には、ストリング定数を指定する必要があります。 フィールド参照または式を指定することはできません。 |

## シグネチャと戻り値の型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

DateTime を返します。

## 例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

DateTime を2時間前に返します。

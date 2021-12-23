---
product: adobe campaign
title: distinctWithNull
description: distinctWithNull 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 73fa9837-d2e1-4f0a-a423-cf7728882eba
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: ht
source-wordcount: '106'
ht-degree: 100%

---

# distinctWithNull {#distinctWithNull}

リストのユニーク値を返します。リストに null 値が少なくとも 1 つ含まれる場合、返されるリストに null 値が含まれます。

## カテゴリ

リスト

## 関数の構文

`distinctWithNull(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`distinctWithNull(<listInteger>)`

整数のリストを返します。

`distinctWithNull(<listDecimal>)`

小数のリストを返します。

`distinctWithNull(<listString>)`

文字列のリストを返します。

`distinctWithNull(<listDateTimeOnly>)`

タイムゾーンを考慮しない日時のリストを返します。

`distinctWithNull(<listDateTime>)`

日時のリストを返します。

`distinctWithNull(<listDateOnly>)`

日付のリストを返します。

`distinctWithNull(<listBoolean>)`

ブール値のリストを返します。

`distinctWithNull(<listDuration>)`

期間のリストを返します。

## 例

`distinctWithNull([10,2,10,null])`

[10, 2, null] を返します。

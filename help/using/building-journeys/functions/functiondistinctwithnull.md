---
product: journey optimizer
title: distinctWithNull
description: distinctWithNull 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinctWithNull, 関数, 式, ジャーニー
exl-id: 73fa9837-d2e1-4f0a-a423-cf7728882eba
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 100%

---

# distinctWithNull {#distinctWithNull}

指定されたリストのユニークな値またはオブジェクトを返します。リストに null エントリが少なくとも 1 つ含まれる場合、返されるリストに null エントリが含まれます。

パラメーター `<listObject>` は、この関数ではサポートされません。

## カテゴリ

リスト

## 関数の構文

`distinctWithNull(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly | 処理するリスト。 |

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

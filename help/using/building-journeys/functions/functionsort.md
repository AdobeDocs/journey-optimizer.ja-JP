---
product: journey optimizer
title: 降順
description: 関数の並べ替えについて説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 607e1424-4165-48ae-b896-cce2d18f7dcc
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# 降順 {#sort}

値またはオブジェクトのリストを並べ替えます。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

## 項目

一連

## 関数のシンタックス

`sort(<parameters>)`

## パラメーター

| 指定 | 入力 | つい |
|-----------|------------------|------------------|
| リストの並べ替え | listString、Liststring、Liststring、Liststring、Liststring、Liststring、listDateTimeOnly、listDateOnly、または listObject | リストが表示されます。 ListObject の場合、フィールド参照である必要があります。 |
| keyAttributeName | 値 | このパラメーターは、listObject に対してのみ使用されます。 特定のリストのオブジェクト内の属性名は、ソートのキーとして使用されます。 |
| sortingOrder | 示す | 昇順 (true) または降順 (false) |

## シグネチャと戻り値の型

`sort(<listInteger>,<boolean>)`

整数のリストを返します。

`sort(<listDecimal>,<boolean>)`

小数点のリストを返します。

`sort(<listString>,<boolean>)`

ストリングのリストを返します。

`sort(<listDateTimeOnly>,<boolean>)`

Datetimes のリストを返します。この場合、タイムゾーンは考慮しません。

`sort(<listDateTime>,<boolean>)`

Datetimes のリストを返します。

`sort(<listDateOnly>,<boolean>)`

日付のリストを返します。

`sort(<listBoolean>,<boolean>)`

ブール値のリストを返します。

`sort(<listObject>,<string>,<boolean>)`

オブジェクトのリストを返します。

## 一

`sort(["A", "C", "B"], true)`

戻り `["A","B","C"]` ます。

`sort([1, 3, 2], false)`

戻り `[3, 2, 1]` ます。


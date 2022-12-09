---
product: journey optimizer
title: 制限
description: 関数の制限について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7fa1e393-2912-4392-b759-e54d08d5635a
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# 制限 {#limit}

リストの最初または最後の N エレメントを返します。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

## 項目

一連

## 関数のシンタックス

`limit(<parameters>)`

## パラメーター

| 指定 | 入力 | つい |
|-----------|------------------|------------------|
| listToProcess | listString、Liststring、Liststring、Liststring、Liststring、Liststring、listDateTimeOnly、listDateOnly、または listObject | リストが表示されます。 ListObject の場合、フィールド参照である必要があります。 |
| numberOfItems | 整数 | 指定されたリストから返されるアイテムの数です。 |
| 「の最後の項目」 | 示す | このパラメーターはオプションです。これは、初期設定で true に設定されています。 true を指定すると、最初の項目が返されます。 false を指定すると、最後のアイテムが返されます。 |

## シグネチャと戻り値の型

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

ストリングのリストを返します。

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

整数のリストを返します。

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

小数点のリストを返します。

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

ブール値のリストを返します。

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

日付のリストを返します。

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Datetimes のリストを返します。この場合、タイムゾーンは考慮しません。

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Datetimes のリストを返します。

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

デュレーションのリストを返します。

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

オブジェクトのリストを返します。

## 一

`limit(["A", "B", "C", "D", "E"], 3)`

戻り `["A","B","C"]` ます。

`limit(["A", "B", "C", "D", "E"], 3, false)`

戻り `["C","D","E"]` ます。

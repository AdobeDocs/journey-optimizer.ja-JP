---
product: journey optimizer
title: distinctWithNull
description: 関数の distinctWithNull について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 73fa9837-d2e1-4f0a-a423-cf7728882eba
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 0%

---

# distinctWithNull {#distinctWithNull}

指定されたリストの個別の値またはオブジェクトを返します。 リストに null エントリが少なくとも1つある場合は、返されるリストに null エントリが含まれています。

## 項目

一連

## 関数のシンタックス

`distinctWithNull(<parameters>)`

## パラメーター

| 指定 | 入力 | つい |
|-----------|------------------|------------------|
| listToProcess | listString、Liststring、Liststring、Liststring、Liststring、Liststring、listDateTimeOnly、listDateOnly、または listObject | リストが処理されます。 ListObject の場合、フィールド参照である必要があります。 |
| keyAttributeName | 値 | このパラメーターはオプションであり、listObject に対してのみ使用されます。 このパラメーターを指定しないと、すべての属性の値が同じである場合に、オブジェクトが重複していると見なされます。 それ以外の場合は、指定された属性の値が同じであれば、オブジェクトが重複していると見なされます。 |

## シグネチャと戻り値の型

`distinctWithNull(<listInteger>)`

整数のリストを返します。

`distinctWithNull(<listDecimal>)`

小数点のリストを返します。

`distinctWithNull(<listString>)`

ストリングのリストを返します。

`distinctWithNull(<listDateTimeOnly>)`

Datetimes のリストを返します。この場合、タイムゾーンは考慮しません。

`distinctWithNull(<listDateTime>)`

Datetimes のリストを返します。

`distinctWithNull(<listDateOnly>)`

日付のリストを返します。

`distinctWithNull(<listBoolean>)`

ブール値のリストを返します。

`distinctWithNull(<listDuration>)`

デュレーションのリストを返します。

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

オブジェクトのリストを返します。

## 例

`distinctWithNull([10,2,10,null])`

10、2、null を返します [ 。]

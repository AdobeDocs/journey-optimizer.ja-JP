---
product: journey optimizer
title: 異なっ
description: 関数の違いについて学習します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f4e2dd34-b634-4a91-af53-60be155a65d0
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# 異なっ {#distinct}

指定されたリストの個別の値またはオブジェクトを返します。 Null エントリは無視されます。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

## 項目

一連

## 関数のシンタックス

`distinct(<parameters>)`

## パラメーター

| 指定 | 入力 | つい |
|-----------|------------------|------------------|
| listToProcess | listString、Liststring、Liststring、Liststring、Liststring、Liststring、listDateTimeOnly、listDateOnly、または listObject | リストが処理されます。 ListObject の場合、フィールド参照である必要があります。 |
| keyAttributeName | 値 | このパラメーターはオプションであり、listObject に対してのみ使用されます。 このパラメーターを指定しないと、すべての属性の値が同じである場合に、オブジェクトが重複していると見なされます。 それ以外の場合は、指定された属性の値が同じであれば、オブジェクトが重複していると見なされます。 |

## シグネチャと戻り値の型

`distinct(<listInteger>)`

整数のリストを返します。

`distinct(<listDecimal>)`

小数点のリストを返します。

`distinct(<listString>)`

ストリングのリストを返します。

`distinct(<listDateTimeOnly>)`

Datetimes のリストを返します。この場合、タイムゾーンは考慮しません。

`distinct(<listDateTime>)`

Datetimes のリストを返します。

`distinct(<listDateOnly>)`

日付のリストを返します。

`distinct(<listBoolean>)`

ブール値のリストを返します。

`distinct(<listDuration>)`

デュレーションのリストを返します。

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

オブジェクトのリストを返します。


## 例

`distinct([10,2,10,null])`

戻り `[10, 2]` ます。

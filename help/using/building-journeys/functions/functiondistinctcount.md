---
product: journey optimizer
title: distinctCount
description: distinctCount 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinctCount, 関数, 式, ジャーニー
exl-id: 8796ba91-5c64-43c2-a444-27ac8b719c86
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 100%

---

# distinctCount{#distinctCount}

null 値を無視して異なる値の数をカウントします。

## カテゴリ

集計

## 関数の構文

`distinctCount(<listAny>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターはオプションで、listObject に対してのみ使用できます。パラメーターを指定しないと、すべての属性の値が同じ場合、オブジェクトは重複していると見なされます。パラメーターを指定していて、指定された属性が同じ値を持つ場合、オブジェクトは重複していると見なされます。 |

## シグネチャと戻り値のタイプ

`distinctCount(<listAny>)`

整数を返します。

`distinctCount(<listObject>)`

`distinctCount(<listObject>,<string>)`

オブジェクトのリストを返します。


## 例

`distinctCount([10,2,10,null])`

2 を返します。

`distinctCount(@event{my_event.productListItems})`

指定されたオブジェクト配列内の厳密に異なるオブジェクトの数を返します（listObject 型）。

`distinctCount(@event{my_event.productListItems}, "SKU")`

個別の「SKU」属性値 {} を持つオブジェクトの数を返します。

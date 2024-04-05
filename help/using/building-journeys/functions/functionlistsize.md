---
product: journey optimizer
title: listSize
description: listSize 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: listSize, 関数, 式, ジャーニー
exl-id: dd378e4d-f65a-495c-ac10-b4209d6b6b88
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 100%

---

# listSize {#listSize}

リスト内の要素の数をカウントします。

## カテゴリ

リスト

## 関数の構文

`listSize(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合、フィールド参照である必要があります。listObject に null オブジェクトを含めることはできません。 |

## シグネチャと戻り値のタイプ

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

整数を返します。

`listSize(<listObject>)`

## 例

`listSize([10,2,3])`

3 を返します。

`listSize(@event{my_event.productListItems})`

指定されたオブジェクト配列内のオブジェクト数を返します（listObject 型）。

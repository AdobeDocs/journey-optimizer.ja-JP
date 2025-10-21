---
product: journey optimizer
title: count
description: count 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: count, 関数, 式, ジャーニー
exl-id: 6980c1ec-3afd-4fc9-ae10-76bcf7364a04
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 100%

---

# count {#count}

null 値を数に入れずに、リストの要素数を数えます。

## カテゴリ

集計

## 関数の構文

`count(<listAny>)`

`count(<listObject>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合、フィールド参照である必要があります。listObject に null オブジェクトを含めることはできません。 |

## シグネチャと戻り値のタイプ

`count(<listAny>)`

整数を返します。

## 例

`count([10,2,10,null])`

3 を返します。

`count(@event{my_event.productListItems})`

指定されたオブジェクト配列内のオブジェクト数を返します（listObject 型）。注：listObject に null オブジェクトを含めることはできません

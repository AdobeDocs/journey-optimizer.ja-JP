---
product: journey optimizer
title: フィルタ
description: 関数フィルターについて説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 05e3d2ba-1a27-4f27-88cc-3d83eb3b14af
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---

# フィルタ{#filter}

指定されたキー値のいずれかと一致するキー属性を持つオブジェクトを持つ listObject を返します。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

## 項目

一連

## 関数のシンタックス

`filter(<parameters>)`

## パラメーター

| 指定 | 入力 | つい |
|-----------|------------------|------------------|
| listToFilter | listObject | フィルター処理されるオブジェクトのリストです。 フィールドリファレンスを指定する必要があります。 |
| keyAttributeName | 値 | フィルタリングのキーとして使用される、特定のリストのオブジェクト内の属性名 |
| keyValueList | 一連 | フィルタリング用のキー値の配列 |

## シグネチャと戻り値の型

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

ListObject を返します。

## 例

次の例は、受信イベントに &quot;myevent&quot; として渡されるペイロードを示しています。

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

次のエクスプレッションを使用できます。

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

「Product2」および「product3」が指定されている2つのオブジェクトを含む listObject を id として返します。

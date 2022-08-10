---
product: adobe campaign
title: sort
description: sort 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 607e1424-4165-48ae-b896-cce2d18f7dcc
source-git-commit: 0facae9e7eafc9f6fcbefbdc6d5563322eaf1251
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 並べ替え {#sort}

値のリストやオブジェクトを自然な順序に並べ替えます。

## カテゴリ

リスト

## 関数の構文

`sort(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToSort | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 並べ替えるリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターは listObject に対してのみ使用します。指定されたリストのオブジェクト内の属性名は、並べ替えのキーとして使用されます。 |
| sortingOrder | ブール値 | 昇順（true）または降順（false） |

## シグネチャと戻り値のタイプ

`sort(<listInteger>,<boolean>)`

整数のリストを返します。

`sort(<listDecimal>,<boolean>)`

小数のリストを返します。

`sort(<listString>,<boolean>)`

文字列のリストを返します。

`sort(<listDateTimeOnly>,<boolean>)`

タイムゾーンを考慮しない日時のリストを返します。

`sort(<listDateTime>,<boolean>)`

日時のリストを返します。

`sort(<listDateOnly>,<boolean>)`

日付のリストを返します。

`sort(<listBoolean>,<boolean>)`

ブール値のリストを返します。

`sort(<listObject>,<string>,<boolean>)`

オブジェクトのリストを返します。

## 例

`sort(["A", "C", "B"], true)`

`["A","B","C"]` を返します。

`sort([1, 3, 2], false)`

`[3, 2, 1]` を返します。


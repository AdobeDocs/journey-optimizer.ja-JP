---
product: journey optimizer
title: sort
description: sort 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 607e1424-4165-48ae-b896-cce2d18f7dcc
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---

# sort {#sort}

値のリストやオブジェクトを自然な順序に並べ替えます。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

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


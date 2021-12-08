---
product: adobe campaign
title: listSize
description: listSize 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dd378e4d-f65a-495c-ac10-b4209d6b6b88
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 100%

---

# listSize {#listSize}

リスト内の要素の数をカウントします。

## カテゴリ

リスト

## 関数の構文

`listSize(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

整数を返します。

## 例

`listSize([10,2,3])`

3 を返します。

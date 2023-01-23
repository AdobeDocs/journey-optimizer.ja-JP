---
product: journey optimizer
title: count
description: count 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: count，関数，式，ジャーニー
exl-id: 6980c1ec-3afd-4fc9-ae10-76bcf7364a04
source-git-commit: ad113c0414b20ac2f758ad06a44315b24a3d3d0c
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 94%

---

# count {#count}

null 値を数に入れずに、リストの要素数を数えます。

## カテゴリ

集計

## 関数の構文

`count(<listAny>)`

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

`count(<listAny>)`

整数を返します。

## 例

`count([10,2,10,null])`

3 を返します。

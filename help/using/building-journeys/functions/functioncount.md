---
product: journey optimizer
title: count
description: count 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6980c1ec-3afd-4fc9-ae10-76bcf7364a04
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

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

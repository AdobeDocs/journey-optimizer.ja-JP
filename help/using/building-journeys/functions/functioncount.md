---
product: adobe campaign
title: count
description: 関数数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: d786f3d42515d65a6574f51b6cff4b85063a0126
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 30%

---

# count {#count}

null 値を考慮しないリストの要素をカウントします。

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

## 署名と戻り値の型

`count(<listAny>)`

整数を返します。

## 例

`count([10,2,10,null])`

3 を返します。

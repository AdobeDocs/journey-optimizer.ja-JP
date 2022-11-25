---
product: journey optimizer
title: distinctCount
description: distinctCount 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8796ba91-5c64-43c2-a444-27ac8b719c86
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: ht
source-wordcount: '49'
ht-degree: 100%

---

# distinctCount{#distinctCount}

null 値を無視して異なる値の数をカウントします。

## カテゴリ

集計

## 関数の構文

`distinctCount(<listAny>)`

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

`distinctCount(<listAny>)`

整数を返します。

## 例

`distinctCount([10,2,10,null])`

2 を返します。

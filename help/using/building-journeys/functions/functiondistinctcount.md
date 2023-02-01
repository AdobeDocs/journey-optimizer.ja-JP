---
product: journey optimizer
title: distinctCount
description: distinctCount 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinctCount, 関数, 式, ジャーニー
exl-id: 8796ba91-5c64-43c2-a444-27ac8b719c86
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: ht
source-wordcount: '53'
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

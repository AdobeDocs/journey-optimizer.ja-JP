---
product: journey optimizer
title: distinctCountWithNull
description: distinctCountWithNull 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: distinctCountWithNull, 関数, 式, ジャーニー
exl-id: 2c3f629f-2220-44a4-9b0c-8aa602301098
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 100%

---

# distinctCountWithNull {#distinctCountWithNull}

null 値を含め、異なる値の数をカウントします。

パラメーター `<listObject>` は、この関数ではサポートされません。

## カテゴリ

集計

## 関数の構文

`distinctCountWithNull(<listAny>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| listToProcess | stString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly |

## シグネチャと戻り値のタイプ

`distinctCountWithNull(<listAny>)`

整数を返します。

## 例

`distinctCountWithNull([10,2,10,null])`

3 を返します。

---
product: journey optimizer
title: countWithNull
description: countWithNull 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: countWithNull, 関数, 式, ジャーニー
exl-id: 8d53b6d8-f00f-4d1a-b6df-951f84a15430
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 100%

---

# countWithNull {#countWithNull}

null 値を含むリストのすべての要素をカウントします。

パラメーター `<listObject>` は、この関数ではサポートされません。

## カテゴリ

集計

## 関数の構文

`countWithNull(<listAny>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| listToProcess | stString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly |

## シグネチャと戻り値のタイプ

`countWithNull(<listAny>)`

整数を返します。

## 例

`countWithNull([10,2,10,null])`

4 を返します。

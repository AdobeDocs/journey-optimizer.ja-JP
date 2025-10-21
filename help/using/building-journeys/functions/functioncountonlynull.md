---
product: journey optimizer
title: countOnlyNull
description: countOnlyNull 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: countOnlyNull, 関数, 式, ジャーニー
exl-id: d06fc594-33dd-48ce-8c62-2f2892a867da
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 100%

---

# countOnlyNull {#countOnlyNull}

リスト内の null 値の数をカウントします。

パラメーター `<listObject>` は、この関数ではサポートされません。

## カテゴリ

集計

## 関数の構文

`countOnlyNull(<listAny>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| listToProcess | stString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly |

## シグネチャと戻り値のタイプ

`countOnlyNull(<listAny>)`

整数を返します。

## 例

`countOnlyNull([10,2,10,null])`

1 を返します。

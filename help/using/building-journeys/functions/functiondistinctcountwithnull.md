---
product: journey optimizer
title: distinctCountWithNull
description: distinctCountWithNull 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2c3f629f-2220-44a4-9b0c-8aa602301098
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '66'
ht-degree: 100%

---

# distinctCountWithNull {#distinctCountWithNull}

null 値を含め、異なる値の数をカウントします。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

## カテゴリ

集計

## 関数の構文

`distinctCountWithNull(<listAny>)`

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

`distinctCountWithNull(<listAny>)`

整数を返します。

## 例

`distinctCountWithNull([10,2,10,null])`

3 を返します。

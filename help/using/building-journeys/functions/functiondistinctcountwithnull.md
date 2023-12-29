---
product: journey optimizer
title: distinctCountWithNull
description: distinctCountWithNull 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinctCountWithNull，関数，式，ジャーニー
exl-id: 2c3f629f-2220-44a4-9b0c-8aa602301098
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 94%

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

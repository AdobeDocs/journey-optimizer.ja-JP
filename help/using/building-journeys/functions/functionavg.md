---
product: adobe campaign
title: avg
description: 関数 avg の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: cc70f90c-2d12-42a0-829f-5f28c3c29cad
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 16%

---

# avg {#avg}

リストまたは 2 つの式のいずれかに指定された、一連の式の平均値を返します。 Null 値は無視されます。


## カテゴリ

集計

## 関数の構文

`avg(<parameter>)`

## パラメーター

サポートされるタイプ：

* listInteger
* listDecimal
* decimal
* 整数

## 署名と戻り値の型

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

小数を返します。

## 例

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0 を返します。

`avg(10.2, 3)`

6.6 を返します。

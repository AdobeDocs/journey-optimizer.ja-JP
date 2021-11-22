---
product: adobe campaign
title: sum
description: 関数の合計について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a9085f4d-6434-4bc5-8e5d-3f2b6033defc
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 15%

---

# sum {#sum}

一連の式の値の合計を返します。 Null 値は無視されます。

## カテゴリ

集計

## 関数の構文

`sum(<parameters>)`

## パラメーター

* listInteger
* listDecimal
* duration
* 整数
* decimal

## 署名と戻り値の型

`sum(<listDecimal>)`

小数を返します。

`sum(<listInteger>)`

整数を返します。

`sum(<integer>,<integer>)`

整数を返します。

`sum(<decimal>,<decimal>)`

小数を返します。

## 例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

21 を返します。

`sum([10.5,null,8.1])`

18.6 を返します。

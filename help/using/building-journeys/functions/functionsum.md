---
product: journey optimizer
title: 総額
description: 関数 sum について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a9085f4d-6434-4bc5-8e5d-3f2b6033defc
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 0%

---

# 総額 {#sum}

式セットの値の合計を返します。 Null 値は無視されます。

## 項目

総計

## 関数のシンタックス

`sum(<parameters>)`

## パラメーター

* listInteger
* リスト10進数
* 持続
* 整数
* 形式

## シグネチャと戻り値の型

`sum(<listDecimal>)`

10進数を返します。

`sum(<listInteger>)`

整数値を返します。

`sum(<integer>,<integer>)`

整数値を返します。

`sum(<decimal>,<decimal>)`

10進数を返します。

## 例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

は21を返します。

`sum([10.5,null,8.1])`

18.6 を返します。

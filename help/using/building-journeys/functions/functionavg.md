---
product: journey optimizer
title: 平均
description: 関数 avg について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: cc70f90c-2d12-42a0-829f-5f28c3c29cad
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 0%

---

# 平均 {#avg}

指定された式のセット間の平均値を返します。これは、リストまたは2つの式のいずれかで指定します。 Null 値は無視されます。


## 項目

総計

## 関数のシンタックス

`avg(<parameter>)`

## パラメーター

サポートされるタイプ:

* listInteger
* リスト10進数
* 形式
* 整数

## シグネチャと戻り値の型

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

10進数を返します。

## 例

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0 を返します。

`avg(10.2, 3)`

6.6 を返します。

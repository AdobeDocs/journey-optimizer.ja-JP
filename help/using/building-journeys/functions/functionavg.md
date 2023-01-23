---
product: journey optimizer
title: avg
description: avg 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: avg，関数，式，ジャーニー
exl-id: cc70f90c-2d12-42a0-829f-5f28c3c29cad
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 94%

---

# avg {#avg}

リストまたは 2 つの式のいずれかで指定された一連の式の平均値を返します。null 値は無視されます。


## カテゴリ

集計

## 関数の構文

`avg(<parameter>)`

## パラメーター

サポートされているタイプ：

* listInteger
* listDecimal
* 小数
* 整数

## シグネチャと戻り値のタイプ

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

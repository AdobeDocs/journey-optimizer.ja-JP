---
product: journey optimizer
title: sum
description: sum 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: sum, 関数, 式, ジャーニー
exl-id: a9085f4d-6434-4bc5-8e5d-3f2b6033defc
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: ht
source-wordcount: '55'
ht-degree: 100%

---

# sum {#sum}

 一連の式の値の合計を返します。null 値は無視されます。

## カテゴリ

集計

## 関数の構文

`sum(<parameters>)`

## パラメーター

* listInteger
* listDecimal
* 期間
* 整数
* 小数

## シグネチャと戻り値のタイプ

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

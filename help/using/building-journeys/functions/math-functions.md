---
product: journey optimizer
title: 数学関数
description: 数学関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 数学，関数，式，ジャーニー，計算，数値
version: Journey Orchestration
source-git-commit: bb47ca4957129a4d05aa3d7286409eef0cb62143
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 35%

---

# 数学関数 {#math-functions}

数学関数は、ジャーニー式での数値計算に不可欠な数学演算を提供します。 これらの関数を使用すると、データに対して正確な数値計算と変換を実行できます。

数学関数は、次の場合に使用します。

* テスト、サンプリング、ランダム化のランダム値を生成する（[random](#random)）
* よりクリーンなデータ表示のために、10 進数を最も近い整数に丸めます（[round](#round)）
* 数値フィールドに対する数学的計算の実行
* ビジネスロジックと意思決定のために数値を変換

数学関数は、小数と整数の両方の型を処理し、型変換を自動的に管理して、ジャーニー式に正確な結果を提供します。

## random {#random}

0 と 1 の間の乱数を生成します。

+++構文

`random()`

+++

+++シグネチャと戻り値のタイプ

`random()`

小数を返します。

+++

## round {#round}

引数に最も近い整数値を返します。差が同じ場合は正の無限大側に丸められます。

+++構文

`round(<parameters>)`

+++

+++パラメーター

* 小数
* 整数

+++

+++シグネチャと戻り値のタイプ

`round(<decimal>)`

`round(<integer>)`

整数を返します。

+++

+++例

`round(3.14)`

3 を返します。

`round(3.54)`

4 を返します。

`round(-3.14)`

-3 を返します。

`round(3)`

3 を返します。

+++


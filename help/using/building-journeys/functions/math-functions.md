---
product: journey optimizer
title: 数学関数
description: 数学関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 数学, 関数, 式, ジャーニー, 計算, 数値
version: Journey Orchestration
source-git-commit: bb47ca4957129a4d05aa3d7286409eef0cb62143
workflow-type: ht
source-wordcount: '156'
ht-degree: 100%

---

# 数学関数 {#math-functions}

数学関数は、ジャーニー式内の数値計算に不可欠な数学演算を提供します。これらの関数を使用すると、データに対して正確な数値計算と変換を実行できます。

数学関数は、次の操作が必要な場合に使用します。

* テスト、サンプリング、ランダム化のためにランダムな値を生成（[random](#random)）
* 小数を最も近い整数に丸めて、よりクリーンなデータ表示を実現（[round](#round)）
* 数値フィールドで数学計算を実行
* ビジネスロジックと意思決定のために数値を変換

数学関数は、小数タイプと整数タイプの両方を処理し、タイプ変換を自動的に管理して、ジャーニー式で正確な結果を確保します。

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


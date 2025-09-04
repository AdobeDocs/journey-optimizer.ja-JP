---
product: journey optimizer
title: round
description: round 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: round，関数，式，ジャーニー
exl-id: b9d5fd2f-9c7f-4811-b34f-23ce1d2c833f
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 91%

---

# round {#round}

引数に最も近い整数値を返します。差が同じ場合は正の無限大側に丸められます。

## カテゴリ

数値計算

## 関数の構文

`round(<parameters>)`

## パラメーター

* 小数
* 整数

## シグネチャと戻り値のタイプ

`round(<decimal>)`

`round(<integer>)`

整数を返します。

## 例

`round(3.14)`

3 を返します。

`round(3.54)`

4 を返します。

`round(-3.14)`

-3 を返します。

`round(3)`

3 を返します。

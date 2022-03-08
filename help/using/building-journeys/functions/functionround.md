---
product: adobe campaign
title: round
description: round 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b9d5fd2f-9c7f-4811-b34f-23ce1d2c833f
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 100%

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

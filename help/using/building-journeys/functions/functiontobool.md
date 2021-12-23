---
product: adobe campaign
title: toBool
description: toBool 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0bb68d05-bb90-48b7-aff3-82ab15d55ebe
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: ht
source-wordcount: '74'
ht-degree: 100%

---

# toBool {#toBool}

引数の値をタイプに応じてブール値に変換します。

* 文字列から変換する場合：文字列値をブール値として変換します。文字列値が「true」の場合は true、それ以外の場合は false を返します。
* 数値から変換する場合：数値が 0 に等しくない場合は true 、それ以外の場合は false を返します。

## カテゴリ

変換

## 関数の構文

`toBool(<parameter>)`

## パラメーター

* 小数
* ブール値
* 文字列
* 整数

## シグネチャと戻り値のタイプ

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

ブール値を返します。

## 例

`toBool("true")`

`toBool(1)`

true を返します。

`toBool("this is not a boolean")`

false を返します。

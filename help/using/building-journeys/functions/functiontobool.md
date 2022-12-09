---
product: journey optimizer
title: toBool
description: 関数のブール型について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0bb68d05-bb90-48b7-aff3-82ab15d55ebe
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# toBool {#toBool}

引数値をブール値に変換します (型によって異なります)。

* From string: string 値をブール値に変換してください。これは、「true」を「true」に設定し、それ以外の場合は false を指定します。
* 0以外の値が返された場合は true、それ以外の場合は false

## 項目

処理

## 関数のシンタックス

`toBool(<parameter>)`

## パラメーター

* 形式
* 示す
* 値
* 整数

## シグネチャと戻り値の型

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

ブール値を返します。

## 例

`toBool("true")`

`toBool(1)`

True を返します。

`toBool("this is not a boolean")`

False を返します。

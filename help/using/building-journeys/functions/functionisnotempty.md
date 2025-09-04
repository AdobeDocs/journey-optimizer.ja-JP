---
product: journey optimizer
title: isNotEmpty
description: isNotEmpty 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: isNotEmpty，関数，式，ジャーニー
exl-id: 654d0e3d-10d9-4a40-b9be-7979c08e0e97
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 90%

---

# isNotEmpty {#isNotEmpty}

パラメーター内の文字列が空でない場合、true を返します。

## カテゴリ

文字列

## 関数の構文

`isNotEmpty(<parameters>)`

## パラメーター

* 文字列

## シグネチャと戻り値のタイプ

`isNotEmpty(<string>)`

ブール値を返します。

## 例

`isNotEmpty("")`

false を返します。

`isNotEmpty("hello")`

true を返します。

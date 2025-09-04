---
product: journey optimizer
title: startWith
description: startWith 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: startWith，関数，式，ジャーニー
exl-id: 1abdf947-2873-4e45-a26c-cb895980e76a
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 91%

---

# startWith {#startWith}

2 番目のパラメーターが最初のパラメーターの接頭辞にある場合は、true を返します。

## カテゴリ

文字列

## 関数の構文

`startWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| 接頭辞 | 文字列 |

## シグネチャと戻り値のタイプ

`startWith(<string>,<string>)`

ブール値を返します。

## 例

`startWith("Hello World", "Hello")`

true を返します。

`startWith("Hello World", "World")`

false を返します。

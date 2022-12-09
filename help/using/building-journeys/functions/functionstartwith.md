---
product: journey optimizer
title: startWith
description: 関数 startWith ついて
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1abdf947-2873-4e45-a26c-cb895980e76a
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 0%

---

# startWith {#startWith}

第2パラメーターが1番目のパラメーターの先頭にある場合は、true を返します。

## 項目

値

## 関数のシンタックス

`startWith(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-------------|--------|
| 値 | 値 |
| いう | 値 |

## シグネチャと戻り値の型

`startWith(<string>,<string>)`

ブール値を返します。

## 一

`startWith("Hello World", "Hello")`

True を返します。

`startWith("Hello World", "World")`

False を返します。

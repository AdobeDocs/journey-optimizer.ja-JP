---
product: adobe campaign
title: endWith
description: endWith 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# endWith {#endWith}

2 番目のパラメーターが最初のパラメーターのサフィックスの場合は true を返します。

## カテゴリ

文字列

## 関数の構文

`endWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| サフィックス | 文字列 |

## 署名と戻り値の型

`endWith(<string>,<string>)`

ブール値を返します。

## 例

`endWith("Hello World", "World")`

true を返します。

`endWith("Hello World", "Hello")`

false を返します。

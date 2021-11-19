---
product: adobe campaign
title: startWithIgnoreCase
description: startWithIgnoreCase 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 27%

---

# startWithIgnoreCase {#startWithIgnoreCase}

2 番目のパラメーターが、大文字と小文字を区別せずに最初のパラメーターのプレフィックスである場合、true を返します。

## カテゴリ

文字列

## 関数の構文

`startWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| prefix | 文字列 |

## 署名と戻り値の型

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`startWithIgnoreCase("rowing is great", "RO")`

true を返します。

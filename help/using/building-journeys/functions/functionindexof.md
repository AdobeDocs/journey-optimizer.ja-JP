---
product: adobe campaign
title: indexOf
description: 関数 indexOf について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 20%

---

# indexOf {#indexOf}

最初の引数文字列が特定の文字列（2 番目の引数文字列）で終わっているかどうかをチェックします。 文字列が見つからない場合は、-1 を返します。

## カテゴリ

文字列

## 関数の構文

`indexOf(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| string | 文字列 |
| 指定された値 | 文字列 |

## 署名と戻り値の型

`indexOf(<string>,<string>)`

整数を返します。

## 例

`indexOf("Hello", "l")`

2 を返します。

説明:

「Hello」で、「l」の最初の値は位置 2 にあります。

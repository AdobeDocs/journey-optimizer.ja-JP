---
product: adobe campaign
title: containIgnoreCase
description: 関数 containIgnoreCase について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 26074584-a215-4515-8a61-7460bd9d4447
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 20%

---

# containIgnoreCase {#containIgnoreCase}

2 番目の引数文字列が最初の引数文字列に含まれているかどうかをチェックします。大文字と小文字の区別は考慮されません。

## カテゴリ

文字列

## 関数の構文

`containIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 文字列 検索済み | 文字列 |

## 署名と戻り値の型

`containIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`containIgnoreCase("rowing is great", "GREAT")`

true を返します。

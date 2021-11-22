---
product: adobe campaign
title: split
description: 関数の分割について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 37bcdf98-203c-4f82-8d8a-be2b2c45c4e7
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

---

# split {#split}

最初の引数文字列を区切り文字列（正規表現に使用できる 2 番目の引数文字列）で分割して、文字列（トークン）のリストを作成します。

## カテゴリ

文字列

## 関数の構文

`split(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 入力文字列 | 文字列 |
| 区切り文字列 | 文字列 |

## 署名と戻り値の型

`split(<input string>, <separator string>)`

listString を返します。

## 例

`split(["A_B_C"], "_")`

戻り値 `["A","B","C"]`

イベントフィールド「event.appVersion」の値の例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

戻り値 `["20", "45", "2", "3434"]`

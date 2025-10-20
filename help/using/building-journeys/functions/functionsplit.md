---
product: journey optimizer
title: split
description: split 関数について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: split, 関数, 式, ジャーニー
exl-id: 37bcdf98-203c-4f82-8d8a-be2b2c45c4e7
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 100%

---

# split {#split}

1 番目の引数文字列を区切り記号列（2 番目の引数文字列：正規表現を指定可能）で分割して、文字列（トークン）のリストを作成します。

## カテゴリ

文字列

## 関数の構文

`split(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 入力文字列 | 文字列 |
| 区切り記号列 | 文字列 |

## シグネチャと戻り値のタイプ

`split(<input string>, <separator string>)`

文字列リストを返します。

## 例

`split("A_B_C", "_")`

`["A","B","C"]` を返します。

イベントフィールド「event.appVersion」の値が「20.45.2.3434」の場合の例

`split(@event{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` を返します

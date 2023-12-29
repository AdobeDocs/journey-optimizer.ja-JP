---
product: journey optimizer
title: containIgnoreCase
description: containIgnoreCase 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: containIgnoreCase，関数，式，ジャーニー
exl-id: 26074584-a215-4515-8a61-7460bd9d4447
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 92%

---

# containIgnoreCase {#containIgnoreCase}

2 番目の引数文字列が最初の引数文字列に含まれているかどうかを、大文字と小文字の区別をせずに確認します。

## カテゴリ

文字列

## 関数の構文

`containIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 検索文字列 | 文字列 |

## シグネチャと戻り値のタイプ

`containIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`containIgnoreCase("rowing is great", "GREAT")`

true を返します。

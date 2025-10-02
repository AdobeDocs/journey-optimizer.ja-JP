---
product: journey optimizer
title: endWithIgnoreCase
description: endWithIgnoreCase 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: endWithIgnoreCase, 関数, 式, ジャーニー
exl-id: 278ef1a4-571c-4b5f-b4de-0cfc644ac7d7
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

---

# endWithIgnoreCase {#endWithIgnoreCase}

最初の引数文字列が特定の文字列（2 番目の引数文字列）で終わっているかどうかを、大文字と小文字の区別をせずに確認します。

## カテゴリ

文字列

## 関数の構文

`endWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 末尾の文字列 | 文字列 |

## シグネチャと戻り値のタイプ

`endWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`endWithIgnoreCase("rowing is great", "AT")`

true を返します。

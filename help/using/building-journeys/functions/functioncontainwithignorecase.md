---
product: journey optimizer
title: containIgnoreCase
description: 関数の containIgnoreCase について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 26074584-a215-4515-8a61-7460bd9d4447
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 0%

---

# containIgnoreCase {#containIgnoreCase}

第2引数のストリングが最初の引数ストリングに含まれているかどうかを確認します。大文字と小文字は考慮されません。

## 項目

値

## 関数のシンタックス

`containIgnoreCase(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 値 | 値 |
| 検索されるストリング | 値 |

## シグネチャと戻り値の型

`containIgnoreCase(<string>,<string>)`

ブール値を返します。

## 一

`containIgnoreCase("rowing is great", "GREAT")`

True を返します。

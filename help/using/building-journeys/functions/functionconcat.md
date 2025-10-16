---
product: journey optimizer
title: concat
description: concat 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: concat, 関数, 式, ジャーニー
exl-id: 690c8aa9-f754-4720-b4ed-a338e5d3b79d
version: Journey Orchestration
source-git-commit: 7ac246c0aa6776d3ec67223c4b07536b8ed0c881
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# concat {#concat}

2 つの文字列パラメーターまたは 1 つの文字列リストを連結します。

## カテゴリ

文字列

## 関数の構文

`concat(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| 文字列 | 文字列 |

## シグネチャと戻り値のタイプ

`concat(<string>,<string>)`

`concat(<listString>)`

文字列を返します。

## 例

`concat("Hello","World")`

「HelloWorld」を返します。

`concat(["Hello"," ","World"])`

「Hello World」を返します。

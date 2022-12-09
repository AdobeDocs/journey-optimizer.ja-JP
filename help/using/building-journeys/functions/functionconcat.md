---
product: journey optimizer
title: 連結
description: 関数の連結について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 690c8aa9-f754-4720-b4ed-a338e5d3b79d
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 0%

---

# 連結 {#concat}

2つのストリングパラメーターまたはストリングのリストを連結します。

## 項目

値

## 関数のシンタックス

`concat(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 一連 | listString |
| 値 | 値 |

## シグネチャと戻り値の型

`concat(<string>,<string>)`

`concat(<listString>)`

ストリングを返します。

## 一

`concat("Hello","World")`

&quot;HelloWorld&quot; を返します。

`concat(["Hello"," ","World"])`

「Hello World」を返します。

---
product: journey optimizer
title: endWith
description: endWith 関数について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: endWith, 関数, 式, ジャーニー
exl-id: ae54c127-9de2-42fd-942c-664d2cfe66d2
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 100%

---

# endWith {#endWith}

2 番目のパラメーターが最初のパラメーターの末尾にある場合、true を返します。

## カテゴリ

文字列

## 関数の構文

`endWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 末尾の文字列 | 文字列 |

## シグネチャと戻り値のタイプ

`endWith(<string>,<string>)`

ブール値を返します。

## 例

`endWith("Hello World", "World")`

true を返します。

`endWith("Hello World", "Hello")`

false を返します。

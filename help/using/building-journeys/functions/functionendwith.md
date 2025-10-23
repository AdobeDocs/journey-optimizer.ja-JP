---
product: journey optimizer
title: endWith
description: endWith 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: endWith, 関数, 式, ジャーニー
exl-id: ae54c127-9de2-42fd-942c-664d2cfe66d2
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: ht
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

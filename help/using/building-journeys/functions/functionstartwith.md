---
product: journey optimizer
title: startWith
description: startWith 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: startWith, 関数, 式, ジャーニー
exl-id: 1abdf947-2873-4e45-a26c-cb895980e76a
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: ht
source-wordcount: '47'
ht-degree: 100%

---

# startWith {#startWith}

2 番目のパラメーターが最初のパラメーターの接頭辞にある場合は、true を返します。

## カテゴリ

文字列

## 関数の構文

`startWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| 接頭辞 | 文字列 |

## シグネチャと戻り値のタイプ

`startWith(<string>,<string>)`

ブール値を返します。

## 例

`startWith("Hello World", "Hello")`

true を返します。

`startWith("Hello World", "World")`

false を返します。

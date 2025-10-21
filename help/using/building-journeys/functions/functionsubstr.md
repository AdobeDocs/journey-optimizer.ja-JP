---
product: journey optimizer
title: substr
description: substr 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: substr, 関数, 式, ジャーニー
exl-id: 58a3107a-b4f3-43da-b454-5ce597515847
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 100%

---

# substr {#substr}

文字列式の開始インデックスと終了インデックスの間にある部分文字列を返します。終了インデックスが指定されていない場合は、文字列式の開始インデックスと末尾の間にある部分文字列を返します。

## カテゴリ

文字列

## 関数の構文

`substr(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|----------|
| 文字列 | 文字列 |
| beginIndex | 整数 |
| 終了インデックス | 整数 |

## シグネチャと戻り値のタイプ

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

文字列を返します。

## 例

`substr("Hello World",6)`

「World」を返します。

`substr("Hello World", 0, 5)`

「Hello」を返します。

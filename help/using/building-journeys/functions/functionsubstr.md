---
product: journey optimizer
title: substr
description: 関数の substr について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 58a3107a-b4f3-43da-b454-5ce597515847
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 0%

---

# substr {#substr}

開始インデックスと終了インデックスの間にある、ストリング式のサブストリングを返します。 終了インデックスが定義されていない場合は、begin index と end index の間に指定されます。

## 項目

値

## 関数のシンタックス

`substr(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-------------|----------|
| 値 | 値 |
| beginIndex | 整数 |
| endIndex | 整数 |

## シグネチャと戻り値の型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

ストリングを返します。

## 一

`substr("Hello World",6)`

「World」を返します。

`substr("Hello World", 0, 5)`

は「Hello」を返します。

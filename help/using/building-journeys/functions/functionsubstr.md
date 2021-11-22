---
product: adobe campaign
title: substr
description: 関数 substr の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 58a3107a-b4f3-43da-b454-5ce597515847
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 18%

---

# substr {#substr}

開始インデックスと終了インデックスの間の文字列式の部分文字列を返します。 end インデックスが定義されていない場合、begin インデックスと end インデックスの間にあります。

## カテゴリ

文字列

## 関数の構文

`substr(<parameters>)`

## パラメーター

| パラメーター | type |
|-------------|----------|
| 文字列 | 文字列 |
| beginIndex | 整数 |
| endIndex | 整数 |

## 署名と戻り値の型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

文字列を返します。

## 例

`substr("Hello World",6)`

「World」を返します。

`substr("Hello World", 0, 5)`

「Hello」を返します。

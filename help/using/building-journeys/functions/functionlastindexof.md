---
product: journey optimizer
title: lastIndexOf
description: lastIndexOf 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: lastIndexOf, 関数, 式, ジャーニー
exl-id: f11f164b-51b5-4b01-8057-ff29d80d2e2c
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 100%

---

# lastIndexOf {#lastIndexOf}

2 番目のパラメータが最後に現れる（最初の引数内の）位置を返します。一致するものがない場合は -1 を返します。

## カテゴリ

文字列

## 関数の構文

`lastIndexOf(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| string | String |
| 指定値 | 文字列 |

## シグネチャと戻り値のタイプ

`lastIndexOf(<string>,<string>)`

整数を返します。

## 例

`lastIndexOf("Hello", "l")`

3 を返します。

説明：

「Hello」で「l」が最後に出現するのは位置 3 です。

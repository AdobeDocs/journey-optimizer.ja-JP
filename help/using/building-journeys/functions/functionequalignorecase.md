---
product: journey optimizer
title: equalIgnoreCase
description: equalIgnoreCase 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: equalIgnoreCase, 関数, 式, ジャーニー
exl-id: b74ef5c9-0202-4a69-8870-77004a4397e0
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 100%

---

# equalIgnoreCase {#equalIgnoreCase}

大文字と小文字を区別せずに、最初の引数文字列と 2 番目の引数文字列を比較します。

## カテゴリ

文字列

## 関数の構文

`equalIgnoreCase(<parameters>)`

## パラメーター

* 文字列

## シグネチャと戻り値のタイプ

`equalIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`equalIgnoreCase("rowing is great", "rowing is GREAT")`

true を返します。

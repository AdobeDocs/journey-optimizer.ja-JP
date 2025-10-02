---
product: journey optimizer
title: startWithIgnoreCase
description: startWithIgnoreCase 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: startWithIgnoreCase, 関数, 式, ジャーニー
exl-id: b6bd9f77-272f-4c2b-b085-20ab5f043793
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# startWithIgnoreCase {#startWithIgnoreCase}

大文字と小文字を区別しない場合に 2 番目のパラメーターが最初のパラメーターの接頭辞としてある場合は、true を返します。

## カテゴリ

文字列

## 関数の構文

`startWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| 接頭辞 | 文字列 |

## シグネチャと戻り値のタイプ

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`startWithIgnoreCase("rowing is great", "RO")`

true を返します。

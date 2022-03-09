---
product: adobe campaign
title: startWithIgnoreCase
description: startWithIgnoreCase 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b6bd9f77-272f-4c2b-b085-20ab5f043793
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# startWithIgnoreCase {#startWithIgnoreCase}

大文字と小文字を区別しない場合に 2 番目のパラメーターが最初のパラメーターの先頭にある場合は、true を返します。

## カテゴリ

文字列

## 関数の構文

`startWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| 先頭の文字列 | 文字列 |

## シグネチャと戻り値のタイプ

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`startWithIgnoreCase("rowing is great", "RO")`

true を返します。

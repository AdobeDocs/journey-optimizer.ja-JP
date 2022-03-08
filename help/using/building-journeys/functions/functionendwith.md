---
product: adobe campaign
title: endWith
description: endWith 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ae54c127-9de2-42fd-942c-664d2cfe66d2
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '43'
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

---
product: journey optimizer
title: matchRegExp
description: 関数の matchRegExp について
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 24cf362c-f390-4bb1-be82-a079bc27fa1f
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 0%

---

# matchRegExp {#matchRegExp}

最初のパラメーターの文字列が、2番目のパラメーターの正規表現と一致する場合は、true を返します。 詳しくは、このページ ](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html) を参照してください [ 。

## 項目

値

## 関数のシンタックス

`matchRegExp(<parameters>)`

## パラメーター

| 指定 | 入力 |
|--- |--- |
| 値 | 値 |
| 表現 | 値 |

## シグネチャと戻り値の型

`matchRegExp(<string>,<string>)`

ブール値を返します。

## 一

`matchRegExp("username@adobe.com", "*adobe")`

True を返します。

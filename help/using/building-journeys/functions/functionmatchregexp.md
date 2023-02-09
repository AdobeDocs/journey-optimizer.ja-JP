---
product: journey optimizer
title: matchRegExp
description: matchRegExp 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: matchRegExp, 関数, 式, ジャーニー
exl-id: 24cf362c-f390-4bb1-be82-a079bc27fa1f
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 100%

---

# matchRegExp {#matchRegExp}

1 番目のパラメーターの文字列が 2 番目のパラメーターの正規表現と一致する場合、true を返します。 詳しくは、[このページ](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)を参照してください。

## カテゴリ

文字列

## 関数の構文

`matchRegExp(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 文字列 | 文字列 |
| 正規表現 | 文字列 |

## シグネチャと戻り値のタイプ

`matchRegExp(<string>,<string>)`

ブール値を返します。

## 例

`matchRegExp("username@adobe.com", "*adobe")`

true を返します。

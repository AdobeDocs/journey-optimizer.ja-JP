---
product: adobe campaign
title: replace
description: replace 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3eb35fd6-2d11-4f24-b0d9-5334e7ed7872
source-git-commit: 68407db81224e9c2b6930c800e57b65e081781fe
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 100%

---

# 置換 {#replace}

ターゲット文字列に一致する最初の出現箇所を、ベース文字列内の置換文字列で置き換えます。

置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

文字列

## 関数の構文

`replace(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base（ベース文字列） | 文字列 |
| target（ターゲット文字列） | 文字列 |
| replacement（置換文字列） | 文字列 |

## シグネチャと戻り値のタイプ

`replace(<base>,<target>,<replacement>)`

文字列を返します。

## 例

`replace("Hello World", "l", "x")`

「Hexlo World」を返します。

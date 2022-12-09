---
product: journey optimizer
title: endend
description: 関数 endWith について
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ae54c127-9de2-42fd-942c-664d2cfe66d2
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 0%

---

# endend {#endWith}

第2パラメーターが1番目のパラメーターとして指定されている場合は、true を返します。

## 項目

値

## 関数のシンタックス

`endWith(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 値 | 値 |
| 与える | 値 |

## シグネチャと戻り値の型

`endWith(<string>,<string>)`

ブール値を返します。

## 一

`endWith("Hello World", "World")`

True を返します。

`endWith("Hello World", "Hello")`

False を返します。

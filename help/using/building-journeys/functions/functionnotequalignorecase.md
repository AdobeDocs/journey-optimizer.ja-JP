---
product: journey optimizer
title: notEqualIgnoreCase
description: 関数の notEqualIgnoreCase について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 74f8cae0-7d2f-4f5e-bc13-837c9bc69ad9
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 0%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

2番目の引数ストリングの最初の引数文字列が異なるかどうかを確認します。大文字と小文字の違いは無視されます。

## 項目

値

## 関数のシンタックス

`notEqualIgnoreCase(<parameters>)`

## パラメーター

* 値

## シグネチャと戻り値の型

`notEqualIgnoreCase(<string>,<string>)`

ブール値を返します。

## 一

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`

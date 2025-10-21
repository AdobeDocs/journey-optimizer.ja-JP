---
product: journey optimizer
title: notEqualIgnoreCase
description: notEqualIgnoreCase 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: notEqualIgnoreCase, 関数, 式, ジャーニー
exl-id: 74f8cae0-7d2f-4f5e-bc13-837c9bc69ad9
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 100%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

最初の引数の文字列と 2 番目の引数の文字列が異なるかどうかを、大文字と小文字の区別を無視して確認します。

## カテゴリ

文字列

## 関数の構文

`notEqualIgnoreCase(<parameters>)`

## パラメーター

* 文字列

## シグネチャと戻り値のタイプ

`notEqualIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`notEqualIgnoreCase(@event{iOSPushPermissionAllowed.device.model}, "iPad")`

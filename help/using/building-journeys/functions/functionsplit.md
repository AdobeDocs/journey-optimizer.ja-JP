---
product: journey optimizer
title: 分割
description: 関数分割について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 37bcdf98-203c-4f82-8d8a-be2b2c45c4e7
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 0%

---

# 分割 {#split}

最初の引数のストリングが区切りストリング (正規表現になる場合があります) に分割され、ストリングのリスト (トークン) が生成されます。

## 項目

値

## 関数のシンタックス

`split(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 入力ストリング | 値 |
| 区切り文字 | 値 |

## シグネチャと戻り値の型

`split(<input string>, <separator string>)`

ListString を返します。

## 一

`split(["A_B_C"], "_")`

制御 `["A","B","C"]`

次の例では、値が value: &quot;20.45.2.3434&quot; であるイベントフィールド &#39; appVersion &#39; を使用しています。

`split(@{event.appVersion}, "\\.")`

制御 `["20", "45", "2", "3434"]`

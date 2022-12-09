---
product: journey optimizer
title: replaceAll
description: 関数の replaceAll について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 5543e123-a5f4-4153-8709-97eeb9be83ba
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# replaceAll {#replaceAll}

ターゲットストリングに一致するすべてのオカレンスが、ベースストリング内の置換ストリングで置き換えられます。

置換は、ストリングの最初から最後まで実行されます。例えば、「aa」を「a」と指定すると、「aa」が「ab」ではなく「ba」に置き換えられます。

## 項目

値

## 関数のシンタックス

`replaceAll(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|--------------|
| ベース | 値 |
| 変換 | string (RegExp) |
| 置換 | 値 |

## シグネチャと戻り値の型

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

ストリングを返します。

## 一{#example}

`replaceAll("Hello World", "l", "x")`

&quot;Hexxo したね Xd&quot; を返します。

ターゲットパラメーターは RegExp であるので、置換するストリングによっては、エスケープする必要がある文字がある場合もあります。 このページ ](../functions/functionreplace.md#example_2) の [ 例を参照してください。

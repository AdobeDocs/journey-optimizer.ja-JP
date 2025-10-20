---
product: journey optimizer
title: replaceAll
description: replaceAll 関数について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: replaceAll, 関数, 式, ジャーニー
exl-id: 5543e123-a5f4-4153-8709-97eeb9be83ba
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# replaceAll {#replaceAll}

ターゲット文字列に一致するすべての出現箇所をベース文字列内の置換文字列で置き換えます。

置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

文字列

## 関数の構文

`replaceAll(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base（ベース文字列） | 文字列 |
| target（ターゲット文字列） | 文字列（RegExp） |
| replacement（置換文字列） | 文字列 |

## シグネチャと戻り値のタイプ

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

文字列を返します。

## 例{#example}

`replaceAll("Hello World", "l", "x")`

「Hexxo Worxd」を返します。

ターゲットパラメーターは RegExp なので、置き換える文字列に応じて、一部の文字をエスケープする必要が生じる場合があります。例について詳しくは、[このページ](../functions/functionreplace.md#example_2)を参照してください。

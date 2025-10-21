---
product: journey optimizer
title: serializeList
description: serializeList 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: serializeList, 関数, 式, ジャーニー
exl-id: 7ead9fa1-59b3-4960-818c-fe6321422952
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 100%

---

# serializeList {#serializeList}

指定されたリスト（listObject 以外の任意の型）を文字列に変換します。

## カテゴリ

リスト

## 関数の構文

`serializeList(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | stString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly | 文字列に変換するリスト。 |
| 区切り記号 | 文字列 | 出力文字列内の各リスト要素間の区切り記号。 |
| addQuotes | ブール値 | このパラメーターは、出力文字列の各要素に引用符を含める（true）か、含まない（false）かを示します。 |

## シグネチャと戻り値のタイプ

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

文字列を返します。

## 例

`serializeList(["Hello","World"], " ", false)`

「Hello World」を返します。

`serializeList(["Hello", "World"], ",", true)`

「&quot;Hello&quot;,&quot;World&quot;」を返します。

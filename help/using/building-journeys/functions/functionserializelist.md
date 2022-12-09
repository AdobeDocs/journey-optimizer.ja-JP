---
product: journey optimizer
title: serializeList
description: 関数の serializeList について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7ead9fa1-59b3-4960-818c-fe6321422952
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---

# serializeList {#serializeList}

最初のパラメーターによって指定されたリスト (任意の型) をストリングに変換します。 第2パラメーターは、使用する区切り文字を表します。 3番目のパラメーターは、式の各要素に引用符を含めるかどうかを示すブール値です。

## 項目

一連

## 関数のシンタックス

`serializeList(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 値 | 値 |
| 示す | 示す |
| DateTimeOnly | DateTimeOnly |
| 一連 | listString |
| 一連 | listBoolean |
| 一連 | listPoint |
| 一連 | リスト10進数 |
| 一連 | listDuration |
| 一連 | listDateTime |
| 一連 | listDateTimeOnly |
| 一連 | listDateOnly |

## シグネチャと戻り値の型

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

ストリングを返します。

## 一

`serializeList(["Hello","World"], " ", false)`

「Hello World」を返します。

`serializeList(["Hello", "World"], ",", true)`

&quot;&quot; Hello &quot;、&quot; World &quot;という戻り値を返します。

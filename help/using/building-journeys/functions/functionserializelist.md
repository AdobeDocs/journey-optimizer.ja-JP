---
product: journey optimizer
title: serializeList
description: serializeList 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: serializeList, 関数, 式, ジャーニー
exl-id: 7ead9fa1-59b3-4960-818c-fe6321422952
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 100%

---

# serializeList {#serializeList}

最初のパラメーターで指定されたリスト（任意のタイプ）を文字列に変換します。 2 番目のパラメーターは、使用する区切り文字を表します。 3 番目のパラメーターは、式の各要素に引用符を含めるかどうかを示すブール値です。

## カテゴリ

リスト

## 関数の構文

`serializeList(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| ブール値 | ブール値 |
| 日時のみ | 日時のみ |
| リスト | listString |
| リスト | listBoolean |
| リスト | listPoint |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

文字列を返します。

## 例

`serializeList(["Hello","World"], " ", false)`

「Hello World」を返します。

`serializeList(["Hello", "World"], ",", true)`

「&quot;Hello&quot;,&quot;World&quot;」を返します。

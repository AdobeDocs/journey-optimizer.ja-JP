---
product: journey optimizer
title: countWithNull
description: countWithNull 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: countWithNull, 関数, 式, ジャーニー
exl-id: 8d53b6d8-f00f-4d1a-b6df-951f84a15430
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: ht
source-wordcount: '53'
ht-degree: 100%

---

# countWithNull {#countWithNull}

null 値を含むリストのすべての要素をカウントします。

## カテゴリ

集計

## 関数の構文

`countWithNull(<listAny>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`countWithNull(<listAny>)`

整数を返します。

## 例

`countWithNull([10,2,10,null])`

4 を返します。

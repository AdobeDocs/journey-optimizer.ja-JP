---
product: journey optimizer
title: countWithNull
description: countWithNull 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8d53b6d8-f00f-4d1a-b6df-951f84a15430
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: ht
source-wordcount: '49'
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

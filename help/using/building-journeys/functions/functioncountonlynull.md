---
product: journey optimizer
title: countOnlyNull
description: countOnlyNull 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: countOnlyNull, 関数, 式, ジャーニー
exl-id: d06fc594-33dd-48ce-8c62-2f2892a867da
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: ht
source-wordcount: '52'
ht-degree: 100%

---

# countOnlyNull {#countOnlyNull}

リスト内の null 値の数をカウントします。

## カテゴリ

集計

## 関数の構文

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

整数を返します。

## 例

`countOnlyNull([10,2,10,null])`

1 を返します。

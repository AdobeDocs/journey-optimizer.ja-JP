---
product: journey optimizer
title: 置き
description: 関数の置き換えについて説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3eb35fd6-2d11-4f24-b0d9-5334e7ed7872
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# 置き {#replace}

ターゲットストリングの最初の出現箇所が、ベースストリング内の置換ストリングに置き換えられます。

置換は、ストリングの最初から最後まで実行されます。例えば、「aa」を「a」と指定すると、「aa」が「ab」ではなく「ba」に置き換えられます。

## 項目

値

## 関数のシンタックス

`replace(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|--------------|
| ベース | 値 |
| 変換 | string (RegExp) |
| 置換 | 値 |

## シグネチャと戻り値の型

`replace(<base>,<target>,<replacement>)`

ストリングを返します。

## 例1

`replace("Hello World", "l", "x")`

「Hexlo World」という結果が返されます。

## 例2 {#example_2}

ターゲットパラメーターは RegExp であるので、置換するストリングによっては、エスケープする必要がある文字がある場合もあります。 次に例を示します。

* 評価する文字列: `|OFFER_A|OFFER_B`
* profile 属性によって提供されます。 `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* 置換されるストリング: `|OFFER_A`
* 置換後のストリング: `''`
* 文字の `|` 前にを追加 `\\` する必要があります。

式は以下のとおりです。

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

返されるストリングは、次のとおりです。 `|OFFER_B`

特定の属性から置き換えられるストリングを作成することもできます。

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`

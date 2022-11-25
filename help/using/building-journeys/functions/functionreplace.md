---
product: journey optimizer
title: replace
description: replace 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3eb35fd6-2d11-4f24-b0d9-5334e7ed7872
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: ht
source-wordcount: '147'
ht-degree: 100%

---

# replace {#replace}

ターゲット文字列に一致する最初の出現箇所を、ベース文字列内の置換文字列で置き換えます。

置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

文字列

## 関数の構文

`replace(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base（ベース文字列） | 文字列 |
| target（ターゲット文字列） | 文字列（RegExp） |
| replacement（置換文字列） | 文字列 |

## シグネチャと戻り値のタイプ

`replace(<base>,<target>,<replacement>)`

文字列を返します。

## 例 1

`replace("Hello World", "l", "x")`

「Hexlo World」を返します。

## 例 2 {#example_2}

ターゲットパラメーターは RegExp なので、置き換える文字列に応じて、一部の文字をエスケープする必要が生じる場合があります。次に例を示します。

* 評価する文字列：`|OFFER_A|OFFER_B`
* プロファイル属性 `#{ExperiencePlatform.myFieldGroup.profile.myOffers}` によって提供されます
* 置き換える文字列：`|OFFER_A`
* `''` によって置き換えられた文字列
* `|` 文字の前に `\\` を追加する必要があります。

式は次の通りです。

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

返される文字列は `|OFFER_B` です。

指定した属性から置き換える文字列を構築することもできます。

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`

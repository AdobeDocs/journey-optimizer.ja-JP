---
product: journey optimizer
title: toDuration
description: toDuration 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: toDuration, 関数, 式, ジャーニー
exl-id: c78e30c5-99ee-4dc7-a03a-17f7ee65f83a
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%

---

# toDuration {#toDuration}

引数の値を期間に変換します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

変換

## 関数の構文

`toDuration(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601 の期間形式 PnDTnHnMn.nS に基づく形式（日数は正確に 24 時間と見なされます） |
| 整数 | ミリ秒数 |

文字列式の場合：指定できる形式は、ISO-8601 期間形式 PnDTnHnMn.nS に基づいたもので、1 日は正確に 24 時間と見なされます。

文字列は、ASCII の負または正の記号で表されるオプションの符号で始まります。負の場合は、期間全体が負の値になります。ASCII 文字「P」が次に現れ、大文字または小文字で表されます。その後に 4 つのセクションがあり、それぞれが数値とサフィックスで構成されます。各セクションには、日、時間、分および秒を示す「D」、「H」、「M」および「S」の ASCII サフィックスがあります（大文字でも小文字でもかまいません）。サフィックスは、順序に従って現れる必要があります。ASCII 文字「T」は、時、分、秒のセクションの最初の出現箇所（存在する場合）より前に記述する必要があります。4 つのセクションのうち少なくとも 1 つが存在し、「T」が存在する場合は、「T」の後に少なくとも 1 つのセクションが存在する必要があります。各セクションの数値部分は、1 つ以上の ASCII 数字で構成される必要があります。数字の接頭辞は、ASCII の負または正の符号を付けてもかまいません。日数、時間数および分数は long 型の値に解析される必要があります。秒数は long 型の値（オプションで小数を含む）に解析される必要があります。小数点はドットまたはコンマです。小数部は 0～9 桁まで可能です。

## シグネチャと戻り値のタイプ

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

## 例

`toDuration("PT10H")`

10 時間の期間を返します。

`toDuration("PT4S")`

4 秒の期間を返します。

`toDuration(4000)`

4 秒の期間を返します。

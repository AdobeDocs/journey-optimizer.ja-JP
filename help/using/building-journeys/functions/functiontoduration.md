---
product: journey optimizer
title: toDuration
description: 関数について詳しくは、Duration
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c78e30c5-99ee-4dc7-a03a-17f7ee65f83a
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---

# toDuration {#toDuration}

引数の値を duration に変換します。 データ型について詳しくは、このページ ](../expression/data-types.md) を [ 参照してください。

## 項目

処理

## 関数のシンタックス

`toDuration(<parameter>)`

## パラメーター

| 指定 | つい |
|--- |--- |
| 値 | ISO-8601 duration フォーマットの PnDTnHnMn に基づくフォーマット、日付は24時間とみなされます |
| 整数 | ミリ秒数 |

ストリング式の場合、指定できるフォーマットは、ISO-8601 duration フォーマットの PnDTnHnMn に基づいています。これは、日付が ISO-になります。

ストリングはオプションの符号で始まります。この記号は、ASCII の正負の記号で表されます。 負の値を指定すると、ピリオド全体が負数になります。 ASCII 文字「P」は、次の大文字または小文字で入力します。 4つのセクションがあり、各セクションには数字と接尾文字が含まれています。 これらのセクションには、ASCII では &quot;D&quot;、&quot;H&quot;、&quot;M&quot;、&quot;M&quot; および &quot;S&quot; という接尾辞が付いています。これは、大文字と小文字のどちらでも受け入れられます。 サフィックスは順番に出現する必要があります。 ASCII 文字「T」は、1時、毎分、または秒セクションが最初に出現する場所より前にある必要があります。 4つのセクションのうち少なくとも1つは存在している必要があります。「T」が表示されている場合は、「T」よりも後に1つ以上のセクションがなければなりません。 各セクションの番号部分は、1つ以上の ASCII 数字で構成する必要があります。 数字の先頭には、ASCII マイナス記号または正符号が付けられます。 日数、時間および分は、同様に解析する必要があります。 秒数は、オプションの分数と共に解析する必要があります。 小数点の部分には、ドット (.) またはカンマ (,) を使用することもできます。 小数部分に 0 ~ 9 桁を設定することもできます。

## シグネチャと戻り値の型

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

## 例

`toDuration("PT10H")`

は、10時間の期間を返します。

`toDuration("PT4S")`

4s の期間を返します。

`toDuration(4000)`

4s の期間を返します。

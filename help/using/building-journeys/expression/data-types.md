---
solution: Journey Optimizer
product: journey optimizer
title: データ型
description: アドバンスエクスプレッションでのデータ型について
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fdfc3287-d733-45fb-ad11-b4238398820a
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# データ型 {#data-types}

厳密には、定数には常にデータ型が含まれています。 リテラル式では、値のみが指定されています。 データ型は、string、integer、decimal などの値を使用して推論できます。 日時のような特定の状況については、表現に専用の関数を使用することになります。

以下の各セクションでは、各種のデータ型表現について説明し、その表現方法について説明します。

## 値 {#string}

**つい**

一般的な一連の文字。 メモリ容量は、使用可能なメモリ量など、環境によっては明示的に指定されたサイズであるとは限りません。

JSON 形式: String

シリアル化フォーマット: UTF-8

**リテラル表現**

```json
"<value>"
```

```json
'<value>'
```

**一**

```json
"hello world"
```

```json
'hello world'
```

## 整数 {#integer}

**つい**

-2 ^ 63 から 2 ^ 63-1 までの整数値。

JSON 形式: Number

**リテラル表現**

```json
<integer value>
```

**一**

```json
42
```

## 形式 {#decimal}

**つい**

10進数を指定します。 これは、未確定値を表します。

* 倍精度浮動小数点型の最大正の有限値 (2 ~ 2 ^-52) x2 ^ 1023
* 倍精度浮動小数点型の正の値。2-1022
* 倍精度浮動小数点型の正の0以外の値。 2 p-1074

JSON 形式: Number

シリアル化フォーマット: 「.」 小数点の区切り文字として

**リテラル表現**

```json
<integer value>.<integer value>
```

**一**

```json
3.14
```

## 示す {#boolean}

**つい**

ブール値が小文字で記述されています。 true または false です。

JSON 形式: ブール値

**リテラル表現**

```json
true
```

```json
false
```

**一**

```json
true
```

## dateOnly{#date-only}

**つい**

日付は、タイムゾーンを指定しない場合は、年と月を表示します。

誕生日に使用されている日付の説明があります。

JSON 形式: String。

形式は、YYYY-MM-DD (ISO-8601) のようになります。例えば、「2021-03-11」のようになります。

ToDateOnly 関数にカプセル化することができます。

DateTimeFormatter ISO_LOCAL_DATE_TIME を使用して、値を逆シリアル化およびシリアル化します。 [詳細情報](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**リテラル表現**

```json
date("<dateOnly in ISO-8601 format>")  
```

**一**

```json
date("2021-02-19")
```

## dateTimeOnly{#date-time-only}

**つい**

タイムゾーンなしで日付時刻を表します。この場合、年-月-日 ~ 秒-分-秒-秒のように表示されます。

JSON 形式: String。

この場合、タイムゾーンは保存または表示されません。 その代わりに、誕生日に使用されている日付の説明が、壁掛け時計の現地時刻とともに表示されます。

オフセットやタイムゾーンなどの追加情報を使用せずに、タイムライン上のインスタントを表すことはできません。

ToDateTimeOnly 関数にカプセル化することができます。

シリアル化フォーマット: ISO-8601 拡張オフセット日付/時刻フォーマット。

DateTimeFormatter ISO_LOCAL_DATE_TIME を使用して、値を逆シリアル化およびシリアル化します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**リテラル表現**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**例**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**つい**

タイムゾーンも考慮する日時定数。 UTC を基準として日時を指定することもできます。

これは、オフセットの追加情報を使用して表示することができます。 これは、特定の場所にある世界中の特定の「モーメント」を表現する方法の1つです。

JSON 形式: String。

ToDateTime 関数にカプセル化することができます。

シリアル化フォーマット: ISO-8601 拡張オフセット日付/時刻フォーマット。

DateTimeFormatter ISO_OFFSET_DATE_TIME を使用して、値を逆シリアル化およびシリアル化します。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

エポック値を指定して整数を渡すこともできます。 [詳細を読む](https://www.epochconverter.com)

タイムゾーンは、オフセットまたはタイムゾーンコード (例: 欧州、パリ、Z-意味 UTC) で指定できます。

**リテラル表現**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**例**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## 持続 {#duration}

**つい**

「34.5 秒」のように、時刻を表します。 ここでは、数または量をミリ秒単位でモデル化します。

サポートされているテンポラルの単位は、ミリ秒、秒、分、時、時刻は24時間に相当します。 年と月は、固定された時間ではないので、サポートされません。

JSON 形式: String。

ToDuration 関数にカプセル化する必要があります。

シリアル化フォーマット: タイムゾーン ID を逆シリアル化するために、java 関数 java 関数が使用されています。

Duration。 parse: 受け入れられるフォーマットは、ISO-8601 duration フォーマットの PnDTnHnMn に基づいています。この値は、24時間と正確に一致しています。 [詳細情報](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**リテラル表現**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**一**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## 一連 {#list}

**つい**

コンマで区切られた式のリスト。区切り文字として角かっこを使用します。

ポリモーフィズムはサポートされていないので、リストに含まれるすべての式は同じ型である必要があります。

**リテラル表現**

```json
[<expression>, <expression>, ... ]
```

**一**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```

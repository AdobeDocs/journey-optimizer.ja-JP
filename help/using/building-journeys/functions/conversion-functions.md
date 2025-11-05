---
product: journey optimizer
title: コンバージョン関数
description: コンバージョン関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: コンバージョン，関数，式，ジャーニー，タイプ，キャスト
version: Journey Orchestration
source-git-commit: 7d75abf6b428becc8b535a63421e85cca417daac
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 87%

---

# コンバージョン関数 {#conversion-functions}

コンバージョン関数を使用すると、ジャーニー式内のデータをタイプ間で変換できます。 これらの関数は、様々なデータソースや操作を操作する際に、データの互換性と適切なタイプの処理を確保するために不可欠です。

次の必要がある場合は、変換関数を使用します。

* 文字列値を数値、ブール値または日付型に変換する
* 日付と時刻を異なる形式と表示域に変換する
* 整数タイプと小数タイプの間で数値をキャストします
* 比較および操作のタイプの互換性の確保
* 異なるタイプ形式を持つ可能性のある外部ソースからのデータを処理します

各コンバージョン関数は、型固有のルールとエッジケースを自動的に処理するので、ジャーニー式でのデータ変換の信頼性と予測可能性が向上します。

## toBool {#toBool}

引数の値をタイプに応じてブール値に変換します。

* 文字列から変換する場合：文字列値をブール値として変換します。文字列値が「true」の場合は true、それ以外の場合は false を返します。
* 数値から変換する場合：数値が 0 に等しくない場合は true 、それ以外の場合は false を返します。

+++構文

`toBool(<parameter>)`

+++

+++パラメーター

* 小数
* ブール値
* 文字列
* 整数

+++

+++シグネチャと戻り値のタイプ

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

ブール値を返します。

+++

+++例

`toBool("true")`

`toBool(1)`

true を返します。

`toBool("this is not a boolean")`

false を返します。

+++

## toDateOnly {#toDateOnly}

引数を dateOnly 型の値に変換します。データタイプについて詳しくは、この[節](../expression/data-types.md)を参照してください。

+++構文

`toDateOnly(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 「YYYY-MM-DD」（XDM 形式）としての日付の文字列表現。ISO-8601 形式もサポートしています。**full-date** の部分に限り考慮されます（[RFC 3339、セクション 5.6](https://www.rfc-editor.org/rfc/rfc3339#section-5.6) | 文字列 |
| 日時 | 日時 |
| タイムゾーンを含まない日時 | 日時のみ |
| エポックのミリ秒単位の整数値 | 整数 |

+++

+++シグネチャと戻り値のタイプ

`toDateOnly(<dateTime>)`

`toDateOnly(<dateTimeOnly>)`

`toDateOnly(<string>)`

`toDateOnly(<integer>, <integer>, <integer>)`

dateOnly 型の値を返します。

+++

+++例

`toDateOnly("2023-08-18")`

`toDateOnly("2023-08-18T00:00:00.000Z")`

`toDateOnly("2023-08-18T00:00:00")`

すべて、2023/08/18 を表す dateOnly オブジェクトを返します。

`toDateOnly(#{ExperiencePlatform.ProfileFieldGroup.person.birthDate})`

dateOnly を返します。

+++

## toDateTime {#toDateTime}

パラメーターをタイプに応じて日時値に変換します。

+++構文

`toDateTime(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601 形式の日時 | 文字列 |
| タイムゾーン ID | 文字列 |
| タイムゾーンを含まない日時 | 日時のみ |
| エポックのミリ秒単位の整数値 | 整数 |

+++

+++シグネチャと戻り値のタイプ

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

**dateTime** を返します。

+++

+++例

`toDateTime ("2023-08-18T23:17:59.123Z")`

2023-08-18T23:17:59.123Z を返します

`toDateTime(toDateTimeOnly("UTC", "2023-08-18T23:17:59.123"))`

2023-08-18T23:17:59.123Z を返します

`toDateTime(1560762190189)`

2023-06-17T09:03:10.189Z を返します

+++

>[!NOTE]
>
>タイムゾーン ID は文字列定数である必要があります。フィールド参照や式は使用できません。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## toDateTimeOnly {#toDateTimeOnly}

引数値を日時のみの値に変換します。

+++構文

`toDateTimeOnly(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601 形式つまり「YYYY-MM-DD」形式（XDM 日付形式）の日時 | 文字列 |
| 日時 | 日時 |

+++

+++シグネチャと戻り値のタイプ

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`

タイムゾーンを無視して日時を返します。

+++

+++例

`toDateTimeOnly ("2023-08-18")`

2023-08-18T00:00:00.000 を表す日時を返します

`toDateTimeOnly(now())`

+++

## toDecimal {#toDecimal}

引数の値をタイプに応じて小数値に変換します。

+++構文

`toDecimal(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を小数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |
| 整数 | 小数に変換します（例：1 は 1.0 になります） |

+++

+++シグネチャと戻り値のタイプ

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

+++

+++例

`toDecimal("4.0")`

4.0 を返します。

+++

## toDuration {#toDuration}

引数の値を期間に変換します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

+++構文

`toDuration(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601 の期間形式 PnDTnHnMn.nS に基づく形式（日数は正確に 24 時間と見なされます） |
| 整数 | ミリ秒数 |

文字列式の場合：指定できる形式は、ISO-8601 期間形式 PnDTnHnMn.nS に基づいたもので、1 日は正確に 24 時間と見なされます。

文字列は、ASCII の負または正の記号で表されるオプションの符号で始まります。負の場合は、期間全体が負の値になります。ASCII 文字「P」が次に現れ、大文字または小文字で表されます。その後に 4 つのセクションがあり、それぞれが数値とサフィックスで構成されます。各セクションには、日、時間、分および秒を示す「D」、「H」、「M」および「S」の ASCII サフィックスがあります（大文字でも小文字でもかまいません）。サフィックスは、順序に従って現れる必要があります。ASCII 文字「T」は、時、分、秒のセクションの最初の出現箇所（存在する場合）より前に記述する必要があります。4 つのセクションのうち少なくとも 1 つが存在し、「T」が存在する場合は、「T」の後に少なくとも 1 つのセクションが存在する必要があります。各セクションの数値部分は、1 つ以上の ASCII 数字で構成される必要があります。数字の接頭辞は、ASCII の負または正の符号を付けてもかまいません。日数、時間数および分数は long 型の値に解析される必要があります。秒数は long 型の値（オプションで小数を含む）に解析される必要があります。小数点はドットまたはコンマです。小数部は 0～9 桁まで可能です。

+++

+++シグネチャと戻り値のタイプ

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

+++

+++例

`toDuration("PT10H")`

10 時間の期間を返します。

`toDuration("PT4S")`

4 秒の期間を返します。

`toDuration(4000)`

4 秒の期間を返します。

+++

## toInteger {#toInteger}

引数の値を整数に変換します。

+++構文

`toInteger(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を整数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| 小数 | 小数部を削除して整数に変換します（例：1.5 は 1 になります） |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |

+++

+++シグネチャと戻り値のタイプ

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

+++

+++例

`toInteger("4")`

4 を返します。

+++

## toString {#toString}

引数の値を、タイプに応じて文字列値に変換します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

+++構文

`toString(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 |
|--- |--- |
| 日時 | 日付を UTC 日付フォーマットに変換します |
| 日時のみ | 日付を UTC 日付フォーマットに変換します |
| 期間 | 対応するミリ秒数の文字列に変換します |
| 整数 | 値の文字列表現に変換します（1 は &quot;1&quot; になります） |
| 小数 | 値の文字列表現に変換します（1.5 は &quot;1.5&quot; になります） |
| ブール値 | ブール値を true の場合は「true」、false の場合は「false」に変換します |

+++

+++シグネチャと戻り値のタイプ

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

文字列を返します。

+++

+++例

`toString(4)`

「4」を返します。

`toString(#{ExperiencePlatform.test_date.person.birthDate}))`

例えば「2023/08/18」のように、指定された dateOnly フィールド（XDM 日付フィールド）の文字列表現を返します。

`toString(toDuration(1520))`

「PT1.52S」を返します。

+++


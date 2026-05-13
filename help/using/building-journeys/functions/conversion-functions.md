---
product: journey optimizer
title: コンバージョン関数
description: コンバージョン関数について詳しく見る
feature: Journeys
role: Developer
level: Experienced
keywords: 変換，関数，式，ジャーニー，タイプ，キャスト
version: Journey Orchestration
exl-id: f1267c9e-200c-43ae-8b98-3c5951a2f2d7
TQID: https://experienceleague.adobe.com/CoDxFCoJOwwmPHOG6pxMxmSASUbATkUoguBjNkrMKeQ
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d998adac-2f81-400b-a669-d07bb196e4eb
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 1271
ht-degree: 0%

---

# コンバージョン関数 {#conversion-functions}

変換関数を使用すると、ジャーニー式の中で、あるタイプから別のタイプにデータを変換できます。 これらの機能は、異なるデータソースや操作を操作する際のデータの互換性と適切なタイプ処理を確保するために不可欠です。

次のような場合に変換関数を使用します。

* 文字列値を数値、ブール値、または日付型に変換（[toInteger](#toInteger)、[toDecimal](#toDecimal)、[toBool](#toBool)）
* 異なる形式と表現間の日付と時刻の変換（[toDateTime](#toDateTime)、[toDateTimeOnly](#toDateTimeOnly)、[toDateOnly](#toDateOnly)）
* 整数と小数点型の間に数値をキャストします（[toInteger](#toInteger)、[toDecimal](#toDecimal)）
* 値を文字列形式（[toString](#toString)）または期間（[toDuration](#toDuration)）に変換
* 比較と操作の互換性を確保
* 異なるタイプの形式を持つ外部ソースからのデータを処理する

各変換関数は、タイプ固有のルールとエッジケースを自動的に処理し、ジャーニーの表現でデータ変換をより信頼性が高く、予測可能にします。

## クイックリファレンス {#quick-reference}

| 目標 | 関数 |
|------|----------|
| 文字列またはエポックを&#x200B;**のタイムゾーンを持つ**&#x200B;日付に変換 | [toDateTime](#toDateTime) |
| 文字列または日付を&#x200B;**タイムゾーンのない**&#x200B;日時に変換します | [toDateTimeOnly](#toDateTimeOnly) |
| 日付のみを抽出（年 – 月 – 日、時間なし） | [toDateOnly](#toDateOnly) |
| 整数に変換 | [toInteger](#toInteger) |
| 10進数に変換 | [toDecimal](#toDecimal) |
| true/falseに変換 | [toBool](#toBool) |
| 任意の値を文字列に変換 | [toString](#toString) |
| デュレーションに変換（ISO-8601、PT10Hなど） | [toDuration](#toDuration) |

>[!TIP]
>
>**toDateTime vs. toDateTimeOnly:** タイムゾーンが重要な場合（例：メッセージのスケジュール設定、地域間のイベントタイムスタンプの比較）に`toDateTime`を使用します。 ローカルの日時のみが関連し、タイムゾーンを無視できる場合（条件でカレンダーの日付を比較する場合など）は、`toDateTimeOnly`を使用します。

## よくある落とし穴 {#pitfalls}

* **タイムゾーンは文字列定数**&#x200B;である必要があります。`toDateTime`のタイムゾーン引数は、フィールド参照または動的式にすることはできません。 `"UTC"`や`"Europe/Paris"`などのリテラル文字列を常に渡します。
* 文字列の入力に必要な&#x200B;**ISO-8601形式** – 文字列を`toDateTime`または`toDateTimeOnly`に渡す場合は、ISO-8601形式（例：`"2023-08-18T23:17:59.123Z"`）に従っていることを確認してください。 形式が正しくない文字列は、エラーなしでnullを返します。
* **エポック値はミリ秒です** — `toDateTime(1560762190189)`はミリ秒を想定しています。 ソースがUnix タイムスタンプを秒単位で提供する場合は、最初に1000を掛けます（例：`toDateTime(myField * 1000)`）。
* **toBool with unexpected strings** — `toBool`は、文字列値が正確に`"true"`の場合にのみ`true`を返します。 その他の文字列（`"1"`、`"yes"`、`"TRUE"`を含む）は`false`を返します。

## toBool {#toBool}

引数の値を型に応じてブール値に変換します。

* 文字列から：文字列値をブール値として変換します。文字列値が「true」の場合は「true」、それ以外の場合は「false」とします
* 数値から：数値が0でない場合はtrue、それ以外の場合はfalse

+++構文

`toBool(<parameter>)`

+++

+++パラメーター

* 小数
* ブーリアン
* 文字列
* 整数

+++

+++署名と返される型

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

ブール値を返します。

+++

+++例

`toBool("true")`

`toBool(1)`

trueを返します。

`toBool("this is not a boolean")`

falseを返します。

+++

## toDateOnly {#toDateOnly}

引数をdateOnly タイプの値に変換します。 データ型について詳しくは、この[ セクション ](../expression/data-types.md)を参照してください。

+++構文

`toDateOnly(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日付の文字列表現を「YYYY-MM-DD」（XDM形式）として指定します。 ISO-8601形式もサポートしています：**フルデイト**&#x200B;部分のみが考慮されます（[RFC 3339、セクション 5.6](https://www.rfc-editor.org/rfc/rfc3339#section-5.6)を参照）。 | 文字列 |
| 日時 | dateTime |
| タイムゾーンのない日時 | dateTimeOnly |
| ミリ秒単位のエポックの整数値 | 整数 |

+++

+++署名と返される型

`toDateOnly(<dateTime>)`

`toDateOnly(<dateTimeOnly>)`

`toDateOnly(<string>)`

`toDateOnly(<integer>, <integer>, <integer>)`

dateOnly タイプ値を返します。

+++

+++例

`toDateOnly("2023-08-18")`

`toDateOnly("2023-08-18T00:00:00.000Z")`

`toDateOnly("2023-08-18T00:00:00")`

allは、2023-08-18を表すdateOnly オブジェクトを返します。

`toDateOnly(#{ExperiencePlatform.ProfileFieldGroup.person.birthDate})`

dateOnlyを返します。

+++

## toDateTime {#toDateTime}

パラメーターをタイプに応じて日付時刻値に変換します。

+++構文

`toDateTime(<parameters>)`

+++

+++パラメーター

| パラメーター | 効果 |
|--- |--- |
| 文字列 | 日時（ISO-8601形式）。 タイムゾーン情報を含む日時の文字列表現 |
| 文字列 | タイムゾーン id。 タイムゾーン識別子（例：「UTC」、「Europe/Paris」） |
| dateOnly | タイムゾーンのない日付を表し、年月の日と見なされます |
| dateTimeOnly | タイムゾーンのない日時を表し、year-month-day-hour-minute-second-millisecondsと見なされます |
| 整数 | ミリ秒単位のエポックの整数値 |

+++

+++署名と返される型

`toDateTime(<string>)`

`toDateTime(<string>, <dateOnly>)`

`toDateTime(<string>, <dateTimeOnly>)`

`toDateTime(<integer>)`

**dateTime**&#x200B;を返します。

+++

+++例

`toDateTime("2023-08-18T23:17:59.123Z")`

2023-08-18T23:17:59.123Zを返します

ISO-8601文字列には、タイムゾーン情報が既に含まれています。

`toDateTime("Europe/Paris", toDateOnly("2023-08-18"))`

2023-08-18T00:00:00.000+02:00を返します

これにより、タイムゾーンと日付のみの値を組み合わせてdateTimeが作成されます。 時刻は、指定されたタイムゾーンの午前0時（00:00:00）に設定されます。

`toDateTime("UTC", toDateTimeOnly("2023-08-18T23:17:59.123"))`

2023-08-18T23:17:59.123Zを返します

これにより、（タイムゾーン情報を持たない） dateTimeOnly値にタイムゾーンを適用してdateTimeが作成されます。

`toDateTime(1560762190189)`

2019-06-17T09:03:10.189Zを返します

Unix タイムスタンプをミリ秒単位でdateTime値に変換します。

+++

>[!NOTE]
>
>タイムゾーン IDは文字列定数である必要があります。 フィールド参照または式にすることはできません。 データ型について詳しくは、[このページ ](../expression/data-types.md)を参照してください。

## toDateTimeOnly {#toDateTimeOnly}

引数の値を日付時間のみの値に変換します。

+++構文

`toDateTimeOnly(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601または「YYYY-MM-DD」形式の日付時刻（XDM日付形式） | 文字列 |
| 日時 | dateTime |

+++

+++署名と返される型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`

タイムゾーンを考慮せずに日時を返します。

+++

+++例

`toDateTimeOnly ("2023-08-18")`

2023-08-18T00:00:00.000を表すdateTimeを返します

`toDateTimeOnly(now())`

+++

## toDecimal {#toDecimal}

引数の値をタイプに応じて10進数値に変換します。

+++構文

`toDecimal(<parameter>)`

+++

+++パラメーター

| パラメーター | 効果 |
|--- |--- |
| 文字列 | 文字列値を10進数に変換します |
| dateTime | 日付をミリ秒（エポックミリ秒）として変換します |
| ブーリアン | ブール値をtrueの場合は1、falseの場合は0に変換します |
| 整数 | 10進数に変換します（例：1は1.0になります）。 |

+++

+++署名と返される型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

10進数を返します。

+++

+++例

`toDecimal("4.0")`

4.0を返します。

+++

## toDuration {#toDuration}

引数の値をデュレーションに変換します。 データ型について詳しくは、[このページ ](../expression/data-types.md)を参照してください。

+++構文

`toDuration(<parameter>)`

+++

+++パラメーター

| パラメーター | 効果 |
|--- |--- |
| 文字列 | ISO-8601期間形式PnDTnHnMn.nSに基づく形式で、日数は正確に24時間と見なされます |
| 整数 | ミリ秒数 |

文字列式の場合：受け入れられる形式は、ISO-8601の期間形式PnDTnHnMn.nSに基づいており、日数は正確に24時間と見なされます。

文字列は、ASCIIの負または正の記号で示されるオプションの記号で始まります。 負の場合、全期間が負になります。 ASCII文字「P」は、大文字または小文字の次の文字です。 次に、数字と接尾辞で構成される4つのセクションがあります。 このセクションには、大文字と小文字の両方で使用できる、日、時間、分、秒のASCIIの接尾辞が「D」、「H」、「M」および「S」に設定されています。 接尾辞は順番に作成する必要があります。 ASCII文字「T」は、最初に発生した場合は、1時間、分、または2番目のセクションの前に発生する必要があります。 4つのセクションのうち少なくとも1つは存在する必要があり、「T」が存在する場合は、「T」の後に少なくとも1つのセクションが存在する必要があります。 各セクションの番号部分は、1つ以上のASCII数字で構成されている必要があります。 数字の先頭にはASCIIの負または正の記号を使用できます。 日数、時間、分数を解析する必要があります。 秒数は、オプションの分数とともに解析する必要があります。 小数点は、ドットまたはコンマのいずれかです。 分数パーツは、0から9桁までです。

+++

+++署名と返されたタイプ

`toDuration(<string>)`

`toDuration(<integer>)`

期間を返します。

+++

+++例

`toDuration("PT10H")`

10時間の期間を返します。

`toDuration("PT4S")`

4sのデュレーションを返します。

`toDuration(4000)`

4sのデュレーションを返します。

+++

## toInteger {#toInteger}

引数の値を整数に変換します。

+++構文

`toInteger(<parameter>)`

+++

+++パラメーター

| パラメーター | 効果 |
|--- |--- |
| 文字列 | 文字列値を整数に変換します |
| dateTime | 日付をミリ秒（エポックミリ秒）として変換します |
| 小数 | 10進数を削除して整数に変換します（例：1.5は1になります）。 |
| ブーリアン | ブール値をtrueの場合は1、falseの場合は0に変換します |

+++

+++署名と返されたタイプ

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

+++

+++例

`toInteger("4")`

4を返します。

+++

## toString {#toString}

引数の値を、タイプに応じて文字列値に変換します。 データ型について詳しくは、[このページ ](../expression/data-types.md)を参照してください。

+++構文

`toString(<parameter>)`

+++

+++パラメーター

| パラメーター | 効果 |
|--- |--- |
| dateTime | 日付をUTC日付形式で変換します |
| dateTimeOnly | 日付をUTC日付形式で変換します |
| 期間 | 対応するミリ秒数に変換します |
| 整数 | 値の文字列表現に変換します（1は「1」になります） |
| 小数 | 値の文字列表現に変換します（1.5は「1.5」になります）。 |
| ブーリアン | ブール値をtrueの場合は「true」、falseの場合は「false」に変換します |

+++

+++署名と返されたタイプ

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

指定されたdateOnly フィールド（XDM日付フィールド）の文字列表現を返します（例：「2023-08-18」）。

`toString(toDuration(1520))`

「PT1.52S」を返します。

+++

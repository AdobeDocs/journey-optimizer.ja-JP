---
product: journey optimizer
title: コンバージョン関数
description: コンバージョン関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: コンバージョン, 関数, 式, ジャーニー, タイプ, キャスト
version: Journey Orchestration
exl-id: f1267c9e-200c-43ae-8b98-3c5951a2f2d7
TQID: https://experienceleague.adobe.com/CoDxFCoJOwwmPHOG6pxMxmSASUbATkUoguBjNkrMKeQ
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
subfeature_v2: []
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 1723
ht-degree: 62%

---

# コンバージョン関数 {#conversion-functions}

コンバージョン関数を使用すると、ジャーニー式内でデータをあるタイプから別のタイプに変換できます。 これらの関数は、様々なデータソースや操作で作業する際に、データの互換性と適切なタイプの処理を確保するために不可欠です。

コンバージョン関数は、次の操作が必要な場合に使用します。

* 文字列値を数値、ブール値、日付タイプに変換（[toInteger](#toInteger)、[toDecimal](#toDecimal)、[toBool](#toBool)）
* 日付と時刻を異なる形式と表示域の間で変換（[toDateTime](#toDateTime)、[toDateTimeOnly](#toDateTimeOnly)、[toDateOnly](#toDateOnly)）
* 数値を整数タイプと小数タイプの間でキャスト（[toInteger](#toInteger)、[toDecimal](#toDecimal)）
* 値を文字列形式（[toString](#toString)）または期間（[toDuration](#toDuration)）に変換
* 比較や演算のタイプの互換性を確保
* 異なるタイプ形式を持つ場合がある外部ソースからのデータを処理

各コンバージョン関数は、タイプ固有のルールとエッジケースを自動的に処理するので、ジャーニー式でのデータ変換の信頼性と予測可能性が向上します。

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

引数を dateOnly 型の値に変換します。 データタイプについて詳しくは、この[節](../expression/data-types.md)を参照してください。

+++構文

`toDateOnly(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 「YYYY-MM-DD」（XDM 形式）としての日付の文字列表現。 ISO-8601 形式もサポートしています。**full-date** の部分に限り考慮されます（[RFC 3339、セクション 5.6](https://www.rfc-editor.org/rfc/rfc3339#section-5.6) | 文字列 |
| 日時 | 日時 |
| タイムゾーンを含まない日時 | dateTimeOnly |
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

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601 形式の日時。 タイムゾーン情報を含む日時の文字列表現 |
| 文字列 | タイムゾーン ID。 タイムゾーン識別子（例：「UTC」、「ヨーロッパ／パリ」） |
| dateOnly | タイムゾーンを含まずに日付を表し、年-月-日として表示されます |
| dateTimeOnly | タイムゾーンのない日時を表し、年-月-日-時間-分-秒-ミリ秒と表示されます |
| 整数 | エポックのミリ秒単位の整数値 |

+++

+++シグネチャと戻り値のタイプ

`toDateTime(<string>)`

`toDateTime(<string>, <dateOnly>)`

`toDateTime(<string>, <dateTimeOnly>)`

`toDateTime(<integer>)`

**dateTime** を返します。

+++

+++例

`toDateTime("2023-08-18T23:17:59.123Z")`

2023-08-18T23:17:59.123Z を返します

ISO-8601 文字列には、既にタイムゾーン情報が含まれています。

`toDateTime("Europe/Paris", toDateOnly("2023-08-18"))`

2023-08-18T00:00:00.000+02:00 を返します

タイムゾーンと日付のみの値を組み合わせて日時を作成します。 時間は、指定されたタイムゾーンの午前 0 時（00:00:00）に設定されます。

`toDateTime("UTC", toDateTimeOnly("2023-08-18T23:17:59.123"))`

2023-08-18T23:17:59.123Z を返します

（タイムゾーン情報を持たない）dateTimeOnly 値にタイムゾーンを適用して日時を作成します。

`toDateTime(1560762190189)`

2019-06-17T09:03:10.189Z を返します。

Unix タイムスタンプをミリ秒単位で dateTime 値に変換します。

+++

>[!NOTE]
>
>タイムゾーン ID は文字列定数である必要があります。 フィールド参照や式は使用できません。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

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
| 整数 | 10進数に変換します（例：1は1.0になります）。 |

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

引数の値を期間に変換します。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

+++構文

`toDuration(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | ISO-8601 の期間形式 PnDTnHnMn.nS に基づく形式（日数は正確に 24 時間と見なされます） |
| 整数 | ミリ秒数 |

文字列式の場合：指定できる形式は、ISO-8601 期間形式 PnDTnHnMn.nS に基づいたもので、1 日は正確に 24 時間と見なされます。

文字列は、ASCII の負または正の記号で表されるオプションの符号で始まります。 負の場合は、期間全体が負の値になります。 ASCII 文字「P」が次に現れ、大文字または小文字で表されます。 その後に 4 つのセクションがあり、それぞれが数値とサフィックスで構成されます。 各セクションには、日、時間、分および秒を示す「D」、「H」、「M」および「S」の ASCII サフィックスがあります（大文字でも小文字でもかまいません）。 サフィックスは、順序に従って現れる必要があります。 ASCII 文字「T」は、時、分、秒のセクションの最初の出現箇所（存在する場合）より前に記述する必要があります。 4 つのセクションのうち少なくとも 1 つが存在し、「T」が存在する場合は、「T」の後に少なくとも 1 つのセクションが存在する必要があります。 各セクションの数値部分は、1 つ以上の ASCII 数字で構成される必要があります。 数字の接頭辞は、ASCII の負または正の符号を付けてもかまいません。 日数、時間数および分数は long 型の値に解析される必要があります。 秒数は long 型の値（オプションで小数を含む）に解析される必要があります。 小数点はドットまたはコンマです。 小数部は 0～9 桁まで可能です。

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

引数の値を、タイプに応じて文字列値に変換します。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

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

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、AJO ジャーニー式のすべてのコンバージョン関数について説明します。文字列、整数、小数、ブール値、日付、日時、期間などの型間で値を変換する方法を説明します。

**インテント：**
* `toDateTime`を使用して、文字列またはエポック整数をタイムゾーンに応じた日時に変換します
* `toDateTimeOnly`を使用して、文字列または日時をタイムゾーンのない日時に変換します
* `toDateOnly`を使用して、文字列または日時から日付のみの値（year-month-day）を抽出します
* `toInteger`、`toDecimal`、または`toBool`を使用して、整数、小数、またはブール値に値をキャストします
* `toString`を使用して、任意の値を文字列表現にシリアライズします
* `toDuration`を使用して、文字列またはミリ秒単位の整数をデュレーションに変換します

**用語集：**
* **dateTime**: タイムゾーンオフセット情報&#x200B;*（製品固有）*&#x200B;を含む日時の値
* **dateTimeOnly**: タイムゾーン情報のない日時の値&#x200B;*（製品固有）*
* **dateOnly**：時間コンポーネント *（製品固有）*&#x200B;のない年 – 月 – 日を表す日付値
* **duration**: ISO-8601形式で表現された期間（例：PT10H） *（製品固有）*
* **エポックミリ秒**: 1970-01-01T00:00:00Zからのミリ秒単位で表されるUnix タイムスタンプ

**ガードレール：**
* `toDateTime`のタイムゾーン引数は文字列定数である必要があります。フィールド参照と動的式は使用できません
* `toDateTime`および`toDateTimeOnly`への文字列入力はISO-8601形式に従う必要があります。形式が正しくない文字列はエラーなしでnullを返します
* エポック整数を持つ`toDateTime`にはミリ秒が必要です。秒ベースのタイムスタンプに1000を掛けて渡します
* `toBool`は正確な文字列`"true"`に対してのみ`true`を返します。`"1"`、`"yes"`、`"TRUE"`などの文字列は`false`を返します

**用語：**
* 正規名：変換関数 – Acronym: none – 変種：型鋳造関数、型変換関数
* 同義語：&quot;toDateTime&quot; = &quot;convert to datetime with timezone&quot;; &quot;toDateTimeOnly&quot; = &quot;convert to datetime without timezone&quot;
* 混乱しないでください：&quot;toDateTime&quot; （timezone対応） ≠ &quot;toDateTimeOnly&quot; （タイムゾーンなし）
* 「toDateOnly」（日付のみ、時刻なし）≠「toDateTime」（日付と時刻とタイムゾーン）は混同しないでください。

**FAQ:**
* **Q: `toDateTime`と`toDateTimeOnly`の比較はいつから使用すべきですか？** — タイムゾーン情報が重要な場合（スケジューリングや地域の比較など）は`toDateTime`を使用します。ローカルの日時のみが関連し、タイムゾーンを無視できる場合は`toDateTimeOnly`を使用します。
* **Q: `toBool("TRUE")`がfalseを返すのはなぜですか？** — `toBool`は小文字の文字列`"true"`のみを認識します。`"TRUE"`または`"yes"`を含むその他すべての文字列値はfalseを返します。
* **Q: Unix タイムスタンプを秒単位でdateTimeに変換する方法を教えてください。** — ミリ秒を取得するには、秒数に1000を掛け、`toDateTime` （例：`toDateTime(myField * 1000)`）に渡します。
* **Q: `toDateTime`のタイムゾーンをプロファイル属性から読み取ることはできますか？**  – いいえ、タイムゾーン IDは文字列定数である必要があります。フィールド参照と式はサポートされていません。
* **Q: `toDuration`が文字列として受け入れる形式は何ですか？** — ISO-8601期間の形式（例：`"PT10H"` 10時間、または`"P1DT2H"` 1日と2時間）。

+++

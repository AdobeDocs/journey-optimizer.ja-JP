---
title: 日時関数ライブラリ
description: 日時関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: edc040de-dfb3-4ebc-91b4-239e10c2260b
source-git-commit: 3eab04f28b1daab556c4b4395d67f28d292fc52b
workflow-type: ht
source-wordcount: '1034'
ht-degree: 100%

---

# 日時関数{#date-time}

日時関数を使用すると、Journey Optimizer 内の値に対して日時操作を実行できます。

## 日数を追加 {#add-days}

`addDays` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された日数で調整します。

**構文**

```sql
{%= addDays(date, number) %}
```

+++例

* 入力：`{%= addDays(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* 出力：`2024-11-11T17:19:51Z`

+++

## 時間数を追加 {#add-hours}

`addHours` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された時間数で調整します。

**構文**

```sql
{%= addHours(date, number) %}
```

+++例

* 入力：`{%= addHours(stringToDate("2024-11-01T17:19:51Z"),1) %}`
* 出力：`2024-11-01T18:19:51Z`

+++

## 分数を追加 {#add-minutes}

`addMinutes` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された分数で調整します

**構文**

```sql
{%= addMinutes(date, number) %}
```

+++例

* 入力：`{%= addMinutes(stringToDate("2024-11-01T17:59:51Z"),10) %}`
* 出力：`2024-11-01T18:09:51Z`

+++

## 月数を追加 {#add-months}

`addMonths` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された月数で調整します。

**構文**

```sql
{%= addMonths(date, number) %}
```

+++例

* 入力：`{%= addMonths(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* 出力：`2025-01-01T17:19:51Z`

+++

## 秒数を追加 {#add-seconds}

`addSeconds` は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された秒数で調整します。

**構文**

```sql
{%= addSeconds(date, number) %}
```

+++例

* 入力：`{%= addSeconds(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* 出力：`2024-11-01T17:20:01Z`

+++

## 年数を追加 {#add-years}

`addYears` は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された年数で調整します。

**構文**

```sql
{%= addYears(date, number) %}
```

+++例

* 入力：`{%= addYears(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* 出力：`2026-11-01T17:19:51Z`

+++

## 経過時間{#age}

`age` 関数を使用すると、指定された日付からの経過時間を取得できます。

**構文**

```sql
 {%= age(datetime) %}
```

<!--
**Example**

The following operation gets the value of the identity map for the key `example@example.com`.

```sql
 {%= age(datetime) %}
```
-->

## 日数 {#age-days}

`ageInDays` 関数は、指定された日付を日数で、つまり指定された日付と現在の日付の間の経過日数を計算します。将来の日付の場合は負の数、過去の日付の場合は正の数になります。

**構文**

```sql
{%= ageInDays(date) %}
```

+++例

currentDate = 2025-01-07T12:17:10.720122+05:30（アジア／コルカタ）

* 入力：`{%= ageInDays(stringToDate("2025-01-01T17:19:51Z"))%}`
* 出力：`5`

+++

## 月数 {#age-months}

`ageInMonths` 関数は、指定された日付を月数で、つまり指定された日付と現在の日付の間の経過月数を計算します。将来の日付の場合は負の数、過去の日付の場合は正の数になります。

**構文**

```sql
{%= ageInMonths(date) %}
```

+++例

currentDate = 2025-01-07T12:22:46.993748+05:30（アジア／コルカタ）

* 入力：`{%=ageInMonths(stringToDate("2024-01-01T00:00:00Z"))%}`
* 出力：`12`

+++

## 日付を比較 {#compare-dates}

`compareDates` 関数は、最初の入力日付を他の入力日付と比較します。date1 が date2 と等しい場合は 0 を返し、date1 が date2 より前の場合は -1 を返し、date1 が date2 より後の場合は 1 を返します。

**構文**

```sql
{%= compareDates(date1, date2) %}
```

+++例

* 入力：`{%=compareDates(stringToDate("2024-12-02T00:00:00Z"), stringToDate("2024-12-03T00:00:00Z"))%}`
* 出力：`-1`

+++

## ZonedDateTime を変換 {#convert-zoned-date-time}

`convertZonedDateTime` 関数は、日時を指定されたタイムゾーンに変換します。

**構文**

```sql
{%= convertZonedDateTime(dateTime, timezone) %}
```

+++例

* 入力：`{%=convertZonedDateTime(stringToDate("2019-02-19T08:09:00Z"), "Asia/Tehran")%}`
* 出力：`2019-02-19T11:39+03:30[Asia/Tehran]`

+++

## 現在の時刻（ミリ秒）{#current-time}

`currentTimeInMillis` 関数を使用すると、現在の時刻をエポックミリ秒単位で取得できます。

**構文**

```sql
{%= currentTimeInMillis() %}
```

<!--
**Example**

The following operation gets all the keys for the map `identityMap`.

```sql
{%= keys(identityMap) %}
```
-->

## 日数の差異{#date-diff}

`dateDiff` 関数を使用すると、2 つの日付間の差異を日数単位で取得できます。

**構文**

```sql
{%= dateDiff(datetime,datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## ある月の日付 {#day-month}

`dayOfWeek` は、その月の日付を表す数値を返します。

**構文**

```sql
{%= dayOfMonth(datetime) %}
```

+++例

* 入力：`{%= dayOfMonth(stringToDate("2024-11-05T17:19:51Z")) %}`
* 出力：`5`

+++


## 曜日 {#day-week}

`dayOfWeek` 関数を使用すると、曜日を取得できます。

**構文**

```sql
{%= dayOfWeek(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## 年間通算日{#day-year}

`dayOfYear` 関数を使用すると、通日（1月1日からの通算日数）を取得できます。

**構文**

```sql
{%= dayOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## 秒数の差異 {#diff-seconds}

`diffInSeconds` 関数は、秒数単位で 2 つの日付間の差異を返します。

**構文**

```sql
{%= diffInSeconds(endDate, startDate) %}
```

+++例

* 入力：`{%=diffInSeconds(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T17:19:01Z"))%}`
* 出力：`50`

+++

## 時間数を抽出 {#extract-hours}

`extractHours` 関数は、指定されたタイムスタンプから時間コンポーネントを抽出します。

**構文**

```sql
{%= extractHours(date) %}
```

+++例

* 入力：`{%= extractHours(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`17`

+++

## 分数を抽出 {#extract-minutes}

`extractMinutes` 関数は、指定されたタイムスタンプから分コンポーネントを抽出します。

**構文**

```sql
{%= extractMinutes(date) %}
```

+++例

* 入力：`{%= extractMinute(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`19`

+++

## 月数を抽出 {#extract-months}

`extractMonth` 関数は、指定されたタイムスタンプから月コンポーネントを抽出します。

**構文**

```sql
{%= extractMonths(date) %}
```

+++例

* 入力：`{%=extractMonth(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`11`

+++

## 秒数を抽出 {#extract-seconds}

`extractSeconds` 関数は、指定されたタイムスタンプから秒コンポーネントを抽出します。

**構文**

```sql
{%= extractSeconds(date) %}
```

+++例

* 入力：`{%=extractSeconds(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`51`

+++

## 日付を書式設定{#format-date}

`formatDate` 関数を使用すると、日時値を書式設定できます。書式は、有効な Java DateTimeFormat パターンである必要があります。

**構文**

```sql
{%= formatDate(datetime, format) %}
```

上記の 1 番目の文字列が日付属性で、2 番目の値が日付の変換および表示方法を示します。

>[!NOTE]
>
> 日付パターンが無効な場合、日付は ISO 標準形式にフォールバックします。
>
> [Oracle ドキュメント](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}にまとめられている Java 日付書式設定関数を使用できます。

**例**

次の操作を実行すると、MM/DD/YY の形式で日付が返されます。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}
```

## 日付をロケールサポートの形式にする{#format-date-locale}

`formatDate` 関数は、日付と時刻の値を、目的のロケールなどの対応する言語に依存する表現にフォーマットするために使用します。書式は、有効な Java DateTimeFormat パターンである必要があります。

**構文**

```sql
{%= formatDate(datetime, format, locale) %}
```

最初の文字列は日付の属性で、2 番目の値はどのように日付を変換して表示するか、3 番目の値は文字列形式のロケールを表します。

>[!NOTE]
>
> 日付パターンが無効な場合、日付は ISO 標準形式にフォールバックします。
>
> [Oracle ドキュメント](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html)にまとめられている Java 日付書式設定関数を使用できます。
>
> [Oracle ドキュメント](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)と[サポートされているロケール](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html)にまとめられている書式設定と有効なロケールを使用できます。

**例**

次の操作を実行すると、MM/DD/YY 形式（ロケール：FRANCE）で日付が返されます。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/DD/YY", "fr_FR") %}
```

## CurrentZonedDateTime を取得 {#get-current-zoned-date-time}

`getCurrentZonedDateTime` 関数は、タイムゾーン情報を含む現在の日時を返します。

**構文**

```sql
{%= getCurrentZonedDateTime() %}
```

+++例

* 入力：`{%= getCurrentZonedDateTime() %}`
* 出力：`2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]`

+++

## 時間数の差異 {#hours-difference}

`diffInHours` 関数は、時間数単位で 2 つの日付間の差異を返します。

**構文**

```sql
{%= diffInHours(endDate, startDate) %}
```

+++例

* 入力：`{%= diffInHours(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T07:19:51Z"))%}`
* 出力：`10`

+++

## 分数の差異{#diff-minutes}

`diffInMinutes` 関数を使用すると、分数単位で 2 つの日付間の差異を返すことができます。

**構文**

```sql
{%= diffInMinutes(endDate, startDate) %}
```

+++例

* 入力：`{%= diffInMinutes(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T16:19:51Z"))%}`
* 出力：`60`

+++

## 月数の差異 {#months-difference}

`diffInMonths` 関数は、月数単位で 2 つの日付間の差異を返します

**構文**

```sql
{%= diffInMonths(endDate, startDate) %}
```

+++例

* 入力：`{%=diffInMonths(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-08-01T17:19:51Z"))%}`
* 出力：`3`

+++

## 日数を設定{#set-days}

`setDays` 関数を使用すると、指定された日時の日付を設定できます。

**構文**

```sql
{%= setDays(datetime, day) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## 時間を設定{#set-hours}

`setHours` 関数を使用すると、日時の時を設定できます。

**構文**

```sql
{%= setHours(datetime, hour) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## 日時に {#to-date-time}

`ToDateTime` 関数は、文字列を日付に変換します。無効な入力に対する出力として、エポック日付を返します。

**構文**

```sql
{%= toDateTime(string, string) %}
```

+++例

* 入力：`{%=toDateTime("2024-11-01T17:19:51Z")%}`
* 出力：`2024-11-01T17:19:51Z`

+++

## UTC に{#to-utc}

`toUTC` 関数を使用すると、日時を UTC に変換できます。

**構文**

```sql
{%= toUTC(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## 開始日に切り捨て {#truncate-day}

`truncateToStartOfDay` 関数を使用すると、指定された日時を、その日の始まり（時刻：00:00）に設定して変更できます。

**構文**

```sql
{%= truncateToStartOfDay(date) %}
```

+++例

* 入力：`{%= truncateToStartOfDay(stringToDate("2024-11-01T17:19:51Z")) %}`
* 出力：`2024-11-01T00:00Z`

+++

## truncateToStartOfQuarter {#truncate-quarter}

`truncateToStartOfQuarter` 関数を使用すると、日時を四半期の最初の日（例：1月1日、4月1日、7月1日、10月1日）の 00:00 に切り捨てることができます。

**構文**

```sql
{%= truncateToStartOfQuarter(dateTime) %}
```

+++例

* 入力：`{%=truncateToStartOfQuarter(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`2024-10-01T00:00Z`

+++

## truncateToStartOfWeek {#truncate-week}

`truncateToStartOfWeek` 関数は、指定された日時を、週の始まり（月曜日の 00:00）に設定して変更します。

**構文**

```sql
{%= truncateToStartOfWeek(dateTime) %}
```

+++例

* 入力：`truncateToStartOfWeek(stringToDate("2024-11-19T17:19:51Z"))%} // tuesday`
* 出力：`2024-11-18T00:00Z // monday`

+++

## truncateToStartOfYear {#truncate-year}

`truncateToStartOfYear` 関数を使用すると、指定された日時を、年の最初の日（1月1日）の 00:00 に切り捨てて変更できます。

**構文**

```sql
{%= truncateToStartOfYear(dateTime) %}
```

+++例

* 入力：`{%=truncateToStartOfYear(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`2024-01-01T00:00Z`

+++

## 年間通算週 {#week-of-year}

`weekOfYear` 関数を使用すると、年の週番号（何週目か）を取得できます。

**構文**

```sql
{%= weekOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## 年数の差異 {#diff-years}

`diffInYears` 関数を使用すると、年数単位で 2 つの日付間の差異を返すことができます。

**構文**

```sql
{%= diffInYears(endDate, startDate) %}: int
```

+++例

* 入力：`{%=diffInYears(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2019-10-01T17:19:51Z"))%}`
* 出力：`5`

+++

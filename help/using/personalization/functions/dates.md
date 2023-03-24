---
title: 日時関数ライブラリ
description: 日時関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: edc040de-dfb3-4ebc-91b4-239e10c2260b
source-git-commit: 2444d8fbe3a86feb0497d754b4f57f234fa29e49
workflow-type: ht
source-wordcount: '413'
ht-degree: 100%

---

# 日時関数{#date-time}

日時関数を使用すると、Journey Optimizer 内の値に対して日時操作を実行できます。

## 年齢{#age}

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

## 現在の時刻 (ミリ秒){#current-time}

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

## 日付の差異{#date-diff}

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


## 曜日{#day-week}

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

## 通日{#day-year}

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

## 日付をフォーマット{#format-date}

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
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/DD/YY") %}
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


## 年間通算週 (UTC){#week-of-year}

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
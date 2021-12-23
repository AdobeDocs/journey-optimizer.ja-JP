---
title: 日時関数ライブラリ
description: 日時関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: edc040de-dfb3-4ebc-91b4-239e10c2260b
source-git-commit: f0c5b42984b76fee005fe0c0e10312d47f9d10e8
workflow-type: ht
source-wordcount: '262'
ht-degree: 100%

---

# 日時関数{#date-time}

日時関数を使用すると、Journey Optimizer 内の値に対して日時操作を実行できます。

## age{#age}

`age` 関数を使用すると、指定された日付からの経過時間を取得できます。

**形式**

```sql
 {%= age(date) %}
```

<!--
**Example**

The following operation gets the value of the identity map for the key `example@example.com`.

```sql
 {%= age(date) %}
```
-->

## currentTimeInMillis{#current-time}

`currentTimeInMillis` 関数を使用すると、現在の時刻をエポックミリ秒単位で取得できます。

**形式**

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

## dateDiff{#date-diff}

`dateDiff` 関数を使用すると、2 つの日付間の差異を日数単位で取得できます。

**形式**

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


## dayOfWeek{#day-week}

`dayOfWeek` 関数を使用すると、曜日を取得できます。

**形式**

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

## dayOfYear{#day-year}

`dayOfYear` 関数を使用すると、通日（1月1日からの通算日数）を取得できます。

**形式**

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

## formatDate{#format-date}

`formatDate` 関数を使用すると、日時値を書式設定できます。書式は、有効な Java DateTimeFormat パターンである必要があります。

**形式**

```sql
{%= formatDate(date, format) %}
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

## setDays{#set-days}

`setDays` 関数を使用すると、指定された日時の日付を設定できます。

**形式**

```sql
{%= setDays(date, day) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## setHours{#set-hours}

`setHours` 関数を使用すると、日時の時を設定できます。

**形式**

```sql
{%= setHours(date, hour) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->


## toUTC{#to-utc}

`toUTC` 関数を使用すると、日時を UTC に変換できます。


**形式**

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


## weekOfYear{#week-of-year}

`weekOfYear` 関数を使用すると、年の週番号（何週目か）を取得できます。

**形式**

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

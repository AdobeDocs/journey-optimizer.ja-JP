---
title: 日付時間関数ライブラリ
description: 日付時間関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: edc040de-dfb3-4ebc-91b4-239e10c2260b
source-git-commit: f0c5b42984b76fee005fe0c0e10312d47f9d10e8
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 6%

---

# 日付時間関数{#date-time}

日付および時間関数は、Journey Optimizer内の値に対して日付と時間の操作を実行するために使用されます。

## 年齢{#age}

この `age` 関数は、指定された日付から年齢を取得するために使用されます。

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

## 現在の時間（ミリ秒）{#current-time}

この `currentTimeInMillis` 関数は、エポックミリ秒単位で現在の時間を取得するために使用されます。

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

## 日付の差異{#date-diff}

この `dateDiff` 関数は、2 つの日付間の差を日数で取得するために使用されます。

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


## 曜日{#day-week}

この `dayOfWeek` 関数は、曜日を取得するために使用されます。

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

## 年間通算日{#day-year}

この `dayOfYear` 関数は、年間通算日を取得するために使用されます。

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

## 日付の書式{#format-date}

この `formatDate` 関数は、日付時刻の値を書式設定するために使用されます。 形式は、有効な Java DateTimeFormat パターンである必要があります。

**形式**

```sql
{%= formatDate(date, format) %}
```

最初の文字列が日付属性で、2 番目の値が日付の変換方法と表示方法です。

>[!NOTE]
>
> 日付パターンが無効な場合、日付は ISO 標準形式にフォールバックします。
>
> Java の日付書式設定関数を要約として使用できます。 [oracle文書](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}

**例**

次の操作を実行すると、次の形式で日付が返されます。MM/DD/YY です。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/DD/YY") %}
```

## 日数を設定{#set-days}

この `setDays` 関数は、指定した日時の日付を設定するために使用されます。

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

## 時間を設定{#set-hours}

この `setHours` 関数は、日時の時間を設定するために使用されます。

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


## UTC に{#to-utc}

この `toUTC` 関数は、日時を UTC に変換するために使用されます。


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


## 週 (UTC){#week-of-year}

この `weekOfYear` 関数は、年の週を取得するために使用されます。

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

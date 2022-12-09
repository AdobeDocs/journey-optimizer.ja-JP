---
title: 日付時刻関数ライブラリ
description: 日付時刻関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: edc040de-dfb3-4ebc-91b4-239e10c2260b
source-git-commit: f06e1e03b3660be36b32437647a8329d0c0d296e
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---

# 日付時刻関数{#date-time}

日付時刻関数は、旅のオプティマイザー内の値に対して日付と時刻の操作を実行するために使用されます。

## 寿命{#age}

`age`この関数は、指定した日付から経過時間を取得するために使用されます。

**書式**

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

## 現在の時間 (ミリ秒){#current-time}

この関数は、 `currentTimeInMillis` 紀元ミリ秒単位で現在の時刻を取得するために使用されます。

**書式**

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

## 日付の違い{#date-diff}

この関数は、 `dateDiff` 2 つの日付間の差を日数で取得するために使用されます。

**書式**

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

この関数は、 `dayOfWeek` 曜日を取得するために使用されます。

**書式**

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

## 年通算日付{#day-year}

この関数は、 `dayOfYear` 通算日を取得するために使用されます。

**書式**

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

## 日付の形式{#format-date}

この関数は、 `formatDate` 日付と時刻の値をフォーマットするために使用されます。 フォーマットは、有効な Java DateTimeFormat パターンである必要があります。

**書式**

```sql
{%= formatDate(datetime, format) %}
```

ここでは、最初のストリングが日付属性であり、2番目のストリングは日付属性を使用して日付を変換し、表示する方法を指定します。

>[!NOTE]
>
> 日付パターンが無効な場合は、その日付が ISO 標準形式にフォールバックされます。
>
> Java 日付フォーマット関数は、Oracle ドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html) で要約 [ されるように使用することができます {_blank}

**一**

次の操作を実行すると、MM/DD/YY の形式で日付が返されます。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/DD/YY") %}
```

## 日の設定{#set-days}

`setDays`この関数を使用して、指定した日付と時刻に日付を設定します。

**書式**

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

## 時間の設定{#set-hours}

`setHours`この関数は、日時を設定するために使用されます。

**書式**

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


## UTC へ{#to-utc}

`toUTC`この関数は、datetime を UTC に変換するために使用されます。


**書式**

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


## 年の通算週{#week-of-year}

`weekOfYear`この関数を使用して、年の通算週を取得します。

**書式**

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
---
product: journey optimizer
title: 日付関数
description: 日付関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 日付、関数、式、ジャーニー、時間
version: Journey Orchestration
exl-id: 68c102c1-f1c7-44b7-893f-9a3b7e0854b6
TQID: https://experienceleague.adobe.com/C2Z5SufckUxCNf9TsloziZS-Q3KPzmgMVNGJGiwDQ08
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d998adac-2f81-400b-a669-d07bb196e4ebid: fe338112-e2ce-4876-8989-fc4d497613f1
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 834
ht-degree: 0%

---

# 日付関数 {#date-functions}

日付関数を使用すると、ジャーニー式の中で日付と時刻の値を操作して操作できます。 これらの関数は、カスタマージャーニーにおける時間ベースの条件、スケジュール設定、時間的計算に不可欠です。

必要に応じて、日付関数を使用します。

* 特定のタイムゾーン処理（[now](#now), [nowWithDelta](#nowWithDelta), [currentTimeInMillis](#currentTimeInMillis)）を使用して、現在の時間または日付を取得します
* 日付が特定の時間範囲内（[inLastDays](#inLastDays)、[inLastHours](#inLastHours)、[inLastMonths](#inLastMonths)、[inLastYears](#inLastYears)、[inNextDays](#inNextDays)、[inNextHours](#inNextHours)、[inNextMonths](#inNextMonths)、[inNextYears](#inNextYears)）に該当するかどうかを確認します
* 日付と時刻のコンポーネントを変更（[setHours](#setHours)、[setDays](#setDays)、[updateTimeZone](#updateTimeZone)）
* 時間ベースの計算と比較の実行
* 異なる時間形式と表現間の変換

日付関数は、時系列論理を正確に制御するため、特定の時間枠やスケジュールに応答する、時間に敏感なジャーニーパスと条件を作成することができます。

>[!NOTE]
>
>このページの関数は、ジャーニー式で使用できます。 `now()`などの一部の関数は、メールコンテンツのパーソナライゼーションエディターでは使用できません。 [詳細情報](../../personalization/functions/dates.md)

## currentTimeInMillis {#currentTimeInMillis}

現在の時間をエポックミリ秒単位で返します。

+++構文

`currentTimeInMillis()`

+++

+++パラメーター

この関数はパラメーターを使用しません。

+++

+++署名と返されたタイプ

`currentTimeInMillis()`

整数を返します。

+++

+++例

`currentTimeInMillis()`

「1544712617131」を返します。

+++

## inLastDays {#inLastDays}

指定されたdateTimeが現在と現在の間（デルタ日）の場合にtrueを返します。

+++構文

`inLastDays(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inLastDays(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

trueを返します。

+++

## inLastHours {#inLastHours}

指定された日時が現在と現在の間（デルタ時間）の場合にtrueを返します。

+++構文

`inLastHours(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inLastHours(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

trueを返します。

`inLastHours(@event{MyEvent.timestamp}, 4)`

trueを返します。

+++

## inLastMonths {#inLastMonths}

指定された日付または日時が現在と現在の間（デルタ月）である場合にtrueを返します。

+++構文

`inLastMonths(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inLastMonths(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastMonths(toDateTime('2023-12-12T01:11:00Z'), 4)`

trueを返します。

+++

## inLastYears {#inLastYears}

指定された日付または日時が現在と現在の間（デルタ年）の場合、trueを返します。

+++構文

`inLastYears(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inLastYears(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastYears(toDateTime('2023-12-12T01:11:00Z'), 4)`

trueを返します。

+++

## inNextDays {#inNextDays}

指定された日付または日時が現在と現在の間にある場合はtrueを返します。

+++構文

`inNextDays(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inNextDays(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

trueを返します。

+++

## inNextHours {#inNextHours}

指定された日付または日時が現在と現在の間にある場合はtrueを返します。

+++構文

`inNextHours(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inNextHours(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

trueを返します。

+++

## inNextMonths {#inNextMonths}

指定された日付または日時が現在から現在+差分月の間にある場合、trueを返します。

+++構文

`inNextMonths(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextMonths(toDateTime('2023-01-12T01:11:00Z'), 4)`

trueを返します。

+++

## inNextYears {#inNextYears}

指定された日付または日時が現在と現在の差分年の間にある場合は、trueを返します。

+++構文

`inNextYears(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | 整数 |

+++

+++署名と返されたタイプ

`inNextYears(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

trueを返します。

+++

## now {#now}

現在の日付を日付形式で返します。 データ型について詳しくは、[このページ ](../expression/data-types.md)を参照してください。

>[!NOTE]
>
>この関数は、ジャーニー式でのみ使用できます。 メールのパーソナライゼーションやその他のコンテンツには、代わりに`getCurrentZonedDateTime()`を使用してください。 [詳細情報](../../personalization/functions/dates.md#get-current-zoned-date-time)

+++構文

`now(<parameter>)`

+++

+++パラメーター

| パラメーター | 効果 |
|--- |--- |
| 文字列 | タイムゾーン識別子（オプション） |

+++

+++署名と返されたタイプ

`now()`

`now("<timeZone id>")`

dateTimeを返します。

+++

+++例

`now()`

2023-06-03T06:30Zを返します。

`toString(now())`

「2023-06-03T06:30Z」を返します

`now("Europe/Paris")`

2023-06-03T08:30+02:00を返します。

+++

## nowWithDelta {#nowWithDelta}

オフセットを含む現在の日時を返します。 タイムゾーン IDを指定すると、タイムゾーンオフセットが適用されます。 データ型について詳しくは、[このページ ](../expression/data-types.md)を参照してください。

+++構文

`nowWithDelta(<parameters>)`

+++

+++パラメーター

| パラメーター | 効果 |
|--- |--- |
| delta | 正または負の整数値 |
| 日付部分 | 年、月、日、時間、分、秒を文字列として指定します |
| タイムゾーン id | タイムゾーン値の文字列表現。 詳しくは、[ データタイプ ](../expression/data-types.md)を参照してください。 タイムゾーン IDは文字列定数である必要があります。 フィールド参照または式にすることはできません。 |

+++

+++署名と返されたタイプ

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

dateTimeを返します。

+++

+++例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

正確に2時間前のdateTimeを返します。

+++

## setHours {#setHours}

日時または日時のみの時間を設定します。 たとえば、明日の特定の時間まで待ちたい場合は、時間を強制できます。

+++構文

`setHours(<parameter>)`

+++

+++パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 時間 | 整数 |

+++

+++署名と返されたタイプ

`setHours(<dateTime>,<hours>)`

日時を返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを考慮せずに日時を返します。

+++

+++例

`setHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

2023-12-12T04:11:00Zを返します。

`setHours(nowWithDelta(1, "days"), 20)`

明日を午後8:XY時に返します。XYは、現在の時間評価の時点の分です。 評価が午前2:45時に行われた場合、返される時間は午後8:45時になります。

+++

## setDays {#setDays}

日時または日時のみの日を設定します。 例えば、月の特定の日まで待ちたい場合は、その日を強制できます。

+++構文

`setDays(<parameter>)`

+++

+++パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 日数 | 整数 |

+++

+++署名と返されたタイプ

`setDays(<dateTime>,<days>)`

日時を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを考慮せずに日時を返します。

+++

+++例

`setDays(toDateTime('2023-12-12T01:11:00Z'), 25)`

2023-12-25T01:11:00Zを返します。

`setDays(toDateTimeOnly(@event{MyEvent.registrationDate}), 1)`

+++

## updateTimeZone {#updateTimeZone}

同じインスタントに新しいタイムゾーンを持つ新しい日時を返します。

+++構文

`updateTimeZone(<parameters>)`

+++

+++パラメーター

* タイムゾーン id：文字列
* dateTime

+++

+++署名と返された型

`updateTimeZone(<dateTime>,<timeZone id>)`

日時を返します。

+++

+++例

`updateTimeZone( toDateTime("2023-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2023-08-28T17:15:30.123+02:00を返します。

`updateTimeZone(@event{MyExpEvent.timestamp}, "Australia/Sydney")`

タイムスタンプフィールドの値が`2021-11-16T16:55:12.939318+01:00`の場合、関数は`2021-11-17T02:55:12.942115+11:00`を返します。

+++

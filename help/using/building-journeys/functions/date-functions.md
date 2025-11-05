---
product: journey optimizer
title: 日付関数
description: 日付関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 日付，関数，式，ジャーニー，時間
version: Journey Orchestration
source-git-commit: bb47ca4957129a4d05aa3d7286409eef0cb62143
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 83%

---

# 日付関数 {#date-functions}

日付関数を使用すると、ジャーニー式内で日付と時間の値を操作および操作できます。 これらの機能は、カスタマージャーニーでの時間ベースの条件、スケジュール、時間計算に不可欠です。

日付関数は、次の場合に使用します。

* 特定のタイムゾーン処理（[now](#now)、[nowWithDelta](#nowWithDelta)、[currentTimeInMillis](#currentTimeInMillis)）で現在の時刻または日付を取得します
* 日付が特定の時間範囲（[inLastDays](#inLastDays)、[inLastHours](#inLastHours)、[inLastMonths](#inLastMonths)、[inLastYears](#inLastYears)、[inNextDays](#inNextDays)、[inNextHours](#inNextHours)、[inNextMonths](#inNextMonths)、[inNextYears](#inNextYears)）に該当するかどうかを確認します
* 日時コンポーネント（[setHours](#setHours)、[setDays](#setDays)、[updateTimeZone](#updateTimeZone)）を変更する
* 時間ベースの計算と比較の実行
* 異なる時間形式と表示域の変換

日付関数を使用すると、時間ロジックを正確に制御でき、特定の期間やスケジュールに応答する、時間依存のジャーニーパスおよび条件を作成できます。

## currentTimeInMillis {#currentTimeInMillis}

現在の時刻をエポックミリ秒単位で返します。

+++構文

`currentTimeInMillis()`

+++

+++パラメーター

この関数にパラメーターはありません。

+++

+++シグネチャと戻り値のタイプ

`currentTimeInMillis()`

整数を返します。

+++

+++例

`currentTimeInMillis()`

「1544712617131」を返します。

+++

## inLastDays {#inLastDays}

指定された dateTime が現在の日時とその delta 日前の間にある場合、true を返します。

+++構文

`inLastDays(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inLastDays(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

+++

## inLastHours {#inLastHours}

指定された日時が現在の日時とその delta 時間前の間にある場合、true を返します。

+++構文

`inLastHours(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inLastHours(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

`inLastHours(@event{MyEvent.timestamp}, 4)`

true を返します。

+++

## inLastMonths {#inLastMonths}

指定された日付または日時が現在の日時とその delta か月前の間にある場合、true を返します。

+++構文

`inLastMonths(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inLastMonths(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastMonths(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

+++

## inLastYears {#inLastYears}

指定された日付または日時が現在の日時とその delta 年前の間にある場合、true を返します。

+++構文

`inLastYears(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inLastYears(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inLastYears(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

+++

## inNextDays {#inNextDays}

指定された日付または日時が現在の日時とその delta 日後の間にある場合、true を返します。

+++構文

`inNextDays(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inNextDays(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

+++

## inNextHours {#inNextHours}

指定された日付または日時が現在と現在 + デルタ時間の間にある場合、true を返します。

+++構文

`inNextHours(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inNextHours(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。

+++

## inNextMonths {#inNextMonths}

指定された日付または日時が現在の日時とその delta か月後の間にある場合、true を返します。

+++構文

`inNextMonths(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextMonths(toDateTime('2023-01-12T01:11:00Z'), 4)`

true を返します。

+++

## inNextYears {#inNextYears}

指定された日付または日時が現在の日時とその delta 年後の間にある場合、true を返します。

+++構文

`inNextYears(<dateTime>,<delta>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

+++

+++シグネチャと戻り値のタイプ

`inNextYears(<dateTime>,<integer>)`

ブール値を返します。

+++

+++例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

true を返します。

+++

## now {#now}

現在の日付を日時形式で返します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

+++構文

`now(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | タイムゾーン識別子（オプション） |

+++

+++シグネチャと戻り値のタイプ

`now()`

`now("<timeZone id>")`

日時を返します。

+++

+++例

`now()`

2023-06-03T06:30Z を返します。

`toString(now())`

&quot;2023-06-03T06:30Z&quot; を返します。

`now("Europe/Paris")`

2023-06-03T08:30+02:00 を返します。

+++

## nowWithDelta {#nowWithDelta}

オフセットを含んだ現在の日時を返します。 タイムゾーン ID を指定した場合は、タイムゾーンオフセットが適用されます。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

+++構文

`nowWithDelta(<parameters>)`

+++

+++パラメーター

| パラメーター | 説明 |
|--- |--- |
| delta | 正または負の整数値 |
| 日時の構成要素 | 「years」、「months」、「days」、「hours」、「minutes」、「seconds」のいずれかを文字列として指定します |
| タイムゾーン ID | タイムゾーン値の文字列表現。 詳しくは、[データタイプ](../expression/data-types.md)を参照してください。タイムゾーン ID は文字列定数である必要があります。フィールド参照や式は使用できません。 |

+++

+++シグネチャと戻り値のタイプ

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

日時を返します。

+++

+++例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

正確に 2 時間前の日時を返します。

+++

## setHours {#setHours}

日時または日時のみの時を設定します。例えば、明日の特定の正時まで待つ場合に、その正時を強制的に指定できます。

+++構文

`setHours(<parameter>)`

+++

+++パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | 日時のみ |
| 時 | 整数 |

+++

+++シグネチャと戻り値のタイプ

`setHours(<dateTime>,<hours>)`

日時を返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを無視して日時を返します。

+++

+++例

`setHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

2023-12-12T04:11:00Z を返します。

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後 8:XY を返します（XY は現在時刻の分）。評価が午前 2:45 に行われた場合、返される時刻は午後 8:45 になります。

+++

## setDays {#setDays}

日時または日時のみの日を設定します。例えば、その月の特定の日まで待つ場合に、その日を強制的に指定できます。

+++構文

`setDays(<parameter>)`

+++

+++パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | 日時のみ |
| 日 | 整数 |

+++

+++シグネチャと戻り値のタイプ

`setDays(<dateTime>,<days>)`

日時を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを無視して日時を返します。

+++

+++例

`setDays(toDateTime('2023-12-12T01:11:00Z'), 25)`

2023-12-25T01:11:00Z を返します。

`setDays(toDateTimeOnly(@event{MyEvent.registrationDate}), 1)`

+++

## updateTimeZone {#updateTimeZone}

新しいタイムゾーンで、同じ瞬間の新しい日時を返します。

+++構文

`updateTimeZone(<parameters>)`

+++

+++パラメーター

* タイムゾーン ID：文字列
* 日時

+++

+++シグネチャと戻り値のタイプ

`updateTimeZone(<dateTime>,<timeZone id>)`

日時を返します。

+++

+++例

`updateTimeZone( toDateTime("2023-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2023-08-28T17:15:30.123+02:00 を返します。

`updateTimeZone(@event{MyExpEvent.timestamp}, "Australia/Sydney")`

「timestamp」フィールドの値が `2021-11-16T16:55:12.939318+01:00` の場合、この関数は `2021-11-17T02:55:12.942115+11:00` を返します。

+++


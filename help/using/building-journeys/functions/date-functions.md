---
product: journey optimizer
title: 日付関数
description: 日付関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 日付, 関数, 式, ジャーニー, 時間
version: Journey Orchestration
exl-id: 68c102c1-f1c7-44b7-893f-9a3b7e0854b6
TQID: https://experienceleague.adobe.com/C2Z5SufckUxCNf9TsloziZS-Q3KPzmgMVNGJGiwDQ08
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
subfeature_v2: []
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 1275
ht-degree: 65%

---

# 日付関数 {#date-functions}

日付関数を使用すると、ジャーニー式内で日時の値を操作して作業できます。 これらの関数は、カスタマージャーニーでの時間ベースの条件、スケジュール、時間計算に不可欠です。

日付関数は、次の操作が必要な場合に使用します。

* 特定のタイムゾーン処理（[now](#now)、[nowWithDelta](#nowWithDelta)、[currentTimeInMillis](#currentTimeInMillis)）を使用して現在の時刻または日付を取得
* 日付が特定の時間範囲（[inLastDays](#inLastDays)、[inLastHours](#inLastHours)、[inLastMonths](#inLastMonths)、[inLastYears](#inLastYears)、[inNextDays](#inNextDays)、[inNextHours](#inNextHours)、[inNextMonths](#inNextMonths)、[inNextYears](#inNextYears)）に該当するかどうかを確認
* 日時コンポーネント（[setHours](#setHours)、[setDays](#setDays)、[updateTimeZone](#updateTimeZone)）を変更
* 時間ベースの計算と比較を実行
* 異なる時間形式と表示域間を変換

日付関数は、時間ロジックを正確に制御し、特定の期間とスケジュールに応答する、時間依存のジャーニーパスと条件を作成できます。

>[!NOTE]
>
>このページの関数は、ジャーニー式で使用できます。 `now()` などの一部の関数は、メールコンテンツのパーソナライゼーションエディターでは使用できません。 [詳細情報](../../personalization/functions/dates.md)

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

現在の日付を日時形式で返します。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

>[!NOTE]
>
>この関数は、ジャーニー式でのみ使用できます。 メールのパーソナライゼーションやその他のコンテンツには、代わりに `getCurrentZonedDateTime()` を使用します。 [詳細情報](../../personalization/functions/dates.md#get-current-zoned-date-time)

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
| タイムゾーン ID | タイムゾーン値の文字列表現。 詳しくは、[データタイプ](../expression/data-types.md)を参照してください。 タイムゾーン ID は文字列定数である必要があります。 フィールド参照や式は使用できません。 |

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

日時または日時のみの時を設定します。 例えば、明日の特定の正時まで待つ場合に、その正時を強制的に指定できます。

+++構文

`setHours(<parameter>)`

+++

+++パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
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

明日の午後 8:XY を返します（XY は現在時刻の分）。 評価が午前 2:45 に行われた場合、返される時刻は午後 8:45 になります。

+++

## setDays {#setDays}

日時または日時のみの日を設定します。 例えば、その月の特定の日まで待つ場合に、その日を強制的に指定できます。

+++構文

`setDays(<parameter>)`

+++

+++パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
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

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、AJO ジャーニー式で使用できるすべての日付関数と時刻関数について説明します。現在の時刻を取得する方法、日付が相対時間枠内にあるかどうかを確認する方法、日付/時刻コンポーネントを変更する方法について説明します。

**インテント：**
* `now`または`nowWithDelta`を使用して、現在の日時（オプションのタイムゾーン付き）を取得します
* `currentTimeInMillis`を使用して、現在の時間をエポック整数として取得します
* `inLastDays`、`inLastHours`、`inLastMonths`、`inLastYears`を使用して、過去N日間、時間、月、または年内に日時が含まれているかどうかを確認します
* `inNextDays`、`inNextHours`、`inNextMonths`、`inNextYears`を使用して、日付が次のN日、時間、月、または年内に含まれるかどうかを確認します
* `setHours`または`setDays`を使用して、特定の時間または日を日付値に強制的に設定します
* `updateTimeZone`を使用して同じインスタントを保持しながら、日時を別のタイムゾーンに変換します

**用語集：**
* **dateTime**: タイムゾーンオフセット情報&#x200B;*（製品固有）*&#x200B;を含む日時の値
* **dateTimeOnly**: タイムゾーン情報のない日時の値&#x200B;*（製品固有）*
* **エポックミリ秒**: 1970-01-01T00:00:00Zから経過したミリ秒数を表す整数
* **delta**：現在の時間を年、月、日、時間、分、秒の数だけシフトするために`nowWithDelta`で使用される整数オフセット（正または負）

**ガードレール：**
* `now()`はジャーニー式でのみ使用できます。メールのパーソナライゼーションには、代わりに`getCurrentZonedDateTime()`を使用してください
* `nowWithDelta`のタイムゾーン IDは文字列定数である必要があります。フィールド参照と動的式はサポートされていません
* `updateTimeZone`のタイムゾーン IDは文字列定数である必要があります

**用語：**
* 正規名：日付関数 – 頭字語：なし – バリアント：日時関数、時間関数
* 同義語：&quot;now （）&quot; = &quot;current datetime&quot;; &quot;currentTimeInMillis （）&quot; = &quot;current epoch milliseconds&quot;
* 混同しないでください：&quot;inLastDays&quot; （時間を振り返る） ≠ &quot;inNextDays&quot; （時間を進める）
* 混同しないでください。「setHours」（時間コンポーネントに代わる）≠「nowWithDelta」（現在の時間をオフセットする）
* 「updateTimeZone」（同じインスタント、異なるタイムゾーン表現）≠「setHours」（時間値自体を変更）は混同しないでください

**FAQ:**
* **Q: メールのパーソナライゼーションコンテンツで`now()`を使用できますか？** — `now()`はジャーニー式でのみ使用できます。 電子メールのパーソナライゼーションに`getCurrentZonedDateTime()`を使用します。
* **Q：過去24時間にイベントが発生したかどうかを確認するにはどうすればよいですか？** — `inLastHours(@event{MyEvent.timestamp}, 24)`を使用します。
* **Q：過去に2時間オフセットした現在の時間を取得するにはどうすればよいですか？** — `nowWithDelta(-2, "hours")`を使用します。
* **Q: `updateTimeZone`と`setHours`の違いは何ですか？** — `updateTimeZone`は同じ時刻を保持しますが、別のタイムゾーンで表現します。一方、`setHours`は実際に日時の値の時間コンポーネントを変更します。
* **Q: `nowWithDelta`のタイムゾーンパラメーターをプロファイルフィールドにすることはできますか？**  – いいえ、タイムゾーン IDは文字列定数である必要があります。フィールド参照はサポートされていません。

+++

---
solution: Journey Optimizer
product: journey optimizer
title: 関数
description: ジャーニー式の関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 関数, 式, エディター, ジャーニー, データ, 操作
exl-id: 5b978eef-7d3e-41fe-bb08-0cf37c3b125d
version: Journey Orchestration
source-git-commit: 99053c6c1327818645adc4ab9a5d3dd30eb96b87
workflow-type: ht
source-wordcount: '855'
ht-degree: 100%

---

# 関数 {#functions}

関数は、Adobe Journey Optimizer の動的なジャーニー式の構成要素です。リアルタイムでデータを変換、計算、検証、操作し、パーソナライズされたカスタマーエクスペリエンスを作成できます。直感的なカテゴリに整理された 60 を超える関数を使用することで、高度な条件を作成し、複雑な計算を実行し、カスタマージャーニーのすべてのステップでデータ駆動型の意思決定を行うことができます。

## 関数について

ジャーニー式の関数は、次の一貫性のある構文パターンに従います。

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

**主な特性：**

* **複数のシグネチャ**：関数は、様々なユースケースに対応するために、異なるシグネチャ（順序付きパラメーターの異なるセット）を持つことができます
* **タイプ固有の戻り値**：各関数には、特定の戻り値タイプ（文字列、整数、ブール値、日付、リストなど）があります
* **0～N 個のパラメーター**：関数は 0～N 個の式を順序付きパラメーターとして受け入れることができるので、使用方法を柔軟に指定できます

## 関数を使用する理由

関数を使用すると、次の操作を実行できます。

* **動的条件を作成** - リアルタイムデータ評価に基づいてジャーニーパスを分岐します
* **大規模にパーソナライズ** - お客様データと行動インサイトを活用してコンテンツとエクスペリエンスをカスタマイズします。
* **決定を自動化** - 手動介入なしでインテリジェントロジックを作成します
* **データを変換** - 互換性を確保するために、データタイプを変換、書式設定、操作します
* **計算を実行** - 数学演算と統計的な分析を実行します
* **入力を検証** - アクションを実行する前に、データの品質と完全性を確認します

## カテゴリ別関数

主な目的別に整理された関数を参照して、ニーズに合った適切なツールをすばやく見つけます。

### Adobe Experience Platform {#aep-functions}

**オーディエンスのセグメント化とターゲティング**

オーディエンスメンバーシップを評価し、Adobe Experience Platform で定義された顧客セグメントに基づいてパーソナライズされたジャーニーパスを作成します。

| 関数 | 説明 |
|----------|-------------|
| [inAudience](../functions/functioninaudience.md) | 個人が特定のオーディエンスに属しているかどうかを確認します |

[Adobe Experience Platform の関数の詳細を表示 →](../functions/functioninaudience.md)

### 集計関数 {#aggregation-functions}

**統計計算とデータ要約**

値のセットに対して計算を実行し、平均値、カウント、合計値、最小値／最大値などのインサイトを導き出します。データ駆動型の意思決定に不可欠です。

| 関数 | 説明 |
|----------|-------------|
| [avg](../functions/aggregation-functions.md#avg) | 平均値を計算します |
| [count](../functions/aggregation-functions.md#count) | null 以外の要素をカウントします |
| [countOnlyNull](../functions/aggregation-functions.md#countOnlyNull) | null 値のみをカウントします |
| [countWithNull](../functions/aggregation-functions.md#countWithNull) | null を含むすべての要素をカウントします |
| [distinctCount](../functions/aggregation-functions.md#distinctCount) | 一意の null 以外の値をカウントします |
| [distinctCountWithNull](../functions/aggregation-functions.md#distinctCountWithNull) | null を含む一意の値をカウントします |
| [max](../functions/aggregation-functions.md#max) | 最大値を見つけます |
| [min](../functions/aggregation-functions.md#min) | 最小値を見つけます |
| [sum](../functions/aggregation-functions.md#sum) | 合計を計算します |

[すべての集計関数を表示 →](../functions/aggregation-functions.md)

### コンバージョン関数 {#conversion-functions}

**データタイプ変換**

操作とデータソース間の互換性を確保するために、様々なタイプ（文字列、整数、小数、ブール値、日付、期間）間でデータを変換します。

| 関数 | 説明 |
|----------|-------------|
| [toBool](../functions/conversion-functions.md#toBool) | ブール値に変換します |
| [toDateOnly](../functions/conversion-functions.md#toDateOnly) | 日付のみ（時間なし）に変換します |
| [toDateTime](../functions/conversion-functions.md#toDateTime) | 時刻付きで日付に変換します |
| [toDateTimeOnly](../functions/conversion-functions.md#toDateTimeOnly) | タイムゾーンなしの日付と時刻に変換します |
| [toDecimal](../functions/conversion-functions.md#toDecimal) | 小数に変換します |
| [toDuration](../functions/conversion-functions.md#toDuration) | 期間に変換します |
| [toInteger](../functions/conversion-functions.md#toInteger) | 整数に変換します |
| [toString](../functions/conversion-functions.md#toString) | 文字列に変換します |

[すべてのコンバージョン関数を表示 →](../functions/conversion-functions.md)

### 日付関数 {#date-functions}

**日時の操作**

日付、時刻、タイムゾーンを操作して、時間ベースの条件を作成し、アクションをスケジュールし、時間計算を実行します。

| 関数 | 説明 |
|----------|-------------|
| [currentTimeInMillis](../functions/date-functions.md#currentTimeInMillis) | 現在の時刻をミリ秒単位で取得します |
| [inLastDays](../functions/date-functions.md#inLastDays) | 日付が過去 N 日以内かどうかを確認します |
| [inLastHours](../functions/date-functions.md#inLastHours) | 日付が過去 N 時間以内かどうかを確認します |
| [inLastMonths](../functions/date-functions.md#inLastMonths) | 日付が過去 N か月以内かどうかを確認します |
| [inLastYears](../functions/date-functions.md#inLastYears) | 日付が過去 N 年以内かどうかを確認します |
| [inNextDays](../functions/date-functions.md#inNextDays) | 日付が次の N 日以内かどうかを確認します |
| [inNextHours](../functions/date-functions.md#inNextHours) | 日付が次の N 時間以内かどうかを確認します |
| [inNextMonths](../functions/date-functions.md#inNextMonths) | 日付が次の N か月以内かどうかを確認します |
| [inNextYears](../functions/date-functions.md#inNextYears) | 日付が次の N 年以内かどうかを確認します |
| [now](../functions/date-functions.md#now) | 現在の日時を取得します |
| [nowWithDelta](../functions/date-functions.md#nowWithDelta) | オフセット付きで現在の時刻を取得します |
| [setHours](../functions/date-functions.md#setHours) | 日時で特定の時間を設定します |
| [setDays](../functions/date-functions.md#setDays) | 日時で特定の日付を設定します |
| [updateTimeZone](../functions/date-functions.md#updateTimeZone) | 日時のタイムゾーンを更新します |

[すべての日付関数を表示 →](../functions/date-functions.md)

### リスト関数 {#list-functions}

**コレクションの操作と分析**

配列とリストをフィルタリング、並べ替え、変換、分析して、複雑なデータ構造を操作し、設定操作を実行します。

| 関数 | 説明 |
|----------|-------------|
| [distinct](../functions/list-functions.md#distinct) | 一意の値を取得します（null は除外されます） |
| [distinctWithNull](../functions/list-functions.md#distinctWithNull) | 一意の値を取得します（null を含みます） |
| [filter](../functions/list-functions.md#filter) | 条件に基づいてリストをフィルタリングします |
| [getListItem](../functions/list-functions.md#getListItem) | 特定のインデックスの項目を取得します |
| [in](../functions/list-functions.md#in) | リストに値が存在するかどうかを確認します |
| [intersect](../functions/list-functions.md#intersect) | リスト間の共通要素を見つけます |
| [limit](../functions/list-functions.md#limit) | 返される項目の数を制限します |
| [listSize](../functions/list-functions.md#listSize) | リストのサイズを取得します |
| [serializeList](../functions/list-functions.md#serializeList) | リストを文字列に変換します |
| [sort](../functions/list-functions.md#sort) | リスト要素を並べ替えます |

[すべてのリスト関数を表示 →](../functions/list-functions.md)

### 数学関数 {#math-functions}

**数学演算**

データ処理とビジネスロジックに対して数値計算と変換を実行します。

| 関数 | 説明 |
|----------|-------------|
| [random](../functions/math-functions.md#random) | 乱数（0～1）を生成します |
| [round](../functions/math-functions.md#round) | 最も近い整数に丸めます |

[すべての数学関数を表示 →](../functions/math-functions.md)

### 文字列関数 {#string-functions}

**テキストの操作と検証**

動的コンテンツの作成と条件付きロジック用にテキストデータを処理、変換、検索、検証します。

| 関数 | 説明 |
|----------|-------------|
| [concat](../functions/string-functions.md#concat) | 文字列を連結します |
| [contain](../functions/string-functions.md#contain) | 文字列に部分文字列が含まれているかどうかを確認します |
| [containIgnoreCase](../functions/string-functions.md#containIgnoreCase) | 「次を含む」を確認します（大文字と小文字は区別されません） |
| [endWith](../functions/string-functions.md#endWith) | 文字列が接尾辞で終わるかどうかを確認します |
| [endWithIgnoreCase](../functions/string-functions.md#endWithIgnoreCase) | 「次で終わる」を確認します（大文字と小文字は区別されません） |
| [equalIgnoreCase](../functions/string-functions.md#equalIgnoreCase) | 文字列を比較します（大文字と小文字は区別されません） |
| [indexOf](../functions/string-functions.md#indexOf) | 最初の発生位置を検索します |
| [isEmpty](../functions/string-functions.md#isEmpty) | 文字列が空かどうかを確認します |
| [isNotEmpty](../functions/string-functions.md#isNotEmpty) | 文字列が空でないかどうかを確認します |
| [lastIndexOf](../functions/string-functions.md#lastIndexOf) | 最後の発生位置を検索します |
| [length](../functions/string-functions.md#length) | 文字列の長さを取得します |
| [lower](../functions/string-functions.md#lower) | 小文字に変換します |
| [matchRegExp](../functions/string-functions.md#matchRegExp) | 正規表現に一致します |
| [notEqualIgnoreCase](../functions/string-functions.md#notEqualIgnoreCase) | 「次と等しくない」を確認します（大文字と小文字は区別されません） |
| [replace](../functions/string-functions.md#replace) | 最初の発生を置き換えます |
| [replaceAll](../functions/string-functions.md#replaceAll) | すべての発生を置き換えます |
| [split](../functions/string-functions.md#split) | 文字列を配列に分割します |
| [startWith](../functions/string-functions.md#startWith) | 文字列が接頭辞で始まるかどうかを確認します |
| [startWithIgnoreCase](../functions/string-functions.md#startWithIgnoreCase) | 「次で始まる」を確認します（大文字と小文字は区別されません） |
| [substr](../functions/string-functions.md#substr) | 部分文字列を抽出します |
| [trim](../functions/string-functions.md#trim) | 先頭／末尾のスペースを削除します |
| [upper](../functions/string-functions.md#upper) | 大文字に変換します |
| [uuid](../functions/string-functions.md#uuid) | UUID を生成します |

[すべての文字列関数を表示→](../functions/string-functions.md)

## 次の手順

使用可能な機能を理解したら、次を参照してください。

* **[高度な式エディター](expressionadvanced.md)** - 高度なエディターを使用して複雑な式を作成する方法について説明します
* **[式の構文](generalities.md)** - ジャーニー式を記述するための構文ルールを習得します
* **[演算子](operators.md)** - 関数でロジックを作成するために使用できる演算子について説明します
* **[フィールド参照](field-references.md)** - 式でデータフィールドを参照する方法について説明します

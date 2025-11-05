---
solution: Journey Optimizer
product: journey optimizer
title: 関数
description: ジャーニー式の関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 関数，式，エディター，ジャーニー，データ，操作
exl-id: 5b978eef-7d3e-41fe-bb08-0cf37c3b125d
version: Journey Orchestration
source-git-commit: 99053c6c1327818645adc4ab9a5d3dd30eb96b87
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 11%

---

# 関数 {#functions}

関数は、Adobe Journey Optimizerの動的なジャーニー式の構成要素です。 データをリアルタイムで変換、計算、検証および操作して、パーソナライズされた顧客体験を作成できます。 60 を超える機能を直感的なカテゴリに整理することで、高度な条件を作成し、複雑な計算を実行し、カスタマージャーニーのすべてのステップでデータに基づく意思決定を行うことができます。

## 関数について

ジャーニー式の関数は、一貫した構文パターンに従います。

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

**主な特徴：**

* **複数のシグネチャ**：関数は、様々なユースケースに対応するために異なるシグネチャ（順序付きパラメーターの異なるセット）を持つことができます
* **型固有の戻り値**：各関数には、特定の戻り値タイプ（文字列、整数、ブール値、日付、リストなど）があります。
* **0 から N のパラメーター**：関数は、0 から N の式を順序付きパラメーターとして受け入れることができ、使用方法を柔軟に指定できます

## 関数を使用する理由

関数を使用すると、次のことができます。

* **動的条件の作成** - リアルタイムデータ評価に基づく分岐ジャーニーパス
* **大規模にパーソナライズ** – 顧客データと行動インサイトを使用して、コンテンツとエクスペリエンスをカスタマイズします
* **決定の自動化** – 手動の介入なしでインテリジェント・ロジックを構築
* **データの変換** - データタイプを変換、書式設定および操作して、互換性を確保します
* **計算の実行** – 数学演算と統計分析を実行します
* **入力を検証** - アクションを実行する前に、データの品質と完全性を確認します

## カテゴリ別関数

主な目的別に整理された機能を参照して、ニーズに合った適切なツールをすばやく見つけます。

### Adobe Experience Platform {#aep-functions}

**オーディエンスのセグメント化とターゲティング**

オーディエンスメンバーシップを評価し、Adobe Experience Platformで定義された顧客セグメントに基づいてパーソナライズされたジャーニーパスを作成します。

| 関数 | 説明 |
|----------|-------------|
| [inAudience](../functions/functioninaudience.md) | 個人が特定のオーディエンスに属しているかどうかを確認 |

[Adobe Experience Platform関数の詳細を表示→](../functions/functioninaudience.md)

### 集計関数 {#aggregation-functions}

**統計計算及びデータの要約**

値のセットに対して計算を実行し、平均、カウント、合計、最小値/最大値などのインサイトを導き出します。 データに基づく意思決定に不可欠です。

| 関数 | 説明 |
|----------|-------------|
| [avg](../functions/aggregation-functions.md#avg) | 平均値を計算 |
| [count](../functions/aggregation-functions.md#count) | Null 以外の要素をカウント |
| [countOnlyNull](../functions/aggregation-functions.md#countOnlyNull) | Null 値のみをカウント |
| [countWithNull](../functions/aggregation-functions.md#countWithNull) | null を含むすべての要素をカウント |
| [distinctCount](../functions/aggregation-functions.md#distinctCount) | 一意の null 以外の値をカウント |
| [distinctCountWithNull](../functions/aggregation-functions.md#distinctCountWithNull) | null を含む一意の値をカウント |
| [max](../functions/aggregation-functions.md#max) | 最大値を検索 |
| [min](../functions/aggregation-functions.md#min) | 最小値を検索 |
| [sum](../functions/aggregation-functions.md#sum) | 合計金額を計算 |

[すべての集計関数を表示→](../functions/aggregation-functions.md)

### コンバージョン関数 {#conversion-functions}

**データタイプ変換**

様々なタイプ（文字列、整数、小数、ブール、日付、期間）のデータを変換し、操作やデータソース間で互換性を確保します。

| 関数 | 説明 |
|----------|-------------|
| [toBool](../functions/conversion-functions.md#toBool) | ブール値に変換 |
| [toDateOnly](../functions/conversion-functions.md#toDateOnly) | 日付のみに変換（時間なし） |
| [toDateTime](../functions/conversion-functions.md#toDateTime) | 日付（時刻）に変換 |
| [toDateTimeOnly](../functions/conversion-functions.md#toDateTimeOnly) | タイムゾーンを含まない日時に変換 |
| [toDecimal](../functions/conversion-functions.md#toDecimal) | 10 進数に変換 |
| [toDuration](../functions/conversion-functions.md#toDuration) | 期間に変換 |
| [toInteger](../functions/conversion-functions.md#toInteger) | 整数に変換 |
| [toString](../functions/conversion-functions.md#toString) | 文字列に変換 |

[すべてのコンバージョン関数を表示→](../functions/conversion-functions.md)

### 日付関数 {#date-functions}

**日時操作**

日付、時刻、タイムゾーンを操作して、時間ベースの条件を作成し、アクションをスケジュールし、時間計算を実行します。

| 関数 | 説明 |
|----------|-------------|
| [currentTimeInMillis](../functions/date-functions.md#currentTimeInMillis) | 現在の時刻をミリ秒単位で取得します |
| [inLastDays](../functions/date-functions.md#inLastDays) | 日付が過去 N 日以内かどうかを確認 |
| [inLastHours](../functions/date-functions.md#inLastHours) | 日付が過去 N 時間以内かどうかを確認 |
| [inLastMonths](../functions/date-functions.md#inLastMonths) | 日付が過去 N か月以内かどうかを確認 |
| [inLastYears](../functions/date-functions.md#inLastYears) | 日付が過去 N 年以内かどうかを確認 |
| [inNextDays](../functions/date-functions.md#inNextDays) | 日付が次の N 日以内であるかどうかを確認します |
| [inNextHours](../functions/date-functions.md#inNextHours) | 日付が次の N 時間以内であるかどうかを確認します |
| [inNextMonths](../functions/date-functions.md#inNextMonths) | 日付が次の N か月以内であるかどうかを確認します |
| [inNextYears](../functions/date-functions.md#inNextYears) | 日付が次の N 年以内であるかどうかを確認します |
| [now](../functions/date-functions.md#now) | 現在の日時を取得 |
| [nowWithDelta](../functions/date-functions.md#nowWithDelta) | オフセットを使用して現在の時刻を取得 |
| [setHours](../functions/date-functions.md#setHours) | 日時に特定の時間を設定する |
| [setDays](../functions/date-functions.md#setDays) | 日時に特定の日を設定する |
| [updateTimeZone](../functions/date-functions.md#updateTimeZone) | 日時のタイムゾーンを更新 |

[すべての日付関数の表示→](../functions/date-functions.md)

### リスト関数 {#list-functions}

**収集の操作と分析**

配列とリストをフィルタリング、並べ替え、変換、分析して、複雑なデータ構造を扱い、設定操作を実行します。

| 関数 | 説明 |
|----------|-------------|
| [distinct](../functions/list-functions.md#distinct) | 一意の値を取得（null を除く） |
| [distinctWithNull](../functions/list-functions.md#distinctWithNull) | 一意の値を取得（null を含む） |
| [filter](../functions/list-functions.md#filter) | 条件に基づいてリストをフィルター |
| [getListItem](../functions/list-functions.md#getListItem) | 特定のインデックスの項目を取得 |
| [in](../functions/list-functions.md#in) | 値がリストに存在するかどうかを確認 |
| [intersect](../functions/list-functions.md#intersect) | リスト間で共通する要素の検索 |
| [limit](../functions/list-functions.md#limit) | 返されるアイテムの制限数 |
| [listSize](../functions/list-functions.md#listSize) | リストのサイズを取得 |
| [serializeList](../functions/list-functions.md#serializeList) | リストを文字列に変換 |
| [sort](../functions/list-functions.md#sort) | リスト要素の並べ替え |

[すべてのリスト関数の表示→](../functions/list-functions.md)

### 数学関数 {#math-functions}

**数学演算**

データ処理とビジネス・ロジックに対して数値計算と変換を実行します。

| 関数 | 説明 |
|----------|-------------|
| [random](../functions/math-functions.md#random) | 乱数を生成（0-1） |
| [round](../functions/math-functions.md#round) | 最も近い整数に丸める |

[すべての数学関数の表示→](../functions/math-functions.md)

### 文字列関数 {#string-functions}

**テキストの操作と検証**

動的コンテンツ作成および条件付きロジック用のテキストデータを処理、変換、検索および検証します。

| 関数 | 説明 |
|----------|-------------|
| [concat](../functions/string-functions.md#concat) | 文字列の連結 |
| [contain](../functions/string-functions.md#contain) | 文字列に部分文字列が含まれているかどうかを確認 |
| [containIgnoreCase](../functions/string-functions.md#containIgnoreCase) | 次を含むをチェック（大文字と小文字を区別しない） |
| [endWith](../functions/string-functions.md#endWith) | 文字列がサフィックスで終わっているかどうかを確認する |
| [endWithIgnoreCase](../functions/string-functions.md#endWithIgnoreCase) | で終わる項目をチェック（大文字と小文字を区別しない） |
| [equalIgnoreCase](../functions/string-functions.md#equalIgnoreCase) | 文字列を比較する（大文字と小文字を区別しない） |
| [indexOf](../functions/string-functions.md#indexOf) | 最初の出現位置を検索 |
| [isEmpty](../functions/string-functions.md#isEmpty) | 文字列が空かどうかを確認 |
| [isNotEmpty](../functions/string-functions.md#isNotEmpty) | 文字列が空でないかどうかを確認 |
| [lastIndexOf](../functions/string-functions.md#lastIndexOf) | 最後のオカレンス位置を検索 |
| [length](../functions/string-functions.md#length) | 文字列の長さを取得 |
| [lower](../functions/string-functions.md#lower) | 小文字に変換 |
| [matchRegExp](../functions/string-functions.md#matchRegExp) | 正規表現に一致 |
| [notEqualIgnoreCase](../functions/string-functions.md#notEqualIgnoreCase) | 等しくないことをチェック （大文字と小文字を区別しない） |
| [replace](../functions/string-functions.md#replace) | 最初の出現箇所を置換 |
| [replaceAll](../functions/string-functions.md#replaceAll) | すべての出現箇所を置換 |
| [split](../functions/string-functions.md#split) | 文字列を配列に分割 |
| [startWith](../functions/string-functions.md#startWith) | 文字列がプレフィックスで始まるかどうかを確認します |
| [startWithIgnoreCase](../functions/string-functions.md#startWithIgnoreCase) | で始まる項目をチェック（大文字と小文字を区別しない） |
| [substr](../functions/string-functions.md#substr) | 部分文字列を抽出 |
| [trim](../functions/string-functions.md#trim) | 先頭/末尾のスペースを削除 |
| [upper](../functions/string-functions.md#upper) | 大文字に変換 |
| [uuid](../functions/string-functions.md#uuid) | UUID を生成 |

[すべての文字列関数の表示→](../functions/string-functions.md)

## 次の手順

使用可能な関数について説明したので、次を参照してください。

* **[高度な式エディター](expressionadvanced.md)** – 高度なエディターを使用して複雑な式を作成する方法を説明します
* **[式構文](generalities.md)** - ジャーニー式を記述するための構文ルールをマスターします
* **[演算子](operators.md)** – 関数でロジックの構築に使用できる演算子を検出します
* **[フィールド参照](field-references.md)** – 式でデータフィールドを参照する方法を説明します

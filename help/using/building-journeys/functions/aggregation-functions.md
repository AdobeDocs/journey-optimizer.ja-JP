---
product: journey optimizer
title: 集計関数
description: 集計関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 集計，関数，式，ジャーニー，平均，カウント，最大，最小，合計
version: Journey Orchestration
source-git-commit: bb47ca4957129a4d05aa3d7286409eef0cb62143
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 78%

---

# 集計関数 {#aggregation-functions}

集計関数は、一連の値に対して計算を実行し、単一の集計結果を返します。 これらの関数を使用すると、平均の計算、最小値と最大値の検索、要素のカウント、数値の合計によって、ジャーニー式のデータを分析できます。

次の場合に、集計関数を使用します。

* リストまたは配列（[avg](#avg)、[sum](#sum)、[min](#min)、[max](#max)）から統計値を計算します
* null 値を含めるか除外するオプションを使用して、コレクション内の要素（[count](#count)、[countOnlyNull](#countOnlyNull)、[countWithNull](#countWithNull)）をカウントします
* データセット内の一意の値を決定します（[distinctCount](#distinctCount)、[distinctCountWithNull](#distinctCountWithNull)）
* 計算指標に基づくデータ駆動型の決定を行う

集計関数は、特定の動作に従って null 値を自動的に処理するので、欠落値や未定義の値を含む可能性のある実際のデータを簡単に操作できます。


## avg {#avg}

リストまたは 2 つの式のいずれかで指定された一連の式の平均値を返します。null 値は無視されます。

+++構文

`avg(<parameter>)`

+++

+++パラメーター

サポートされているタイプ：

* listInteger
* listDecimal
* 小数
* 整数

+++

+++シグネチャと戻り値のタイプ

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

小数を返します。

+++

+++例

`avg(@event{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0 を返します。

`avg(10.2, 3)`

6.6 を返します。

+++

## count {#count}

null 値を数に入れずに、リストの要素数を数えます。

+++構文

`count(<listAny>)`

`count(<listObject>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合、フィールド参照である必要があります。listObject に null オブジェクトを含めることはできません。 |

+++

+++シグネチャと戻り値のタイプ

`count(<listAny>)`

整数を返します。

+++

+++例

`count([10,2,10,null])`

3 を返します。

`count(@event{my_event.productListItems})`

指定されたオブジェクト配列内のオブジェクト数を返します（listObject 型）。注：listObject に null オブジェクトを含めることはできません

+++

## countOnlyNull {#countOnlyNull}

リスト内の null 値の数をカウントします。

+++構文

`countOnlyNull(<listAny>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly |

+++

+++シグネチャと戻り値のタイプ

`countOnlyNull(<listAny>)`

整数を返します。

+++

+++例

`countOnlyNull([10,2,10,null])`

1 を返します。

+++

**注意：** パラメーター `<listObject>` は、この関数ではサポートされていません。

## countWithNull {#countWithNull}

null 値を含むリストのすべての要素をカウントします。

+++構文

`countWithNull(<listAny>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly |

+++

+++シグネチャと戻り値のタイプ

`countWithNull(<listAny>)`

整数を返します。

+++

+++例

`countWithNull([10,2,10,null])`

4 を返します。

+++

**注意：** パラメーター `<listObject>` は、この関数ではサポートされていません。

## distinctCount {#distinctCount}

null 値を無視して異なる値の数をカウントします。

+++構文

`distinctCount(<listAny>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターはオプションで、listObject に対してのみ使用できます。パラメーターを指定しないと、すべての属性の値が同じ場合、オブジェクトは重複していると見なされます。パラメーターを指定していて、指定された属性が同じ値を持つ場合、オブジェクトは重複していると見なされます。 |

+++

+++シグネチャと戻り値のタイプ

`distinctCount(<listAny>)`

整数を返します。

`distinctCount(<listObject>)`

`distinctCount(<listObject>,<string>)`

オブジェクトのリストを返します。

+++

+++例

`distinctCount([10,2,10,null])`

2 を返します。

`distinctCount(@event{my_event.productListItems})`

指定されたオブジェクト配列内の厳密に異なるオブジェクトの数を返します（listObject 型）。

`distinctCount(@event{my_event.productListItems}, "SKU")`

個別の「SKU」属性値 {} を持つオブジェクトの数を返します。

+++

## distinctCountWithNull {#distinctCountWithNull}

null 値を含め、異なる値の数をカウントします。

+++構文

`distinctCountWithNull(<listAny>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly |

+++

+++シグネチャと戻り値のタイプ

`distinctCountWithNull(<listAny>)`

整数を返します。

+++

+++例

`distinctCountWithNull([10,2,10,null])`

3 を返します。

+++

**注意：** パラメーター `<listObject>` は、この関数ではサポートされていません。

## max {#max}

リストまたは 2 つの式として指定された一連の式の中から最大値を返します。null 値は無視されます。

+++構文

`max(<parameter>)`

+++

+++パラメーター

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* 期間
* 整数
* 小数
* 日時
* 日時のみ

+++

+++シグネチャと戻り値のタイプ

`max(<listDuration>)`

期間を返します。

`max(<listInteger>)`

期間を返します。

`max(<listDateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`max(<listDateTime>)`

日時を返します。

`max(<listDateOnly>)`

日付を返します。

`max(<listDecimal>)`

小数を返します。

`max(<decimal>,<decimal>)`

小数を返します。

`max(<duration>,<duration>)`

期間を返します。

`max(<dateTime>,<dateTime>)`

日時を返します。

`max(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`max(<integer>,<integer>)`

整数を返します。

+++

+++例

`max(@event{BarBeacon.inventory},5)`

`max([10,3,8])`

10 を返します。

`max([10,null,8])`

10 を返します。

+++

## min {#min}

リストまたは 2 つの式のいずれかで指定された一連の式の中の最小値を返します。null 値は無視されます。

+++構文

`min(<parameters>)`

+++

+++パラメーター

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* 期間
* 整数
* 小数
* 日時
* 日時のみ

+++

+++シグネチャと戻り値のタイプ

`min(<listDuration>)`

期間を返します。

`min(<listInteger>)`

期間を返します。

`min(<listDateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`min(<listDateTime>)`

日時を返します。

`min(<listDateOnly>)`

日付を返します。

`min(<listDecimal>)`

小数を返します。

`min(<decimal>,<decimal>)`

小数を返します。

`min(<duration>,<duration>)`

期間を返します。

`min(<dateTime>,<dateTime>)`

日時を返します。

`min(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`min(<integer>,<integer>)`

整数を返します。

+++

+++例

`min(@event{BarBeacon.inventory},5)`

`min([10,3,8])`

3 を返します。

`min([10,null,8])`

「8」を返します。

+++

## sum {#sum}

 一連の式の値の合計を返します。null 値は無視されます。

+++構文

`sum(<parameters>)`

+++

+++パラメーター

* listInteger
* listDecimal
* 期間
* 整数
* 小数

+++

+++シグネチャと戻り値のタイプ

`sum(<listDecimal>)`

小数を返します。

`sum(<listInteger>)`

整数を返します。

`sum(<integer>,<integer>)`

整数を返します。

`sum(<decimal>,<decimal>)`

小数を返します。

+++

+++例

`sum(@event{BarBeacon.inventory},5)`

`sum([10,3,8])`

21 を返します。

`sum([10.5,null,8.1])`

18.6 を返します。

+++

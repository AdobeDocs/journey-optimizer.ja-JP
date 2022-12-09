---
solution: Journey Optimizer
product: journey optimizer
title: Operators
description: 高度な式の演算子について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 706e2e02-9bd9-46e7-a73d-dda3c9ae4ba8
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# Operators {#operators}

演算子には、単項演算子と二項演算子の2種類があります。 左側の単項演算子と右側の単項演算子には、左向きの単項演算子があります。

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

## 重要な注意事項{#important-notes}

* 乗算 ( `*` ) を使用する場合は、両方の演算フィールドの型が整数または decimal のいずれかである必要があります。 一
   * 次の例は正しいとなります。 `3.0 * 4.0`
   * `3 * 4.0` エラーになります。

## 演算子  {#logical}

### そして

```json
<expression1> and <expression2>
```

&lt;expression1>And&lt;expression2>はブール値である必要があります。&lt;/expression2> &lt;/expression1>結果はブール値です。

一

```json
3.14 > 2 and 3.15 < 1
```

### か



```json
<expression1> or <expression2>
```

&lt;expression1>And&lt;expression2>はブール値である必要があります。&lt;/expression2> &lt;/expression1>結果はブール値です。

一

```json
3.14 > 2 or 3.15 < 1
```

### じゃない



```json
not <expression>
```

&lt;expression> ブール値である必要があります。 &lt;/expression>結果はブール値です。

一

```json
not 3.15 < 1
```

## 関係 {#comparison}

### は null



```json
<expression> is null
```

結果はブール値です。

Null は、式に評価値が含まれていないことを意味します。

一

```json
@{BarBeacon.location} is null
```

### は null ではありません。



```json
<expression> is not null
```

結果はブール値です。

Null は、式に評価値が含まれていないことを意味します。

一

```json
@{BarBeacon.location} is not null
```

### に null



```json
<expression> has null
```

&lt;expression> リストである必要があります。 &lt;/expression>結果はブール値です。

リストに含まれている null 値が少なくとも1つあることを確認する場合に便利です。

一

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

>[!NOTE]
>
>&lt;expression1>&lt;expression2>データ型のコントロールはありません。&lt;/expression2> &lt;/expression1>

一

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

>[!NOTE]
&lt;expression1>&lt;expression2>データ型のコントロールはありません。&lt;/expression2> &lt;/expression1>

結果はブール値です。

一

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

Datetime を Datetime と比較できます。

Datetimeonly は、Datetimeonly と比較することもできます。

整数または decimal は、整数または10進数の両方を使用して比較できます。

他の任意の組み合わせは禁止されています。

結果はブール値です。

一

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime を Datetime と比較できます。

Datetimeonly は、Datetimeonly と比較することもできます。

整数または decimal は、整数または10進数の両方を使用して比較できます。

他の任意の組み合わせは禁止されています。

結果はブール値です。

一

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime を Datetime と比較できます。

Datetimeonly は、Datetimeonly と比較することもできます。

整数または decimal は、整数または10進数の両方を使用して比較できます。

他の任意の組み合わせは禁止されています。

結果はブール値です。

一

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime を Datetime と比較できます。

Datetimeonly は、Datetimeonly と比較することもできます。

整数または decimal は、整数または10進数の両方を使用して比較できます。

他の任意の組み合わせは禁止されています。

結果はブール値です。

一

```json
42 <= 3.14
```

## 四捨五入 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

どちらの式も数値 (整数または decimal) である必要があります。

結果も数値になります。

一

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

どちらの式も数値 (整数または decimal) である必要があります。

結果も数値になります。

一

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

どちらの式も数値 (整数または decimal) である必要があります。

結果も数値になります。

&lt;expression2> 0以外 (0 を返す) を指定することはできません。&lt;/expression2>

一

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

どちらの式も数値 (整数または decimal) である必要があります。

結果も数値になります。

一

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

どちらの式も数値 (整数または decimal) である必要があります。

結果も数値になります。

一

```json
3 % 2 -- returns 1.
```

## 演算 {#math}

### は数値



```json
<expression> is numeric
```

式の型は integer または decimal です。

一

```json
@ is numeric
```

### は整数



```json
<expression> is integer
```

式の型は整数です。

一

```json
@ is integer
```

### 10進数



```json
<expression> is decimal
```

式の型は decimal です。

一

```json
@ is decimal
```

## 値 {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

これにより2つの式が連結されます。

1つの式は、連結されたストリングである必要があります。

一

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 古い {#date}

### +



```json
<expression> + <duration>
```

日付時刻に期間を追加するには、dateTimeOnly または duration を指定します。

一

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```

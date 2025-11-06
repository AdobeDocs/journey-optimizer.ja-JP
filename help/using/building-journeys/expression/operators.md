---
solution: Journey Optimizer
product: journey optimizer
title: 演算子
description: 高度な式で使用できる演算子について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 式, 構文, 演算子, エディター, ジャーニー
exl-id: 706e2e02-9bd9-46e7-a73d-dda3c9ae4ba8
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 100%

---

# 演算子 {#operators}

演算子には、単項演算子と二項演算子の 2 種類があります。左単項演算子と右単項演算子があります。

```json
// left-hand unary operators
// <operator> <operand> 
// operand is an expression
not (@event{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

// right-hand unary operators
// <operator> <operand> 
// operand is an expression
@event{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

// binary operators
// <operand1> <operator> <operand2>
// operand is an expression
(@event{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or (@event{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com") 
```

## 重要な注意事項{#important-notes}

* 乗算（`*`）の場合、両方の演算フィールドのタイプは整数または 10 進数で同じにする必要があります。例：
   * 以下の例は正しいです。`3.0 * 4.0`
   * `3 * 4.0` はエラーを引き起こします

* `+` 演算子を使用する場合、式を括弧で囲む必要があります。例：
   * `toDateTimeOnly(toDateTime((currentTimeInMillis()) + 1))` は正しいです
   * `toDateTimeOnly(toDateTime(currentTimeInMillis() + 1))` はエラーを引き起こします

## 論理  {#logical}

### and

```json
<expression1> and <expression2>
```

&lt;expression1> と &lt;expression2> は両方ともブール値である必要があります。結果はブール値です。

例：

```json
3.14 > 2 and 3.15 < 1
```

### or

```json
<expression1> or <expression2>
```

&lt;expression1> と &lt;expression2> は両方ともブール値である必要があります。結果はブール値です。

例：

```json
3.14 > 2 or 3.15 < 1
```

### not

```json
not <expression>
```

&lt;expression> はブール値である必要があります。結果はブール値です。

例：

```json
not 3.15 < 1
```

## 比較 {#comparison}

### is null

```json
<expression> is null
```

結果はブール値です。

null は、式に評価値がないことを意味します。

例：

```json
@event{BarBeacon.location} is null
```

### is not null

```json
<expression> is not null
```

結果はブール値です。

null は、式に評価値がないことを意味します。

例：

```json
@event{BarBeacon.location} is not null
```

### has null

```json
<expression> has null
```

&lt;expression> はリストである必要があります。結果はブール値です。

リストに少なくとも 1 つの null 値が含まれているかどうかを識別するのに役立ちます。

例：

```json
["foo", "bar", null] has null
```

true を返します

```json
["foo", "bar", ""] has null
```

&quot;&quot; が null と見なされないので、false を返します。

### ==

```json
<expression1> == <expression2>
```

>[!NOTE]
>
>&lt;expression1> と &lt;expression2> には、データタイプコントロールはありません。

例：

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### ! =

```json
<expression1> != <expression2>
```

>[!NOTE]
>
>&lt;expression1> と &lt;expression2> には、データタイプコントロールはありません。

結果はブール値です。

例：

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

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
3.14 > 42
```

### >=

```json
<expression1> >= <expression2>
```

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
42 >= 3.14
```

### &lt;

```json
<expression1> < <expression2>
```

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
42 < 3.14
```

### &lt;=

```json
<expression1> <= <expression2>
```

日時は日時と比較できます。

「日時のみ」は「日時のみ」と比較することができます。

整数と小数はどちらも、整数と小数の両方と比較できます。

その他の組み合わせは禁止されています。

結果はブール値です。

例：

```json
42 <= 3.14
```

## 算術計算 {#arithmetic}

### +

```json
<expression1> + <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
1 + 2
```

3 を返します

### -

```json
<expression1> - <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
2 - 1 
```

1 を返します

### /

```json
<expression1> / <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

&lt;expression2> は 0 以外である必要があります（0 の場合は戻り値が 0 になります）。

例：

```json
4 / 2
```

2 を返します

### *

```json
<expression1> * <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
3 * 4
```

12 を返します

### %

```json
<expression1> % <expression2>
```

両方の式は数値（整数または小数）である必要があります。

結果も数値です。

例：

```json
3 % 2
```

1 を返します。

## 数値計算 {#math}

### is numeric

```json
<expression> is numeric
```

式のタイプは整数または小数です。

例：

```json
@ is numeric
```

### is integer

```json
<expression> is integer
```

式のタイプは整数です。

例：

```json
@ is integer
```

### is decimal

```json
<expression> is decimal
```

式のタイプは小数です。

例：

```json
@ is decimal
```

## 文字列 {#string}

### +

```json
<string> + <expression>
```

```json
<expression> + <string>
```

2 つの式を連結します。

一方の式は、連結される文字列である必要があります。

例：

```json
"the current time is " + (now())
```

「現在の時刻は 2023-09-23T09:30:06.693Z です」を返します

```json
(now()) + " is the current time"
```

「2023-09-23T09:30:06.693Z は現在の時刻です」を返します

```json
"a" + "b" + "c" + 1234
```

「abc1234」を返します

## 日付 {#date}

### +

```json
<expression> + <duration>
```

日時、日時のみ、期間のいずれかに期間を連結します。

例：

```json
(toDateTime("2023-12-03T15:15:30Z")) + (toDuration("PT15M"))  
```

_dateTime_ 2023-12-03T15:30:30Z を返します

```json
(toDateTimeOnly("2023-12-03T15:15:30")) + (toDuration("PT15M"))
```

_dateTimeOnly_ 2023-12-03T15:30:30 を返します

```json
(now()) + (toDuration("PT1H"))
```

_dateTime_ （UTC タイムゾーンを使用）現在の時刻から 1 時間後を返します

```json
(toDuration("PT1H")) + (toDuration("PT1H"))
```

_duration_ PT2H を返します

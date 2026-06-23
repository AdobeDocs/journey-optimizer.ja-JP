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
TQID: https://experienceleague.adobe.com/sK2GNHkkiJ4M5V99Uucc-b68iESNW7kCNBjHVNT-dMs
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
subfeature_v2: []
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 1001
ht-degree: 54%

---

# 演算子 {#operators}

演算子には、単項演算子と二項演算子の 2 種類があります。 左単項演算子と右単項演算子があります。

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

* 乗算（`*`）の場合、両方の演算フィールドのタイプは整数または 10 進数で同じにする必要があります。 例：
   * 以下の例は正しいです。`3.0 * 4.0`
   * `3 * 4.0` はエラーを引き起こします

* `+` 演算子を使用する場合、式を括弧で囲む必要があります。 例：
   * `toDateTimeOnly(toDateTime((currentTimeInMillis()) + 1))` は正しいです
   * `toDateTimeOnly(toDateTime(currentTimeInMillis() + 1))` はエラーを引き起こします

## 論理  {#logical}

### and

```json
<expression1> and <expression2>
```

&lt;expression1> と &lt;expression2> は両方ともブール値である必要があります。 結果はブール値です。

例：

```json
3.14 > 2 and 3.15 < 1
```

### or

```json
<expression1> or <expression2>
```

&lt;expression1> と &lt;expression2> は両方ともブール値である必要があります。 結果はブール値です。

例：

```json
3.14 > 2 or 3.15 < 1
```

### not

```json
not <expression>
```

&lt;expression> はブール値である必要があります。 結果はブール値です。

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

&lt;expression> はリストである必要があります。 結果はブール値です。

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

### !=

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

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページは、ジャーニーの高度な式エディターで使用できる演算子の完全なリファレンスです。論理（`and`, `or`, `not`）、比較（`==`, `!=`, `>`, `>=`, `<`, `<=`, `is null`, `is not null`, `has null`）、算術（`+`, `-`, `*`）、数式のチェック （`is numeric`, `is integer`） `is decimal`）、文字列連結、日付算術演算子。`/`&#x200B;`%`

**インテント：**

* 論理演算子`and`、`or`、`not`を使用してブール条件を組み合わせる
* `is null` / `is not null`を使用して、フィールドまたは式の値がnullかどうかを確認します
* `has null`演算子を使用して、リスト内のnull値を検出します
* `>`、`>=`、`<`、`<=`、`==`、および`!=`を使用して、数値、日時、および日時のみの値を比較します
* `+`、`-`、`/`、`*`、`%`を使用して、数値に対して算術を実行します
* `+`演算子を使用して、dateTime、dateTimeOnlyまたはduration値に期間を追加します

**用語集：**

* **単項演算子**：単一のオペランドに適用される演算子。左（例：`not`）または右（例：`is null`） *（製品固有）*&#x200B;にすることができます
* **バイナリ演算子**:2つのオペランド （例：`and`、`==`、`+`）間に適用された演算子&#x200B;*（製品固有）*
* **にnull**&#x200B;があります。リストに少なくとも1つのnull要素&#x200B;*（product-specific）*&#x200B;が含まれている場合にtrueを返す右側単項演算子
* **は数値です/は整数です/は小数です**：式&#x200B;*（product-specific）*&#x200B;の数値サブタイプに基づいてブール値を返す型チェック演算子

**ガードレール：**

* 乗算（`*`）を使用する場合、両方のオペランドは同じ数値型（整数または両方の小数）である必要があります。型を混在すると、エラーが発生します
* 日付計算に`+`演算子を使用する場合、エラーの解析を避けるために、式を括弧で囲む必要があります
* 比較演算子（`>`, `>=`, `<`, `<=`）は、互換性のある型の間でのみ有効です。DatetimeはDatetime、DatetimeOnlyはDatetimeOnly、または数値はnumericです。他の組み合わせは使用できません
* 空の文字列`""`はnullと見なされません – `has null`は`""`を含むリストに対してfalseを返します
* `==`および`!=`演算子は、オペランド間でデータ型制御を実行しません

**用語：**

* 正規名：演算子 – 頭字語：なし – バリアント：式演算子、ジャーニー演算子
* 同義語：`and` = &quot;logical AND&quot;; `or` = &quot;logical OR&quot;; `not` = &quot;logical NOT&quot;; `%` = &quot;modulo&quot;
* 混同しないでください：`is null` （式に評価値がありません） ≠ `== null` （有効な構文ではありません）、`has null` （リストにnullが含まれています） ≠ `is null` （式そのものがnullです）

**FAQ:**

* **Q：整数に10進数を直接掛けることはできますか？**  – いいえ。`*`の両方のオペランドは同じ型である必要があります。 `3.0 * 4.0` （両方とも小数）または`3 * 4` （両方とも整数）を使用してください。
* **Q: dateTimeに15分を追加するにはどうすればよいですか？** — `(toDateTime("...")) + (toDuration("PT15M"))`を使用します。
* **Q: `is null`と`has null`の違いは何ですか？** — `is null`は、1つの式に評価値がないかどうかを確認します。`has null`は、リストに少なくとも1つのnull要素が含まれているかどうかを確認します。
* **Q: `"" has null`はtrueを返しますか？**  – いいえ。空の文字列はnullと見なされないので、結果はfalseです。
* **Q: `3 * 4.0`がエラーを引き起こすのはなぜですか？** — `*`演算子では、両方のオペランドが同じ数値型である必要があります。整数と小数を混在させることはできません。

+++

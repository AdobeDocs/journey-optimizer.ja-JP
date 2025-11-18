---
title: 演算子関数ライブラリ
description: 演算子関数ライブラリ
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 75b0b380-d9a6-418e-b9f6-e64de385ba8d
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---

# 演算子 {#operators}

## ブール関数 {#boolean-functions}

ブール関数を使用すると、様々な要素に対してブール論理を実行できます。

### および{#and}

`and` 関数は、論理積を作成するために使用されます。

**構文**

```sql
{%= query1 and query2 %}
```

**例**

次の操作は、母国がフランスで、かつ 1985 年に生まれたすべての人を返します。

```sql
{%= profile.homeAddress.country = "France" and profile.person.birthYear = 1985 %}
```

### または{#or}

`or` 関数は、論理和を作成するために使用されます。

**構文**

```sql
{%= query1 or query2 %}
```

**例**

次の操作は、母国がフランス、または 1985 年に生まれたすべての人を返します。

```sql
{%= profile.homeAddress.country = "France" or profile.person.birthYear = 1985 %}
```

<!--
## Not{#not}

The `not` (or `!`) function is used to create a logical negation.

**Syntax**

```sql
not ({QUERY})
!({QUERY})
```

**Example**

The following operation will return all people who do not have their home country as Canada.

```sql
not (homeAddress.countryISO = "CA")
```
-->

## 比較関数 {#comparison-functions}

比較関数は、様々な式と値を比較するために使用され、結果に応じて true または false を返します。

### Equals{#equals}

`=`（次に等しい）関数は、ある値または式が別の値または式と等しいかどうかを確認します。

**構文**

```sql
{%= expression = value %}
```

**例**

次の操作は、自宅住所の国がフランスかどうかを確認します。

```sql
{%= profile.homeAddress.country = "France" %}
```

### 次と等しくない{#notequal}

`!=`（次と等しくない）関数は、ある値または式が別の値または式と等しく&#x200B;**ない**&#x200B;かどうかを確認します。

**構文**

```sql
{%= expression != value %}
```

**例**

次の操作は、自宅住所の国がフランスでないかどうかを確認します。

```sql
{%= profile.homeAddress.country != "France" %}
```

### 次より大きい{#greaterthan}

`>`（次より大きい）関数は、最初の値が 2 番目の値より大きいかどうかを確認するために使用します。

**構文**

```sql
{%= expression1 > expression2 %}
```

**例**

次の操作は、1970 年より後（1970 年は含まない）に生まれた人々を定義します。

```sql
{%= profile.person.birthYear > 1970 %}
```

### 同じかそれ以上{#greaterthanorequal}

`>=`（同じかそれ以上）は、1 つ目の値が 2 つ目の値以上かどうかを確認するために使用されます。

**構文**

```sql
{%= expression1 >= expression2 %}
```

**例**

以下の操作は、1970 年以降に生まれた人々を定義します。

```sql
{%= profile.person.birthYear >= 1970 %}
```

### 次より小さい{#lessthan}

`<`（次より小さい）比較関数は、最初の値が 2 番目の値より小さいかどうかを調べるために使用されます。

**構文**

```sql
{%= expression1 < expression2 %}
```

**例**

次の操作は、2000 年より前（2000 年を含まない）に生まれた人々を定義します。

```sql
{%= profile.person.birthYear < 2000 %}
```

### 同じかそれ以下{#lessthanorequal}

`<=`（同じかそれ以下）比較関数は、最初の値が 2 番目の値以下かどうかを確認するために使用されます。

**構文**

```sql
{%= expression1 <= expression2 %}
```

**例**

次の操作は、2000 年以前に生まれた人々を定義します。

```sql
{%= profile.person.birthYear <= 2000 %}
```

**数値を使用した操作**

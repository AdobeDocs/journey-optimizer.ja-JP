---
title: 演算子関数ライブラリ
description: 演算子関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 98%

---

# 演算子 {#operators}

## ブール関数

ブール関数は、異なる要素に対してブール論理を実行するために使用します。

### And{#and}

`and` 関数は、論理積を作成するために使用されます。

**形式**

```sql
{%= query1 and query2 %}
```

**例**

次の操作は、母国がフランスで、かつ 1985 年に生まれたすべての人を返します。

```sql
{%= profile.homeAddress.country = "France" and profile.person.birthYear = 1985 %}
```

### Or{#or}

`or` 関数は、論理和を作成するために使用されます。

**形式**

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

**Format**

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





## 比較関数

比較関数は、異なる式と値を比較するために使用され、それに応じて true または false を返します。

### Equals{#equals}

`=`（equals）関数は、ある値または式が別の値または式と等しいかどうかを確認します。

**形式**

```sql
{%= expression = value %}
```

**例**

次の操作は、自宅住所の国がフランスかどうかを確認します。

```sql
{%= profile.homeAddress.country = "France" %}
```

### Not equal{#notequal}

`!=`（not equal）関数は、ある値または式が別の値または式と等しく&#x200B;**ない**&#x200B;かどうかを確認します。

**形式**

```sql
{%= expression != value %}
```

**例**

次の操作は、自宅住所の国がフランスでないかどうかを確認します。

```sql
{%= profile.homeAddress.country != "France" %}
```

### Greater than{#greaterthan}

`>`（greater than）関数は、最初の値が 2 番目の値より大きいかどうかを確認するために使用します。

**形式**

```sql
{%= expression1 > expression2 %}
```

**例**

次の操作は、1970 年より後（1970 年は含まない）に生まれた人々を定義します。

```sql
{%= profile.person.birthYear > 1970 %}
```

### Greater than or equal to{#greaterthanorequal}

`>=`（greater than or equal to）は、1 つ目の値が 2 つ目の値以上かどうかを確認するために使用されます。

**形式**

```sql
{%= expression1 >= expression2 %}
```

**例**

以下の操作は、1970 年以降に生まれた人々を定義します。

```sql
{%= profile.person.birthYear >= 1970 %}
```

### Less than{#lessthan}

`<`（less than）比較関数は、最初の値が 2 番目の値より小さいかどうかを調べるために使用されます。

**形式**

```sql
{%= expression1 < expression2 %}
```

**例**

次の操作は、2000 年より前（2000 年を含まない）に生まれた人々を定義します。

```sql
{%= profile.person.birthYear < 2000 %}
```

### Less than or equal to{#lessthanorequal}

`<=`（less than or equal to）比較関数は、最初の値が 2 番目の値以下かどうかを確認するために使用されます。

**形式**

```sql
{%= expression1 <= expression2 %}
```

**例**

次の操作は、2000 年以前に生まれた人々を定義します。

```sql
{%= profile.person.birthYear <= 2000 %}
```

**数値を使用した操作**


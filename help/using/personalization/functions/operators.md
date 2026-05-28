---
title: 演算子関数ライブラリ
description: 演算子関数ライブラリ
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 75b0b380-d9a6-418e-b9f6-e64de385ba8d
TQID: https://experienceleague.adobe.com/b4Tz4auDyWb-iaUYAie31DL5hlHh97n3rYm7EP-JjIw
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
feature_v2:
  - id: fda7be7c-b81e-42c0-95a9-616e5b893c03
subfeature_v2: []
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 308
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

### 次に等しい{#equals}

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

### Not equal{#notequal}

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

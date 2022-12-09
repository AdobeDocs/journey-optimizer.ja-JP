---
title: 演算子ライブラリ
description: 演算子ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 75b0b380-d9a6-418e-b9f6-e64de385ba8d
source-git-commit: 284d95976ab1b58aaea2a4c41db20a3ea5a9b761
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# Operators {#operators}

## ブール関数 {#boolean-functions}

ブール関数は、様々なエレメントに対してブールロジックを実行するために使用されます。

### そして{#and}

この関数は、 `and` 論理積を作成するために使用されます。

**書式**

```sql
{%= query1 and query2 %}
```

**一**

次の操作を実行すると、東京都と誕生年1985のすべての人物が返されます。

```sql
{%= profile.homeAddress.country = "France" and profile.person.birthYear = 1985 %}
```

### か{#or}

この関数は、 `or` 論理和を作成するために使用されます。

**書式**

```sql
{%= query1 or query2 %}
```

**一**

次の操作を実行すると、東京都を含むすべての人物がフランス語または誕生年1985に返されます。

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

## 比較関数 {#comparison-functions}

比較関数は、異なる式と値を比較するために使用され、true または false を返します。

### Str{#equals}

(Equals) 関数は、ある値または式が別の値または式に等しいかどうかをチェックし `=` ます。

**書式**

```sql
{%= expression = value %}
```

**一**

次の例では、住所が東京都であるかどうかを確認します。

```sql
{%= profile.homeAddress.country = "France" %}
```

### 不等号{#notequal}

(不等号) 関数は、 `!=` ある値または式が **別の値または式と等しくない** かどうかをチェックします。

**書式**

```sql
{%= expression != value %}
```

**一**

次の例では、住所が東京であるかどうかをチェックします。

```sql
{%= profile.homeAddress.country != "France" %}
```

### より大きい{#greaterthan}

(より大きい) 関数は、 `>` 最初の値が2番目の値より大きいかどうかをチェックするために使用されます。

**書式**

```sql
{%= expression1 > expression2 %}
```

**一**

次の操作を実行すると、ユーザーの出身が1970以降に定義されます。

```sql
{%= profile.person.birthYear > 1970 %}
```

### より大きいまたは等しい{#greaterthanorequal}

「より大きい」または「等しい」関数は、 `>=` 最初の値が2つ目の値以上であるかどうかをチェックするために使用されます。

**書式**

```sql
{%= expression1 >= expression2 %}
```

**一**

次の操作は、1970以降の人材の出生を定義します。

```sql
{%= profile.person.birthYear >= 1970 %}
```

### 未満{#lessthan}

(不等号) 比較関数は、 `<` 最初の値が2番目の値より小さいかどうかを調べるために使用されます。

**書式**

```sql
{%= expression1 < expression2 %}
```

**一**

次の操作を実行すると、2000より前のユーザーの出生が定義されます。

```sql
{%= profile.person.birthYear < 2000 %}
```

### 以下{#lessthanorequal}

(不等号または不等号) 比較関数は、 `<=` 最初の値が2つ目の値以下かどうかを調べるために使用されます。

**書式**

```sql
{%= expression1 <= expression2 %}
```

**一**

次の例では、2000またはそれ以前の人物出生が定義されています。

```sql
{%= profile.person.birthYear <= 2000 %}
```

**数値を含む演算**

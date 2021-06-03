---
title: 関数ライブラリ
description: 関数ライブラリ
source-git-commit: 8c58dd667ea59a17833bbe3482b1a233ac2e28fe
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 60%

---

# オブジェクト関数 {#objects}

![](../../assets/do-not-localize/badge.png)

## Isnull{#isNull}

`isNull` 関数は、オブジェクト参照が存在しないかどうかを判定します。

**形式**

```sql
{%= isNull(object) %}
```

**例**

次の操作は、その人の自宅住所が存在しないかどうかを確認します。

```sql
{%= isNull(person.homeAddress) %}
```

## isNotNull{#isNotNull}

`isNotNull` 関数は、オブジェクト参照が存在するかどうかを判定します。

**形式**

```sql
{%= isNotNull(object) %}
```

**例**

次の操作は、その人の自宅住所が存在するかどうかを確認します。

```sql
{%= isNotNull(person.homeAddress) %}
```

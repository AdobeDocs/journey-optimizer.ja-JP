---
title: オブジェクト関数ライブラリ
description: オブジェクト関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 52%

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

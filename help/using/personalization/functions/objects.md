---
title: オブジェクト関数ライブラリ
description: オブジェクト関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: ht
source-wordcount: '59'
ht-degree: 100%

---

# オブジェクト関数 {#objects}

## Is null{#isNull}

`isNull` 関数は、オブジェクト参照が存在しないかどうかを判定します。

**形式**

```sql
{%= isNull(object) %}
```

**例**

次の操作は、ユーザーの自宅の住所が存在しないかどうかを確認します。

```sql
{%= isNull(person.homeAddress) %}
```

## Is not null{#isNotNull}

`isNotNull` 関数は、オブジェクト参照が存在するかどうかを判定します。

**形式**

```sql
{%= isNotNull(object) %}
```

**例**

次の操作は、ユーザーの自宅の住所が存在するかどうかを確認します。

```sql
{%= isNotNull(person.homeAddress) %}
```

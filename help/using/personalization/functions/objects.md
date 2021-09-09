---
title: オブジェクト関数ライブラリ
description: オブジェクト関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 6ce70e32-aac3-4a2c-bfeb-c370521853ca
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: tm+mt
source-wordcount: '57'
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

---
title: オブジェクト関数ライブラリ
description: オブジェクト関数ライブラリ
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 6ce70e32-aac3-4a2c-bfeb-c370521853ca
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: ht
source-wordcount: '57'
ht-degree: 100%

---

# オブジェクト関数 {#objects}

## null である{#isNull}

`isNull` 関数は、オブジェクト参照が存在しないかどうかを判定します。

**構文**

```sql
{%= isNull(object) %}
```

**例**

次の操作は、ユーザーの自宅の住所が存在しないかどうかを確認します。

```sql
{%= isNull(person.homeAddress) %}
```

## null でない{#isNotNull}

`isNotNull` 関数は、オブジェクト参照が存在するかどうかを判定します。

**構文**

```sql
{%= isNotNull(object) %}
```

**例**

次の操作は、ユーザーの自宅の住所が存在するかどうかを確認します。

```sql
{%= isNotNull(person.homeAddress) %}
```

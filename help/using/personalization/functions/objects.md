---
title: オブジェクト関数ライブラリ
description: オブジェクト関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 6ce70e32-aac3-4a2c-bfeb-c370521853ca
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 100%

---

# オブジェクト関数 {#objects}

## null である{#isNull}

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

## null でない{#isNotNull}

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

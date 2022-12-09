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
ht-degree: 0%

---

# オブジェクト関数 {#objects}

## は null{#isNull}

この関数は、 `isNull` オブジェクト参照が存在しないかどうかを判断します。

**書式**

```sql
{%= isNull(object) %}
```

**一**

次の例では、個人の自宅住所が存在しないかどうかを確認します。

```sql
{%= isNull(person.homeAddress) %}
```

## は null ではありません。{#isNotNull}

この関数は、 `isNotNull` オブジェクト参照が存在するかどうかを判断します。

**書式**

```sql
{%= isNotNull(object) %}
```

**一**

次の操作は、個人の住所があるかどうかを確認します。

```sql
{%= isNotNull(person.homeAddress) %}
```

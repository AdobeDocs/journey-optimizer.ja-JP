---
title: 関数ライブラリ
description: 関数ライブラリ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 89%

---

# オブジェクト関数{#objects}

![](../../assets/do-not-localize/badge.png)

## Isnull

`isNull` 関数は、オブジェクト参照が存在しないかどうかを判定します。

**形式**

```sql
isNull({OBJECT})
```

**例**

次の PQL クエリは、ユーザーの自宅住所が存在しないかどうかを確認します。

```sql
isNull(person.homeAddress)
```

## isNotNull

`isNotNull` 関数は、オブジェクト参照が存在するかどうかを判定します。

**形式**

```sql
isNotNull({OBJECT})
```

**例**

次の PQL クエリは、ユーザーの自宅住所が存在するかどうかを確認します。

```sql
isNotNull(person.homeAddress)
```

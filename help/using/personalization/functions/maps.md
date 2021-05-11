---
title: 関数ライブラリ
description: 関数ライブラリ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 85%

---

# マップ関数{#maps}

![](../../assets/do-not-localize/badge.png)

[!DNL Profile Query Language] (PQL)オファーは、マップとのやり取りを容易にする機能です。

## get

`get` 関数は、特定のキーのマップの値を取得するために使用されます。

**形式**

```sql
get({MAP},{STRING})
```

**例**

次の PQL クエリは、キー `example@example.com` の ID マップの値を取得します。

```sql
get(identityMap,"example@example.com")
```

## keys

`keys` 関数は、特定のマップのすべてのキーを取得するために使用されます。

**形式**

```sql
keys({MAP})
```

**例**

次の PQL クエリは、マップ `identityMap` のすべてのキーを取得します。

```sql
keys(identityMap)
```

## values

`values` 関数は、特定のマップのすべての値を取得するために使用されます。

**形式**

```sql
values({MAP})
```

**例**

次の PQL クエリは、マップ `identityMap` のすべての値を取得します。

```sql
values(identityMap)
```

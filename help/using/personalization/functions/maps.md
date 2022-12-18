---
title: マップ関数ライブラリ
description: マップ関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: de6a8da2-55cf-4105-ba93-40c556732626
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 100%

---

# マップ関数{#maps}

パーソナライゼーションでマップ関数を使用すると、マップとのやり取りが容易になります。

## 取得{#get}

`get` 関数は、特定のキーのマップの値を取得するために使用されます。

**形式**

```sql
{%= get(map, string) %}
```

**例**

次の操作は、キー `example@example.com` の ID マップの値を取得します。

```sql
{%= get(identityMap,"example@example.com") %}
```

## キー{#keys}

`keys` 関数は、特定のマップのすべてのキーを取得するために使用されます。

**形式**

```sql
{%= keys(map) %}
```

**例**

次の操作は、マップ `identityMap` のすべてのキーを取得します。

```sql
{%= keys(identityMap) %}
```

## 値{#values}

`values` 関数は、特定のマップのすべての値を取得するために使用されます。

**形式**

```sql
{%= values(map) %}
```

**例**

次の操作は、マップ `identityMap` のすべての値を取得します。

```sql
{%= values(identityMap) %}
```

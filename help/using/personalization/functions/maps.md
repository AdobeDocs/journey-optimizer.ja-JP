---
title: 関数ライブラリのマップ
description: 関数ライブラリのマップ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: de6a8da2-55cf-4105-ba93-40c556732626
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 0%

---

# 関数のマップ{#maps}

マップ間の連携を容易にするには、パーソナル化にマップ関数を使用します。

## 取得{#get}

`get`この関数は、指定されたキーのマップの値を取得するために使用されます。

**書式**

```sql
{%= get(map, string) %}
```

**一**

次の操作では、キー `example@example.com` の id マップの値を取得します。

```sql
{%= get(identityMap,"example@example.com") %}
```

## キー{#keys}

`keys`この関数は、指定されたマップのすべてのキーを取得するために使用されます。

**書式**

```sql
{%= keys(map) %}
```

**一**

次の操作を実行すると、マップ `identityMap` のすべてのキーが取得されます。

```sql
{%= keys(identityMap) %}
```

## 指定{#values}

`values`この関数は、指定されたマップのすべての値を取得するために使用されます。

**書式**

```sql
{%= values(map) %}
```

**一**

次の操作は、マップ `identityMap` のすべての値を取得します。

```sql
{%= values(identityMap) %}
```

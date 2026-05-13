---
title: マップ関数ライブラリ
description: マップ関数ライブラリ
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: de6a8da2-55cf-4105-ba93-40c556732626
TQID: https://experienceleague.adobe.com/KeitEe0NQxxc-snCyWSGlov-OyUgiva6ddzrCTxEKSs
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 102
ht-degree: 100%

---

# マップ関数{#maps}

パーソナライゼーションでマップ関数を使用すると、マップとのやり取りが容易になります。

## 取得{#get}

`get` 関数は、特定のキーのマップの値を取得するために使用されます。

**構文**

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

**構文**

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

**構文**

```sql
{%= values(map) %}
```

**例**

次の操作は、マップ `identityMap` のすべての値を取得します。

```sql
{%= values(identityMap) %}
```

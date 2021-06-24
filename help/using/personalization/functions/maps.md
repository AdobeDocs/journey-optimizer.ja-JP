---
title: マップ関数ライブラリ
description: マップ関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: e3b7e80b72e6be71d5b38cd5507d20ad2e8ca8d4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 83%

---

# マップ関数{#maps}

パーソナライゼーションでマップ関数を使用すると、マップとのやり取りが容易になります。

## get{#get}

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

## keys{#keys}

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

## values{#values}

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

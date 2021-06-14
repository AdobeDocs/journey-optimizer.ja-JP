---
title: マップ関数ライブラリ
description: マップ関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 61%

---

# マップ関数{#maps}

![](../../assets/do-not-localize/badge.png)

[!DNL Profile Query Language]（PQL）の機能を使用すると、マップの操作が容易になります。

## get{#get}

`get` 関数は、特定のキーのマップの値を取得するために使用されます。

**形式**

```sql
{%= get(map, string) %}
```

**例**

次の操作は、キー`example@example.com`のIDマップの値を取得します。

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

次の操作は、マップ`identityMap`のすべてのキーを取得します。

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

次の操作は、マップ`identityMap`のすべての値を取得します。

```sql
{%= values(identityMap) %}
```

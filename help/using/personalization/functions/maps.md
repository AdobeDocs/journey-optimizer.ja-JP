---
title: 関数ライブラリ
description: 関数ライブラリ
source-git-commit: 8c58dd667ea59a17833bbe3482b1a233ac2e28fe
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 66%

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

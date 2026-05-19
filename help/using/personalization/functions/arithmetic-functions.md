---
title: 演算関数ライブラリ
description: 演算関数ライブラリ
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 21ef8f50-8389-4675-a8e5-0438a3eee592
TQID: https://experienceleague.adobe.com/vQcfLG40Xhz4-ebm--J875oU4o-6BXC0SvNq24OOyTk
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 180
ht-degree: 100%

---

# 演算関数 {#maths}

演算関数は、値に対する基本的な計算を実行するために使用します。

## 加算{#add}

`+`（加算）関数は、2 つの引数式の合計を見つけるために使用されます。

**構文**

```sql
{%= double + double %}
```

**例**

次の操作は、2 つの異なる製品の価格を合計します。

```sql
{%= product1.price + product2.price %}
```

## 乗算{#multiply}

`*`（乗算）関数は、2 つの引数式の積を求めるために使用されます。

**構文**

```sql
{%= double * double %}
```

**例**

次の操作は、在庫製品と製品価格を検索して、製品の総価値を算出します。

```sql
{%= product.inventory * product.price %}
```

## 減算{#substract}

`-`（減算）関数は、2 つの引数式の違いを見つけるために使用されます。

**構文**

```sql
{%= double - double %}
```

**例**

次の操作は、2 つの異なる製品の価格の違いを見つけます。

```sql
{%= product1.price - product2.price %}
```

## 除算{#divide}

`/`（除算）関数は、2 つの引数式の商を見つけるために使用されます。

**構文**

```sql
{%= double / double %}
```

**例**

次の操作は、販売された製品の合計と獲得した合計金額の比率を求めて、品目ごとの平均コストを算出します。

```sql
{%= totalProduct.price / totalProduct.sold %}
```

## 剰余{#remainder}

`%`（モジュロ/剰余）関数は、2 つの引数式を除算した後の剰余を見つけるために使用されます。

**構文**

```sql
{%= double % double %}
```

**例**

次の操作は、年齢が 5 で割り切れるかどうかを確認します。

```sql
{%= person.age % 5 = 0 %}
```

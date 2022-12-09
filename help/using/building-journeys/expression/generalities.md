---
solution: Journey Optimizer
product: journey optimizer
title: '?'
description: 高度な式エディターについて
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c9434b28-2750-4a53-985e-c4a3f940472c
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---

# 高度な式エディターのシンタックス {#syntax}

## 括弧とエクスプレッションの優先度{#parentheses-and-expression-priority}

括弧を使用すると、複雑な式を読みやすくすることができます。 _(&lt;expression>)_ はという意味 _&lt;expression>_ です。&lt;/expression> &lt;/expression>括弧を使用して、評価の順序と結合性を定義することもできます。

式は左から右に評価されます。 算術演算子のアソシエティビティは、次のように適用する必要があります。 multiplications およびディビジョンは、「追加」や「subtractions」よりも優先されます。 特定の順序を指定するには、演算子を区切るためにカッコを追加する必要があります。 例えば：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 表記 | 方式 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39; * &#39; は、「+」よりも優先されます。 2 * 10 が評価されます。</li><li>4 + 20 > 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>かっこによって優先順位が評価されます。 (4 + 2) が評価されます。</li><li> 6 * 10 > 60</li></ul> |

## 大文字と小文字の区別{#case-sensitivity}

次の例では、大文字と小文字が区別されています。

* すべての演算子 (and、or など) 小文字で記述する必要があります。 例えば、 _`<expression1>`and`<expression2>`_ は有効な式であり、式 _`<expression1>``<expression2>`_ ではありません。
* 関数名はすべて大文字と小文字が区別されます。 例えば、in segment () _は有効_ ですが、 _segment ()_ では使用できません。
* フィールド参照および定数値は大文字と小文字が区別されます。これは、演算子や関数とは異なり、言語のビルトインエレメントではありません。これはエンドユーザーによって作成されます。

## 返された式の型{#returned-expression-type}

使用しているコンテキストによっては、式エディターが別の値を返すことがあります。

| 高度な式エディターの使用方法 | 返された式の型 |
|--- |--- |
| 条件 (データソースの条件、日付条件) | 示す |
| カスタムタイマー | dateTimeOnly |
| アクションパラメーターマッピング | れ |

---
solution: Journey Optimizer
product: journey optimizer
title: 高度な式エディターの構文
description: 高度な式エディターで使用される構文について説明します。
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: 構文, エディター, ジャーニー
exl-id: c9434b28-2750-4a53-985e-c4a3f940472c
source-git-commit: 2de94e8ce3fe77399c8dc1d515ae73d58cb8f43d
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 100%

---

# 高度な式エディターの構文 {#syntax}

[高度な式エディター](expressionadvanced.md)を使用する際の構文の基本事項を以下に示します。高度な式エディターの使用例について詳しくは、[このページ](advanced-editor-use-cases.md)を参照してください。

## 括弧と式の優先度 {#parentheses-and-expression-priority}

括弧を使用すると、複雑な式が読みやすくなります。_(&lt;expression>)_ は _&lt;expression>_&#x200B;と同等です。括弧を使用して、評価順序と結合規則を定義することもできます。

式は左から右に評価されます。演算子の結合規則を適用する必要があります。乗算と除算は、加算と減算よりも優先されます。特定の順序を強制するには、括弧を追加して演算を区切る必要があります。例：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 式 | 評価結果 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>「*」は「+」よりも優先されます：2 * 10 の評価結果は → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧によって優先度が変わります：(4 + 2) の評価結果は → 6</li><li> 6 * 10 → 60</li></ul> |

## 大文字と小文字の区別 {#case-sensitivity}

大文字と小文字の区別に関する様々なルールを次に示します。

* すべての演算子（and、or など）は、小文字で記述する必要があります。例： _`<expression1>`and`<expression2>`_ は有効な式であるのに対して、_`<expression1>`AND`<expression2>`_ は有効な式ではありません。
* すべての関数名では大文字と小文字が区別されます。例：_inAudience()_ は有効なのに対して、_INAUDIENCE()_ 関数は有効ではありません。
* フィールド参照と定数値は、大文字と小文字が区別されます。（演算子や関数とは異なり）これらは言語の組み込み要素ではなく、エンドユーザーが作成します。

## 式の戻り値のタイプ {#returned-expression-type}

使用コンテキストに応じて、式エディターは異なる値を返す可能性があります。

| 高度な式エディターでの使用法 | 式の戻り値として想定されるタイプ |
|--- |--- |
| 条件（データソース条件、日付条件） | ブール値 |
| カスタムタイマー | 日時のみ |
| アクションパラメーターのマッピング | 任意 |

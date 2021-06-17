---
title: ヘルパー関数ライブラリ
description: Journey Optimizerヘルパー関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 7%

---


# テンプレート言語およびヘルパー関数 {#functionsL}

[!DNL Journey Optimizer]テンプレート言語を使用して、計算、データの書式設定または変換、条件、パーソナライゼーションのコンテキストでの操作などのデータに対して操作を実行し、操作を実行します。 [このページ](../personalization-syntax.md)では、パーソナライゼーション構文のガイドラインを説明します。

テンプレート言語は、次に示すように、式エディターのパーソナライゼーションドロップダウンリストで使用できるヘルパー関数で利用されます。

![](../assets/access-helper-functions.png)

[!DNL Journey Optimizer]式エディターでは、ヘルパー関数は次の3つのカテゴリにグループ化されます。[関数](#functions-helper)、[ヘルパー](#helper-helper)および[演算子](#operators-helper)。

## 関数{#functions-helper}

**配列関数**

<table>
    <tr>
        <td><a href="aggregation.md#average">平均</a></td><td>この関数は、配列内の選択された値すべての算術平均を返します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#in">In</a></td><td>この関数は、項目が配列またはリストのメンバーであるかどうかを判断するために使用されます</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#min">Minimum</a></td><td>この関数は、配列内の選択された値すべての最小値を返します</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count">Count</a></td><td>この関数は、指定された配列内の要素数を返します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#includes">Includes</a></td><td>この関数は、配列またはリストに特定の項目が含まれているかどうかを判定します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#notin">Not in</a></td><td>この関数は、項目が配列またはリストのメンバーでないかどうかを判定します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#distinct">Distinct</a></td><td>この関数は、重複する値が削除された配列またはリストから値を取得します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#intersects">Intersects</a></td><td>この関数は、2つの配列またはリストに、共通メンバーが1つ以上あるかどうかを判断します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#subset">Subset of</a></td><td>この関数は、特定の配列（配列A）が別の配列（配列B）のサブセットであるか、つまり、配列Aのすべての要素が配列Bの要素であるかを判定します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#head">First item</a></td><td>この関数は、配列またはリスト内の最初の項目を返します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#last-n">配列の最後のn</a></td><td>この関数は、指定した数値式に基づいて昇順で並べ替えられた場合、配列の最後の「N」項目を返します</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#sum">Sum</a></td><td>この関数は、配列内の選択された値の合計を返します</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#first-n">配列の最初のn</a></td><td>この関数は、指定した数値式に基づいて昇順で並べ替えられた場合、配列の最初の「N」項目を返します</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#max">Maximum</a></td><td>この関数は、配列内の選択された値すべての最大値を返します</td>
    </tr>
    <tr>
    <td><a href="arrays-list.md#superset">Superset of</a></td><td>この関数は、特定の配列（配列A）が別の配列（配列B）のスーパーセットであるか、つまり、配列Aに配列Bのすべての要素が含まれているかを判定します</td>
    </tr>
</table>


**マップ関数**

<table>
    <tr>
        <td><a href="maps.md#get">get</a></td><td>この関数は、特定のキーのマップの値を取得するために使用されます</td>
    </tr>
    <tr>
        <td><a href="maps.md#keys">keys</a></td><td>この関数は、特定のマップのすべてのキーを取得するために使用されます</td>
    </tr>
    <tr>
        <td><a href="maps.md#values">values</a></td><td>この関数は、指定されたマップのすべての値を取得します</td>
    </tr>
</table>

**オブジェクト関数**

<table>
    <tr>
        <td><a href="objects.md#isNotNull">isNotNull</a></td><td>この関数は、オブジェクト参照が存在するかどうかを判断するために使用されます</td>
    </tr>
    <tr>
        <td><a href="objects.md#isNull">Isnull</a></td><td>この関数は、オブジェクト参照が存在しないかどうかを判断するために使用されます</td>
    </tr>
</table>

**文字列関数**

<table>
    <tr>
        <td><a href="string.md#camelCase">キャメルケース</a></td><td>この関数は、文字列の各単語の最初の文字を大文字にするために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#concat">Concat</a></td><td>この関数は、2つの文字列を1つに結合するために使用します</td>
    </tr>
    <tr>
        <td><a href="string.md#contains">contains</a></td><td>この関数は、文字列が指定の部分文字列を含むかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotContain">doesNotContain</a></td><td>この関数は、文字列が指定の部分文字列を含んでいないかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotEndWith">doesNotEndWith</a></td><td>この関数は、文字列が指定の部分文字列で終わらないかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotStartWith">doesNotStartWith</a></td><td>この関数は、文字列が指定の部分文字列で始まらないかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#encode64">エンコード64</a></td><td>この関数は、文字列のエンコードまたはデコードに使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#endsWith">endsWith</a></td><td>この関数は、文字列が指定の部分文字列で終わるかどうかを判定するために使用されます</td>
    </tr>
        </tr>
    <tr>
        <td><a href="string.md#equals">equals</a></td><td>この関数は、文字列が指定の部分文字列で始まらないかどうか（大文字と小文字を区別）を判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#equalsIgnoreCase">大文字と小文字が等しい</a></td><td>この関数は、文字列が指定の部分文字列で始まらないかどうかを、大文字と小文字を区別せずに判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#extractEmailDomain">Eメールドメインの抽出</a></td><td>この関数は、電子メールアドレスのドメインを抽出するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#isEmpty">IsEmpty</a></td><td>この関数は、文字列または式が空かどうかを確認するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#leftTrim">左トリミング</a></td><td>この関数は、文字列の先頭から空白を削除します</td>
    </tr>
    <tr>
        <td><a href="string.md#length">Length</a></td><td>この関数は、文字列または式の文字数を取得するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#like">like</a></td><td>この関数は、文字列が指定のパターンと一致するかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#lower">小文字</a></td><td>この関数は、文字列を小文字に変換します</td>
    </tr>
    <tr>
        <td><a href="string.md#matches">matches</a></td><td>この関数は、文字列が特定の正規表現と一致するかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#notEqualTo">等しくない</a></td><td>この関数は、文字列が指定の文字列に等しくないかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#regexGroup">正規表現グループ</a></td><td>この関数は、指定された正規表現に基づいて特定の情報を抽出するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#replace">置換</a></td><td>この関数は、文字列内の特定の部分文字列を別の部分文字列で置き換えます</td>
    </tr>
    <tr>
        <td><a href="string.md#replaceAll">すべてを置換</a></td><td>この関数は、「target」に一致するテキストのすべての部分文字列を、指定されたリテラルの「replacement」文字列に置き換えます。</td>
    </tr>
    <tr>
        <td><a href="string.md#rightTrim">右トリミング</a></td><td>この関数は、文字列の末尾から空白を削除します </td>
    </tr>
    <tr>
        <td><a href="string.md#split">Split</a></td><td>この関数は、文字列を特定の文字で分割するために使用します</td>
    </tr>
    <tr>
        <td><a href="string.md#startsWith">startsWith</a></td><td>この関数は、文字列が指定の部分文字列で始まるかどうかを判定するために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#titleCase">単語の先頭のみ大文字</a></td><td>この関数は、文字列の各単語の最初の文字を大文字にするために使用されます</td>
    </tr>
    <tr>
        <td><a href="string.md#trim">トリミング</a></td><td>この関数は、文字列の先頭と末尾の空白を削除します</td>
    </tr>
    <tr>
        <td><a href="string.md#upper">大文字</a></td><td>この関数は、文字列を大文字に変換します</td>
    </tr>
</table>


## ヘルパー{#helper-helper}

ヘルパーの詳細は、[このページ](helpers.md)で説明しています。


<table>
    <tr>
        <td><a href="helpers.md#each">Each</a></td><td>この関数は、配列を反復するために使用されます</td>
    </tr>
    <tr>
        <td><a href="helpers.md#if-function">If</a></td><td>この関数は、条件付きブロックの定義に使用されます。式の評価がtrueを返した場合、ブロックがレンダリングされます</td>
    </tr>
    <tr>
        <td><a href="helpers.md#let">Let</a></td><td>この関数を使用すると、式を変数として保存し、後でクエリで使用できます</td>
    </tr>
   <tr>
        <td><a href="helpers.md#unless">Unless</a></td><td>この関数は、条件付きブロックの定義に使用されます。式の評価がfalseを返した場合、ブロックがレンダリングされます</td>
    </tr>
    <tr>
        <td><a href="helpers.md#with">With</a></td><td>この関数は、template-partの評価トークンを変更するために使用されます</td>
    </tr>
</table>

## 演算子{#operators-helper}

### 演算関数 {#arithmetic-helper}

演算関数は、値に対して基本的な計算を実行するために使用されます。

<table>
    <tr>
        <td><a href="arithmetic-functions.md#add">追加</a></td><td>この演算子は、2つの引数式の合計を見つけるために使用されます</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#divide">除算</a></td><td>この演算子は、2つの引数式の商を見つけるために使用されます</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#multiply">乗算</a></td><td>この演算子は、2つの引数式の積を見つけるために使用されます</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#remainder">剰余</a> </td><td>この演算子は、2つの引数式を除算した後の剰余を見つけるために使用されます</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#substract">減算</a> </td><td>この演算子は、2つの式の違いを見つけます</td>
    </tr>
</table>


### ブール関数

ブール関数 は、異なる要素に対してブール論理を実行するために使用されます。

<table>
    <tr>
        <td><a href="operators.md#and">And</a></td><td>この演算子は論理積を作成します</td>
    </tr>
    <tr>
        <td><a href="operators.md#not">If</a></td><td>この演算子は、指定された条件がtrueかどうかに応じて式を解決します</td>
    </tr>
    <tr>
        <td><a href="operators.md#not">Not</a></td><td>この演算子は論理否定を作成します</td>
    </tr>
    <tr>
        <td><a href="operators.md#or">または</a></td><td>この演算子は論理和を作成します</td>
    </tr>
</table>


### 比較関数

比較関数 を使用して異なる式と値を比較し、適宜trueまたはfalseを返します。

<table>
    <tr>
        <td><a href="operators.md#and">イコール</a></td><td>この操作は、値が等しいかどうかを確認します</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthan">より大きい</a></td><td>この演算子は、最初の値が2番目の値より大きいかどうかを確認します</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthanorequal">以上</a></td><td>この演算子は、最初の値が2番目の値以上かどうかを確認します</td>
    </tr>
    <tr>
        <td><a href="operators.md#notequal">等しくない</a></td><td>この演算子は、指定された式が値に等しくないかどうかを確認します</td>
    </tr>
    <tr>
        <td><a href="operators.md#lessthanorequal">次よりも小さいか等しい</a> </td><td>この演算子は、最初の値が2番目の値より小さいか等しいかどうかを確認します</td>
    </tr>
</table>


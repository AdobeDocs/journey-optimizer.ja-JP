---
product: journey optimizer
title: 文字列関数
description: 文字列関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 文字列，関数，式，ジャーニー，テキスト，操作
version: Journey Orchestration
source-git-commit: d58319d687d113ce680c415524fdea0400cb38f0
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 84%

---

# 文字列関数 {#string-functions}

文字列関数を使用すると、ジャーニー式内のテキスト値を操作および操作できます。 これらの機能は、カスタマージャーニーでのテキスト処理、検証、変換および分析に不可欠です。

次の必要がある場合は、文字列関数を使用します。

* 複数のテキスト値の連結と結合
* 特定のテキストパターンまたは部分文字列の検索
* 大文字と小文字を区別する一致または大文字と小文字を区別しない一致を持つ文字列を比較
* 部分文字列操作を使用してテキストの一部を抽出する
* テキストを大文字または小文字に変換する
* 文字列が空であるか、特定の値を含んでいるかを確認します
* テキストパターンを新しい値に置き換える
* 文字列を配列に分割して、さらに処理する
* 正規表現に対してテキストを検証します

文字列関数は、包括的なテキスト操作機能を提供し、ジャーニー式のテキストコンテンツに基づく高度なデータ処理と条件付きロジックを可能にします。

## concat {#concat}

2 つの文字列パラメーターまたは 1 つの文字列リストを連結します。

+++構文

`concat(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| 文字列 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`concat(<string>,<string>)`

`concat(<listString>)`

文字列を返します。

+++

+++例

`concat("Hello","World")`

「HelloWorld」を返します。

`concat(["Hello"," ","World"])`

「Hello World」を返します。

+++

## contain {#contain}

1 番目の引数文字列に 2 番目の引数文字列が含まれているかどうかを確認します。

+++構文

`contain(<parameters>)`

+++

+++パラメーター

* 文字列

+++

+++シグネチャと戻り値のタイプ

`contain(<string>,<string>)`

ブール値を返します。

+++

+++例

`contain("rowing is great", "great")`

true を返します。

+++

## containIgnoreCase {#containIgnoreCase}

2 番目の引数文字列が最初の引数文字列に含まれているかどうかを、大文字と小文字の区別をせずに確認します。

+++構文

`containIgnoreCase(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 検索文字列 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`containIgnoreCase(<string>,<string>)`

ブール値を返します。

+++

+++例

`containIgnoreCase("rowing is great", "GREAT")`

true を返します。

+++

## endWith {#endWith}

2 番目のパラメーターが最初のパラメーターの末尾にある場合、true を返します。

+++構文

`endWith(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 末尾の文字列 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`endWith(<string>,<string>)`

ブール値を返します。

+++

+++例

`endWith("Hello World", "World")`

true を返します。

`endWith("Hello World", "Hello")`

false を返します。

+++

## endWithIgnoreCase {#endWithIgnoreCase}

最初の引数文字列が特定の文字列（2 番目の引数文字列）で終わっているかどうかを、大文字と小文字の区別をせずに確認します。

+++構文

`endWithIgnoreCase(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 末尾の文字列 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`endWithIgnoreCase(<string>,<string>)`

ブール値を返します。

+++

+++例

`endWithIgnoreCase("rowing is great", "AT")`

true を返します。

+++

## equalIgnoreCase {#equalIgnoreCase}

大文字と小文字を区別せずに、最初の引数文字列と 2 番目の引数文字列を比較します。

+++構文

`equalIgnoreCase(<parameters>)`

+++

+++パラメーター

* 文字列

+++

+++シグネチャと戻り値のタイプ

`equalIgnoreCase(<string>,<string>)`

ブール値を返します。

+++

+++例

`equalIgnoreCase("rowing is great", "rowing is GREAT")`

true を返します。

+++

## indexOf {#indexOf}

2 番目のパラメーターが最初に現れる（最初の引数内の）位置を返します。一致するものがない場合は「-1」を返します。

+++構文

`indexOf(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| string | String |
| 指定値 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`indexOf(<string>,<string>)`

整数を返します。

+++

+++例

`indexOf("Hello", "l")`

2 を返します。

説明：

「Hello」で「l」が最初に出現するのは位置 2 です。

+++

## isEmpty {#isEmpty}

パラメーター内の文字列に文字が含まれていない場合は true を返します。

+++構文

`isEmpty(<parameters>)`

+++

+++パラメーター

* 文字列

+++

+++シグネチャと戻り値のタイプ

`isEmpty(<string>)`

ブール値を返します。

+++

+++例

`isEmpty("")`

true を返します。

`isEmpty("Hello World")`

false を返します。

+++

## isNotEmpty {#isNotEmpty}

パラメーター内の文字列が空でない場合、true を返します。

+++構文

`isNotEmpty(<parameters>)`

+++

+++パラメーター

* 文字列

+++

+++シグネチャと戻り値のタイプ

`isNotEmpty(<string>)`

ブール値を返します。

+++

+++例

`isNotEmpty("")`

false を返します。

`isNotEmpty("hello")`

true を返します。

+++

## lastIndexOf {#lastIndexOf}

2 番目のパラメータが最後に現れる（最初の引数内の）位置を返します。一致するものがない場合は -1 を返します。

+++構文

`lastIndexOf(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| string | String |
| 指定値 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`lastIndexOf(<string>,<string>)`

整数を返します。

+++

+++例

`lastIndexOf("Hello", "l")`

3 を返します。

説明：

「Hello」で「l」が最後に出現するのは位置 3 です。

+++

## length {#length}

パラメーター内の文字列式の文字数を返します。

+++構文

`length(<parameters>)`

+++

+++パラメーター

* 文字列

+++

+++シグネチャと戻り値のタイプ

`length(<string>)`

整数を返します。

+++

+++例

`length("Hello World")`

11 を返します。

+++

## lower {#lower}

パラメーターを小文字にしたものを返します。

+++構文

`lower(<parameter>)`

+++

+++パラメーター

* 文字列

+++

+++シグネチャと戻り値のタイプ

`lower(<string>)`

文字列を返します。

+++

+++例

`lower("A")`

「a」を返します。

+++

## matchRegExp {#matchRegExp}

1 番目のパラメーターの文字列が 2 番目のパラメーターの正規表現と一致する場合、true を返します。 詳しくは、[このページ](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)を参照してください。

+++構文

`matchRegExp(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|--- |--- |
| 文字列 | 文字列 |
| 正規表現 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`matchRegExp(<string>,<string>)`

ブール値を返します。

+++

+++例

`matchRegExp("12345", "\\d+")`

true を返します。

+++

## notEqualIgnoreCase {#notEqualIgnoreCase}

最初の引数の文字列と 2 番目の引数の文字列が異なるかどうかを、大文字と小文字の区別を無視して確認します。

+++構文

`notEqualIgnoreCase(<parameters>)`

+++

+++パラメーター

* 文字列

+++

+++シグネチャと戻り値のタイプ

`notEqualIgnoreCase(<string>,<string>)`

ブール値を返します。

+++

+++例

`notEqualIgnoreCase(@event{iOSPushPermissionAllowed.device.model}, "iPad")`

+++

## replace {#replace}

ターゲット文字列に一致する最初の出現箇所を、ベース文字列内の置換文字列で置き換えます。

置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

+++構文

`replace(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base（ベース文字列） | 文字列 |
| target（ターゲット文字列） | 文字列（RegExp） |
| replacement（置換文字列） | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`replace(<base>,<target>,<replacement>)`

文字列を返します。

+++

+++例

`replace("Hello World", "l", "x")`

「Hexlo World」を返します。

**正規表現の例：**

ターゲットパラメーターは RegExp なので、置き換える文字列に応じて、一部の文字をエスケープする必要が生じる場合があります。次に例を示します。

* 評価する文字列：`|OFFER_A|OFFER_B`
* プロファイル属性 `#{ExperiencePlatform.myFieldGroup.profile.myOffers}` によって提供されます
* 置き換える文字列：`|OFFER_A`
* `''` によって置き換えられた文字列
* `|` 文字の前に `\\` を追加する必要があります。

式は次の通りです。

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

返される文字列は `|OFFER_B` です。

指定した属性から置き換える文字列を構築することもできます。

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`

+++

## replaceAll {#replaceAll}

ターゲット文字列に一致するすべての出現箇所をベース文字列内の置換文字列で置き換えます。

置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

+++構文

`replaceAll(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base（ベース文字列） | 文字列 |
| target（ターゲット文字列） | 文字列（RegExp） |
| replacement（置換文字列） | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

文字列を返します。

+++

+++例

`replaceAll("Hello World", "l", "x")`

「Hexxo Worxd」を返します。

ターゲットパラメーターは RegExp なので、置き換える文字列に応じて、一部の文字をエスケープする必要が生じる場合があります。[replace](#replace) 関数の例を参照してください。

+++

## split {#split}

1 番目の引数文字列を区切り記号列（2 番目の引数文字列：正規表現を指定可能）で分割して、文字列（トークン）のリストを作成します。

+++構文

`split(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 入力文字列 | 文字列 |
| 区切り記号列 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`split(<input string>, <separator string>)`

文字列リストを返します。

+++

+++例

`split("A_B_C", "_")`

`["A","B","C"]` を返します。

イベントフィールド「event.appVersion」の値が「20.45.2.3434」の場合の例

`split(@event{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` を返します

+++

## startWith {#startWith}

2 番目のパラメーターが最初のパラメーターの接頭辞にある場合は、true を返します。

+++構文

`startWith(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| 接頭辞 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`startWith(<string>,<string>)`

ブール値を返します。

+++

+++例

`startWith("Hello World", "Hello")`

true を返します。

`startWith("Hello World", "World")`

false を返します。

+++

## startWithIgnoreCase {#startWithIgnoreCase}

大文字と小文字を区別しない場合に 2 番目のパラメーターが最初のパラメーターの接頭辞としてある場合は、true を返します。

+++構文

`startWithIgnoreCase(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| 接頭辞 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

+++

+++例

`startWithIgnoreCase("rowing is great", "RO")`

true を返します。

+++

## substr {#substr}

文字列式の開始インデックスと終了インデックスの間にある部分文字列を返します。終了インデックスが指定されていない場合は、文字列式の開始インデックスと末尾の間にある部分文字列を返します。

+++構文

`substr(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-------------|----------|
| 文字列 | 文字列 |
| beginIndex | 整数 |
| 終了インデックス | 整数 |

+++

+++シグネチャと戻り値のタイプ

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

文字列を返します。

+++

+++例

`substr("Hello World",6)`

「World」を返します。

`substr("Hello World", 0, 5)`

「Hello」を返します。

+++

## trim {#trim}

先頭と末尾のスペースを削除します。

+++構文

`trim(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |

+++

+++シグネチャと戻り値のタイプ

`trim(<string>)`

文字列を返します。

+++

+++例

`trim(" Hello ")`

「Hello」を返します。

+++

## upper {#upper}

パラメーターを大文字にしたものを返します。

+++構文

`upper(<parameters>)`

+++

+++シグネチャと戻り値のタイプ

`upper(<string>)`

文字列を返します。

+++

+++例

`upper("b")`

「B」を返します。

+++

## uuid {#uuid}

ランダムな UUID（Universal Unique IDentifier）を生成します。

+++構文

`uuid()`

+++

+++パラメーター 

この関数にはパラメーターは必要ありません。

+++

+++シグネチャと戻り値のタイプ

`uuid()`

文字列を返します。

+++

+++例

`uuid()`

「79e70b7f-8a85-400b-97a1-9f9826121553」を返します。

+++


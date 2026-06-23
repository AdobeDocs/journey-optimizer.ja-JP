---
product: journey optimizer
title: 文字列関数
description: 文字列関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 文字列, 関数, 式, ジャーニー, テキスト, 操作
version: Journey Orchestration
exl-id: 8186c564-56fa-417a-afd3-8e479e5b23b9
TQID: https://experienceleague.adobe.com/wrP3c7l3uHzN6w3l-fXBQOSb5Tx2NuW-6iyogKpDPc8
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
subfeature_v2: []
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 1668
ht-degree: 68%

---

# 文字列関数 {#string-functions}

文字列関数を使用すると、ジャーニー式内でテキスト値を操作して作業できます。 これらの関数は、カスタマージャーニーでのテキストの処理、検証、変換、分析に不可欠です。

文字列関数は、次の操作が必要な場合に使用します。

* 複数のテキスト値を連結して組み合わせ（[concat](#concat)）
* 特定のテキストパターンまたは部分文字列を検索（[contain](#contain)、[containIgnoreCase](#containIgnoreCase)、[indexOf](#indexOf)、[lastIndexOf](#lastIndexOf)、[matchRegExp](#matchRegExp)）
* 大文字と小文字を区別または区別しない一致で文字列を比較（[equalIgnoreCase](#equalIgnoreCase)、[notEqualIgnoreCase](#notEqualIgnoreCase)）
* 文字列の先頭と末尾を確認（[startWith](#startWith)、[startWithIgnoreCase](#startWithIgnoreCase)、[endWith](#endWith)、[endWithIgnoreCase](#endWithIgnoreCase)）
* 部分文字列演算を使用してテキストの一部を抽出（[substr](#substr)）
* テキストを大文字または小文字に変換（[upper](#upper)、[lower](#lower)、[trim](#trim)）
* 文字列が空であるか、特定の値を含んでいるかを確認（[isEmpty](#isEmpty)、[isNotEmpty](#isNotEmpty)）
* テキストパターンを新しい値に置換（[replace](#replace)、[replaceAll](#replaceAll)）
* 文字列を配列に分割してさらに処理（[split](#split)）
* 文字列の長さを取得（[length](#length)）または一意の識別子を生成（[uuid](#uuid)）

文字列関数は、包括的なテキスト操作機能を提供し、ジャーニー式のテキストコンテンツに基づいて高度なデータ処理と条件付きロジックを可能にします。

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

2 番目のパラメーターが最初に現れる（最初の引数内の）位置を返します。 一致するものがない場合は「-1」を返します。

+++構文

`indexOf(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
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

`isEmpty(<null>)`

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

2 番目のパラメータが最後に現れる（最初の引数内の）位置を返します。 一致するものがない場合は「-1」を返します。

+++構文

`lastIndexOf(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
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

**RegExp を使用した例：**

ターゲットパラメーターは RegExp なので、置き換える文字列に応じて、一部の文字をエスケープする必要が生じる場合があります。 次に例を示します。

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

ターゲットパラメーターは RegExp なので、置き換える文字列に応じて、一部の文字をエスケープする必要が生じる場合があります。 例について詳しくは、[replace](#replace) 関数を参照してください。

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

文字列式の開始インデックスと終了インデックスの間にある部分文字列を返します。 終了インデックスが指定されていない場合は、文字列式の開始インデックスと末尾の間にある部分文字列を返します。

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

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、AJO ジャーニー式で使用できるすべての文字列関数について説明します。テキスト検索、比較、変換、抽出、検証、置換、分割、一意のID生成を対象としています。

**インテント：**
* `concat`を使用して2つ以上の文字列を連結する
* `contain`または`containIgnoreCase`を使用して、文字列内の部分文字列（大文字と小文字を区別または区別しない）を検索します
* `equalIgnoreCase`または`notEqualIgnoreCase`を使用して大文字と小文字を無視しながら、2つの文字列を比較します
* `startWith`、`endWith`およびそれらの大文字と小文字を区別しないバリアントを使用して、文字列が特定の接頭辞または接尾辞で始まるか終了するかを確認します
* `substr`を使用してインデックス位置で部分文字列を抽出する
* `replace`または`replaceAll`を使用して、文字列内のパターンの最初またはすべての出現を置換します
* `split`を使用して、文字列を区切り記号でトークンのリストに分割します
* `uuid`を使用して、一意のIDが必要な場合にランダム UUIDを生成します
* `isEmpty`または`isNotEmpty`を使用して、文字列が空か空でないかを確認します

**用語集：**
* **RegExp**: `replace`、`replaceAll`、`matchRegExp`でターゲットパラメーターとして使用される正規表現パターン – 特殊文字は`\\`でエスケープする必要があります
* **UUID**: Universal Unique IDentifier — ランダムに生成された文字列識別子が`uuid()`によって返されました
* **substr**：開始インデックスとオプションの終了インデックス （ゼロ ベース）を指定して、文字列の一部を抽出します

**ガードレール：**
* `replace`および`replaceAll`の`target` パラメーターはRegExpとして扱われます。特殊文字（`|`、`.`など）は`\\`でエスケープする必要があります
* `replace`は最初の一致する出現のみを置き換えます。`replaceAll`を使用してすべての出現を置き換えます
* `isEmpty`はnull値に対してfalseを返します（trueではありません）。nullは空の文字列とは見なされません
* 一致が見つからなかった場合、`indexOf`と`lastIndexOf`は–1を返します
* 文字列インデックスの位置は0から始まります（最初の文字は0の位置です）

**用語：**
* 正規名：文字列関数 – Acronym: none – 変種：テキスト関数、文字列操作関数
* 同義語：&quot;contain&quot; = &quot;substring check&quot;; &quot;split&quot; = &quot;tokenize string&quot;; &quot;trim&quot; = &quot;strip whitespace&quot;
* 混乱しないでください：&quot;replace&quot; （最初の出現のみ） ≠ &quot;replaceAll&quot; （すべての出現）
* 「indexOf」（最初の出現位置）≠「lastIndexOf」（最後の出現位置）は混同しないでください
* 混同しないでください：&quot;isEmpty&quot; （0長の文字列の場合はtrue） ≠ null チェック （nullの場合はisEmptyがfalseを返します）
* 混同しないでください：&quot;equalIgnoreCase&quot; （等しい無視ケースの場合はtrueを返します） ≠ &quot;notEqualIgnoreCase&quot; （異なる無視ケースの場合はtrueを返します）

**FAQ:**
* **Q：大文字と小文字を区別せずに、文字列に部分文字列が含まれているかどうかを確認するにはどうすればよいですか？** — `containIgnoreCase("myString", "searchTerm")`を使用します。検索語が見つかった場合はtrueを返します。
* **Q: `replace`と`replaceAll`の違いは何ですか？** — `replace`は最初の一致するオカレンスのみを置換し、`replaceAll`は文字列内のすべてのオカレンスを置換します。
* **Q: `replace`で`|`文字をエスケープする必要があるのはなぜですか？** — ターゲットパラメーターは正規表現として扱われます。`|`は特殊なRegExp文字であり、リテラルパイプとして扱うには`\\|`としてエスケープする必要があります。
* **Q: `isEmpty`はnullに対してtrueを返しますか？**  – いいえ、`isEmpty`はnullに対してfalseを返します。0長の文字列`""`に対してのみtrueを返します。
* **Q: 「20.45.2.3434」のようなバージョン文字列からメジャーバージョン番号を抽出するにはどうすればよいですか？** — `getListItem(split(@event{event.appVersion}, "\\."), 0)`を使用してドットで分割し、最初の要素を取得します。
* **Q: ジャーニー式で一意のIDを生成するにはどうすればよいですか？** — `uuid()`を使用します。これは、パラメーターが不要なランダムに生成されたUUID文字列を返します。

+++

---
title: 文字列関数ライブラリ
description: 文字列関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 8674ef9e-261b-49d9-800e-367f9f7ef979
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '1846'
ht-degree: 100%

---

# 文字列関数 {#string}

パーソナライゼーションエディターで文字列関数を使用する方法を説明します。

## キャメルケース {#camelCase}

`camelCase` 関数は、文字列の各単語の最初の文字を大文字にします。

**構文**

```sql
{%= camelCase(string)%}
```

**例**

次の関数は、プロファイルの住所の最初の文字を大文字にします。

```sql
{%= camelCase(profile.homeAddress.street) %}
```

## 次の場所の文字コード {#char-code-at}

`charCodeAt` 関数は、JavaScript の charCodeAt 関数と同様に、文字の ASCII 値を返します。文字列と整数（文字の位置を定義する）を入力引数として受け取り、対応する ASCII 値を返します。

**構文**

```sql
{%= charCodeAt(string,int) %}: int
```

**例**

次の関数は、o の ASCII 値（111）を返します。

```sql
{%= charCodeAt("some", 1)%}
```

## 連結 {#concate}

`concat` 関数は、2 つの文字列を 1 つに結合します。

**構文**

```sql
{%= concat(string,string) %}
```

**例**

次の関数は、プロファイルの国と市区町村を 1 つの文字列に組み合わせます。

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

## 次を含む {#contains}

`contains` 関数は、文字列が指定の部分文字列を含んでいるかどうかを判定するために使用されます。

**構文**

```sql
{%= contains(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `STRING_1` | チェックの実行対象となる文字列です。 |
| `STRING_2` | 最初の文字列内で検索する文字列です。 |
| `CASE_SENSITIVE` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

* 次の関数は、プロファイルの名に A （大文字または小文字）が含まれているかどうかを確認します。この場合は「true」が返され、そうでない場合は「false」が返されます。

  ```sql
  {%= contains(profile.person.name.firstName, "A", false) %}
  ```

* 次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが「2010@gm」という文字列を含んでいるかどうかを判定します。

  ```sql
  {%= contains(profile.person.emailAddress,"2010@gm") %}
  ```

## 次を含まない{#doesNotContain}

`doesNotContain` 関数は、文字列が指定の部分文字列を含んでいないかどうかを判定するために使用されます。

**構文**

```sql
{%= doesNotContain(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `STRING_1` | チェックの実行対象となる文字列です。 |
| `STRING_2` | 最初の文字列内で検索する文字列です。 |
| `CASE_SENSITIVE` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが「2010@gm」という文字列を含んでいないかどうかを判定します。

```sql
{%= doesNotContain(profile.person.emailAddress,"2010@gm")%}
```


## 次で終わらない{#doesNotEndWith}

`doesNotEndWith` 関数は、文字列が指定の部分文字列で終わらないかどうかを判定するために使用されます。

**構文**

```sql
{%= doesNotEndWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが「.com」で終わらないかどうかを判定します。

```sql
doesNotEndWith(person.emailAddress,".com")
```

## 次で始まらない{#doesNotStartWith}

`doesNotStartWith` 関数は、文字列が指定の部分文字列で始まらないかどうかを判定するために使用されます。

**構文**

```sql
{%= doesNotStartWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が「Joe」で始まらないかどうかを判定します。

```sql
{%= doesNotStartWith(person.name,"Joe")%}
```

## エンコード 64{#encode64}

`encode64` 関数は、個人情報（PI）を URL などに含める必要がある場合に、個人情報を保持する文字列をエンコードするために使用します。

**構文**

```sql
{%= encode64(string) %}
```

## 次で終わる{#endsWith}

`endsWith` 関数は、文字列が指定の部分文字列で終わるかどうかを判定するために使用されます。

**構文**

```sql
{%= endsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが「.com」で終わるかどうかを判定します。

```sql
{%= endsWith(person.emailAddress,".com") %}
```


## 次に等しい{#equals}

`equals` 関数は、文字列が指定の文字列に等しいかどうかを判定するために使用します。

**構文**

```sql
{%= equals(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が「John」かどうかを判定します。

```sql
{%=equals(profile.person.name,"John") %}
```

## 等しい (大文字と小文字を区別しない){#equalsIgnoreCase}

`equalsIgnoreCase` 関数は、大文字と小文字を区別せずに、文字列が指定の文字列に等しいかどうかを判定するために使用します。

**構文**

```sql
{%= equalsIgnoreCase(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別せずに、名前が「John」かどうかを判定します。

```sql
{%= equalsIgnoreCase(profile.person.name,"John") %}
```

## 電子メールドメインを抽出 {#extractEmailDomain}

`extractEmailDomain` 関数は、メールアドレスのドメインを抽出するために使用します。

**構文**

```sql
{%= extractEmailDomain(string) %}
```

**例**

次のクエリは、個人のメールアドレスのメールドメインを抽出します。

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

## 通貨の書式設定 {#format-currency}

`formatCurrency` 関数は、2 番目の引数で文字列として渡されたロケールに応じて、任意の数値を対応する言語に依存する通貨表現に変換するために使用します。

**構文**

```sql
{%= formatCurrency(number/double,string) %}: string
```

**例**

このクエリは £56.00 を返します

```sql
{%= formatCurrency(56L,"en_GB") %}
```

## URL ホストを取得 {#get-url-host}

`getUrlHost` 関数は、URL のホスト名を取得するために使用されます。

**構文**

```sql
{%= getUrlHost(string) %}: string
```

**例**

```sql
{%= getUrlHost("https://www.myurl.com/contact") %}
```

「www.myurl.com」を返します

## URL パスを取得 {#get-url-path}

`getUrlPath` 関数は、URL のドメイン名の後のパスを取得するために使用されます。

**構文**

```sql
{%= getUrlPath(string) %}: string
```

**例**

```sql
{%= getUrlPath("https://www.myurl.com/contact.html") %}
```

「/contact.html」を返します

## URL プロトコルを取得 {#get-url-protocol}

`getUrlProtocol` 関数は、URL のプロトコルを取得するために使用されます。

**構文**

```sql
{%= getUrlProtocol(string) %}: string
```

**例**

```sql
{%= getUrlProtocol("https://www.myurl.com/contact.html") %}
```

「http」を返します

## インデックス {#index-of}

`indexOf` 関数は、2 番目のパラメーターが最初に現れる（最初の引数内の）位置を返すために使用されます。一致するものがない場合は「-1」を返します。

**構文**

```sql
{%= indexOf(STRING_1, STRING_2) %}: integer
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初のパラメーターで検索する文字列 |

**例**

```sql
{%= indexOf("hello world","world" ) %}
```

「6」を返します。

## 空である {#isEmpty}

`isEmpty` 関数は、文字列が空かどうかを判断するために使用します。

**構文**

```sql
{%= isEmpty(string) %}
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。それ以外の場合は、「false」を返します。

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

## 空でない {#is-not-empty}

`isNotEmpty` 関数は、文字列が空でないかどうかを判定するために使用されます。

**構文**

```sql
{= isNotEmpty(string) %}: boolean
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。それ以外の場合は、「false」を返します。

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

## 最後のインデックス {#last-index-of}

`lastIndexOf` 関数は、2 番目のパラメーターが最後に現れる（最初の引数内の）位置を返すために使用されます。一致するものがない場合は「-1」を返します。

**構文**

```sql
{= lastIndexOf(STRING_1, STRING_2) %}: integer
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初のパラメーターで検索する文字列 |

**例**

```sql
{%= lastIndexOf("hello world","o" ) %}
```

「7」を返します。

## 左トリミング {#leftTrim}

`leftTrim` 関数は、文字列の先頭から空白を削除するために使用します。

**構文**

```sql
{%= leftTrim(string) %}
```

## 長さ {#length}

`length` 関数は、文字列または式の文字数を取得するために使用します。

**構文**

```sql
{%= length(string) %}
```

**例**

次の関数は、プロファイルの市区町村名の長さを返します。

```sql
{%= length(profile.homeAddress.city) %}
```

## 類似{#like}

`like` 関数は、文字列が指定のパターンと一致するかどうかを判定するために使用されます。

**構文**

```sql
{%= like(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列列と照合される式です。式の作成に使用できる特殊文字として、`%` と `_` の 2 つがサポートされています。 <ul><li>`%` は、0 個以上の文字を表すために使用されます。</li><li>`_` は、1 文字を表すために使用されます。</li></ul> |

**例**

次のクエリでは、「es」というパターンを含む住所の市区町村をすべて取得します。

```sql
{%= like(profile.homeAddress.city, "%es%")%}
```

## 小文字{#lower}

`lowerCase` 関数は、文字列を小文字に変換します。

**構文**

```sql
{%= lowerCase(string) %}
```

**例**

この関数は、プロファイルの名を小文字に変換します。

```sql
{%= lowerCase(profile.person.name.firstName) %}
```

## 一致{#matches}

`matches` 関数は、文字列が特定の正規表現と一致するかどうかを判定するために使用されます。正規表現でのパターンマッチングについて詳しくは、[こちらのドキュメント](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)を参照してください。

**構文**

```sql
{%= matches(STRING_1, STRING_2) %}
```

**例**

次のクエリでは、大文字と小文字を区別せずに、人の名前が「John」で始まるかどうかを判定します。

```sql
{%= matches(person.name.,"(?i)^John") %}
```

## マスク {#mask}

`Mask` 関数は、文字列の一部を「X」の文字に置き換えるために使用されます。

**構文**

```sql
{%= mask(string,integer,integer) %}
```

**例**

次のクエリでは、「123456789」文字列を「X」の文字に置き換えます（最初と最後の 2 文字を除きます）。

```sql
{%= mask("123456789",1,2) %}
```

このクエリは `1XXXXXX89` を返します。

## MD5 {#md5}

`md5` 関数は、文字列の md5 ハッシュを計算して返すために使用されます。

**構文**

```sql
{%= md5(string) %}: string
```

**例**

```sql
{%= md5("hello world") %}
```

「5eb63bbbe01eeed093cb22bb8f5acdc3」を返します。

## 次と等しくない{#notEqualTo}

`notEqualTo` 関数は、文字列が指定の文字列に等しくないかどうかを判定するために使用されます。

**構文**

```sql
{%= notEqualTo(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が「John」でないかどうかを判定します。

```sql
{%= notEqualTo(profile.person.name,"John") %}
```

## 等しくない (大文字と小文字を区別しない) {#not-equal-with-ignore-case}

`notEqualWithIgnoreCase` 関数は、大文字と小文字を区別せずに、2 つの文字列を比較するために使用されます。

**構文**

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別せずに、ユーザーの名前が「john」でないかどうかを判定します。

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

## 正規表現グループ{#regexGroup}

`Group` 関数は、指定された正規表現に基づいて特定の情報を抽出するために使用されます。

**構文**

```sql
{%= regexGroup(STRING, EXPRESSION, GROUP) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING}` | チェックの実行対象となる文字列です。 |
| `{EXPRESSION}` | 最初の文字列列と照合する正規表現です。 |
| `{GROUP}` | 照合する式のグループです。 |

**例**

次のクエリは、メールアドレスからドメイン名を抽出するために使用します。

```sql
{%= regexGroup(emailAddress,"@(\\w+)", 1) %}
```

## 置換 {#replace}

`replace` 関数は、文字列内の特定の部分文字列を別の部分文字列で置き換えるために使用します。

**構文**

```sql
{%= replace(STRING_1,STRING_2,STRING_3) %}:string
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | 部分文字列を置き換える必要がある文字列です。 |
| `{STRING_2}` | 置き換える部分文字列。 |
| `{STRING_3}` | 置換する部分文字列。 |

**例**

```sql
{%= replace("Hello John, here is your monthly newsletter!","John","Mark") %}
```

「Hello Mark, here is your monthly newsletter!」を返します。

## すべて置換{#replaceAll}

`replaceAll` 関数は、「regex」式に一致するテキストのすべてのサブ文字列を、指定されたリテラルの「replacement」文字列に置き換えるために使用します。正規表現には「\」と「+」の特別な処理があり、すべての正規表現は PQL エスケープ戦略に従います。置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

**構文**

```sql
{%= replaceAll(string,string,string) %}
```

>[!NOTE]
>
> 2 番目の引数として使用される式が特殊な正規表現文字である場合は、2 つのバックスラッシュ（`//`）を使用します。特殊な正規表現文字は次のとおりです：[.、+、*、?、^、$、(、)、[、]、{、}、|、\]
> 
> 詳しくは、[Oracleのドキュメント](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html){_blank}を参照してください。
>

## 右トリミング {#rightTrim}

`rightTrim` 関数は、文字列の末尾から空白を削除するために使用します。

**構文**

```sql
{%= rightTrim(string) %}
```

## 分割 {#split}

`split` 関数は、文字列を特定の文字で分割する場合に使用します。

**構文**

```sql
{%= split(string,string) %}
```

## 次で始まる{#startsWith}

`startsWith` 関数は、文字列が指定の部分文字列で始まるかどうかを判定するために使用されます。

**構文**

```sql
{%= startsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が「Joe」で始まるかどうかを判定します。

```sql
{%= startsWith(person.name,"Joe") %}
```

## 文字列を日付に {#string-to-date}

`stringToDate` 関数は、文字列値を日時値に変換します。 日時の文字列表現とフォーマッターの文字列表現の 2 つの引数を取ります。

**構文**

```sql
{= stringToDate("date-time value","formatter" %}
```

**例**

```sql
{= stringToDate("2023-01-10 23:13:26", "yyyy-MM-dd HH:mm:ss") %}
```

## 文字列を整数に {#string-to-integer}

`string_to_integer` 関数は、文字列値を整数値に変換するために使用されます。

**構文**

```sql
{= string_to_integer(string) %}: int
```

## 文字列から数値へ {#string-to-number}

`stringToNumber` 関数は、文字列を数値に変換するために使用されます。無効な入力の出力と同じ文字列を返します。

**構文**

```sql
{%= stringToNumber(string) %}: double
```

## 部分文字列 {#sub-string}

`Count string` 関数は、開始インデックスと終了インデックスの間の文字列式の部分文字列を返すために使用されます。
**構文**

```sql
{= substr(string, integer, integer) %}: string
```

## タイトルケース{#titleCase}

**titleCase** 関数は、文字列の各単語の最初の文字を大文字にするために使用します。

**構文**

```sql
{%= titleCase(string) %}
```

**例**

その人物が「Washington high street」に住んでいる場合、この関数は「Washington high street」を返します。

```sql
{%= titleCase(profile.person.location.Street) %}
```

## ブール値に {#to-bool}

`toBool` 関数は、引数の値を、型に応じてブール値に変換するために使用されます。

**構文**

```sql
{= toBool(string) %}: boolean
```

## 日時に {#to-date-time}

`toDateTime` 関数は、文字列を日付型に変換するために使用されます。無効な入力に対する出力として、エポック日付を返します。

**構文**

```sql
{%= toDateTime(string, string) %}: date-time
```

## 日時のみに {#to-date-time-only}

`toDateTimeOnly` 関数は、引数の値を日時のみの値に変換するために使用されます。無効な入力に対する出力として、エポック日付を返します。この関数は、文字列、日付、長さおよび整数のフィールドタイプを受け入れます。

**構文**

```sql
{%= toDateTimeOnly(string/date/long/int) %}: date-time
```

## トリミング {#trim}

**trim** 関数は、文字列の先頭と末尾にあるすべての空白を削除します。

**構文**

```sql
{%= trim(string) %}
```

## 大文字{#upper}

**upperCase** 関数は、文字列を大文字に変換します。

**構文**

```sql
{%= upperCase(string) %}
```

**例**

この関数は、プロファイルの姓を大文字に変換します。

```sql
{%= upperCase(profile.person.name.lastName) %}
```

## URL デコード {#url-decode}

`urlDecode` 関数は、URL エンコードされた文字列をデコードするために使用されます。

**構文**

```sql
{%= urlDecode(string) %}: string
```

## URL エンコード {#url-encode}

`Count only null` 関数は、文字列を URL エンコードするために使用されます。

**構文**

```sql
{%= urlEncode(string) %}: string
```

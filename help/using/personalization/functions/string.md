---
title: 文字列関数ライブラリ
description: 文字列関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 8674ef9e-261b-49d9-800e-367f9f7ef979
source-git-commit: 284d95976ab1b58aaea2a4c41db20a3ea5a9b761
workflow-type: tm+mt
source-wordcount: '1686'
ht-degree: 77%

---

# 文字列関数 {#string}

式エディターで文字列関数を使用する方法を説明します。

## Camel Case {#camelCase}

`camelCase` 関数は、文字列の各単語の最初の文字を大文字にします。

**形式**

```sql
{%= camelCase(string)%}
```

**例**

次の関数は、プロファイルの住所の最初の文字を大文字にします。

```sql
{%= camelCase(profile.homeAddress.street) %}
```

## Concat {#concate}

`concat` 関数は、2 つの文字列を 1 つに結合します。

**形式**

```sql
{%= concat(string,string) %}
```

**例**

次の関数は、プロファイルの国と市区町村を 1 つの文字列に組み合わせます。

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

## contains {#contains}

`contains` 関数は、文字列が指定の部分文字列を含んでいるかどうかを判定するために使用されます。

**形式**

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

## Does not contain{#doesNotContain}

`doesNotContain` 関数は、文字列が指定の部分文字列を含んでいないかどうかを判定するために使用されます。

**形式**

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


## Does not end with{#doesNotEndWith}

`doesNotEndWith` 関数は、文字列が指定の部分文字列で終わらないかどうかを判定するために使用されます。

**形式**

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

## Does not start with{#doesNotStartWith}

`doesNotStartWith` 関数は、文字列が指定の部分文字列で始まらないかどうかを判定するために使用されます。

**形式**

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

## Encode 64{#encode64}

`encode64` 関数は、個人情報（PI）を URL などに含める必要がある場合に、個人情報を保持する文字列をエンコードするために使用します。

**形式**

```sql
{%= encode64(string) %}
```

## Ends with{#endsWith}

`endsWith` 関数は、文字列が指定の部分文字列で終わるかどうかを判定するために使用されます。

**形式**

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


## Equals{#equals}

`equals` 関数は、文字列が指定の文字列に等しいかどうかを判定するために使用します。

**形式**

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

## Equals Ignore Case{#equalsIgnoreCase}

`equalsIgnoreCase` 関数は、大文字と小文字を区別せずに、文字列が指定の文字列に等しいかどうかを判定するために使用します。

**形式**

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

## Extract Email Domain {#extractEmailDomain}

`extractEmailDomain` 関数は、メールアドレスのドメインを抽出するために使用します。

**形式**

```sql
{%= extractEmailDomain(string) %}
```

**例**

次のクエリは、個人のメールアドレスのメールドメインを抽出します。

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

## URL ホストを取得 {#get-url-host}

この `getUrlHost` 関数は、URL のホスト名を取得するために使用されます。

**形式**

```sql
{%= getUrlHost(string) %}: string
```

**例**

```sql
{%= getUrlHost("http://www.myurl.com/contact") %}
```

&quot;www.myurl.com&quot;を返します

## URL パスを取得 {#get-url-path}

この `getUrlPath` 関数は、URL のドメイン名の後にパスを取得するために使用されます。

**形式**

```sql
{%= getUrlPath(string) %}: string
```

**例**

```sql
{%= getUrlPath("http://www.myurl.com/contact.html") %}
```

&quot;/contact.html&quot;を返します

## URL プロトコルを取得 {#get-url-protocol}

この `getUrlProtocol` 関数は、URL のプロトコルを取得するために使用されます。

**形式**

```sql
{%= getUrlProtocol(string) %}: string
```

**例**

```sql
{%= getUrlProtocol("http://www.myurl.com/contact.html") %}
```

「http」を返します

## インデックス {#index-of}

この `indexOf` 関数は、2 番目のパラメーターの最初の値の（最初の引数内の）位置を返すために使用されます。 一致するものがない場合は -1 を返します。

**形式**

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

6 を返します。

## Is empty {#isEmpty}

この `isEmpty` 関数は、文字列が空かどうかを判定するために使用されます。

**形式**

```sql
{%= isEmpty(string) %}
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。それ以外の場合は、「false」を返します。

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

## Is Not Empty（空ではない） {#is-not-empty}

この `isNotEmpty` 関数は、文字列が空でないかどうかを判定するために使用されます。

**形式**

```sql
{= isNotEmpty(string) %}: boolean
```

**例**

次の関数は、プロファイルの携帯電話番号が空でない場合に「true」を返します。 それ以外の場合は、「false」を返します。

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

## 最後のインデックス {#last-index-of}

この `lastIndexOf` 関数は、2 番目のパラメーターの最後の値の（最初の引数内の）位置を返すために使用されます。 一致するものがない場合は -1 を返します。

**形式**

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

7 を返します。

## Left trim {#leftTrim}

`leftTrim` 関数は、文字列の先頭から空白を削除するために使用します。

**形式**

```sql
{%= leftTrim(string) %}
```

## Length {#length}

`length` 関数は、文字列または式の文字数を取得するために使用します。

**形式**

```sql
{%= length(string) %}
```

**例**

次の関数は、プロファイルの市区町村名の長さを返します。

```sql
{%= length(profile.homeAddress.city) %}
```

## like{#like}

`like` 関数は、文字列が指定のパターンと一致するかどうかを判定するために使用されます。

**形式**

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

## Lower Case{#lower}

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

## matches{#matches}

`matches` 関数は、文字列が特定の正規表現と一致するかどうかを判定するために使用されます。正規表現でのパターンマッチングについて詳しくは、[こちらのドキュメント](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)を参照してください。

**形式**

```sql
{%= matches(STRING_1, STRING_2) %}
```

**例**

次のクエリでは、大文字と小文字を区別せずに、人の名前が「John」で始まるかどうかを判定します。

```sql
{%= matches(person.name.,"(?i)^John") %}
```

## mask（#mask）

`Mask` 関数は、文字列の一部を「X」の文字に置き換えるために使用されます。

**形式**

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

この `md5` 関数は、文字列の md5 ハッシュを計算して返すために使用されます。

**形式**

```sql
{%= md5(string) %}: string
```

**例**

```sql
{%= md5("hello world") %}
```

「5eb63bbe01eed093cb22bb8f5acdc3」を返します。

## notEqualTo{#notEqualTo}

`notEqualTo` 関数は、文字列が指定の文字列に等しくないかどうかを判定するために使用されます。

**形式**

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

## 次と等しくない（大文字と小文字を区別しない） {#not-equal-with-ignore-case}

この `notEqualWithIgnoreCase` 関数は、大文字と小文字を区別せずに、2 つの文字列を比較するために使用されます。

**形式**

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、人の名前が「john」でないかどうかを判定し、大文字と小文字を区別しません。

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

## 正規表現グループ{#regexGroup}

`Group` 関数は、指定された正規表現に基づいて特定の情報を抽出するために使用されます。

**形式**

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
{%= regexGroup(emailAddress,"@(\w+)", 1) %}
```

## Replace {#replace}

`replace` 関数は、文字列内の特定の部分文字列を別の部分文字列で置き換えるために使用します。

**形式**

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

## Replace All{#replaceAll}

`replaceAll` 関数は、「target」に一致するテキストのすべてのサブ文字列を、指定されたリテラルの「replacement」文字列に置き換えるために使用します。置換は、文字列の先頭から末尾に向けておこなわれます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

**形式**

```sql
{%= replaceAll(string,string,string) %}
```

## Right trim {#rightTrim}

`rightTrim` 関数は、文字列の末尾から空白を削除するために使用します。

**形式**

```sql
{%= rightTrim(string) %}
```

## Split {#split}

`split` 関数は、文字列を特定の文字で分割する場合に使用します。

**形式**

```sql
{%= split(string,string) %}
```

## Starts with{#startsWith}

`startsWith` 関数は、文字列が指定の部分文字列で始まるかどうかを判定するために使用されます。

**形式**

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

## 文字列を整数に {#string-to-integer}

この `string_to_integer` 関数は、文字列値を整数値に変換するために使用されます。

**形式**

```sql
{= string_to_integer(string) %}: int
```

## 文字列から数値へ {#string-to-number}

この `stringToNumber` 関数は、文字列を数値に変換するために使用されます。 無効な入力の出力と同じ文字列を返します。

**形式**

```sql
{%= stringToNumber(string) %}: double
```

## サブ文字列 {#sub-string}

この `Count string` 関数は、begin インデックスと end インデックスの間の文字列式のサブ文字列を返すために使用されます。
**形式**

```sql
{= substr(string, integer, integer) %}: string
```

## Title Case{#titleCase}

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

この `toBool` 関数は、引数の値を、型に応じてブール値に変換するために使用します。

**形式**

```sql
{= toBool(string) %}: boolean
```

## 日時に {#to-date-time}

この `toDateTime` 関数は、文字列を日付に変換するために使用されます。 無効な入力に対する出力として、エポック日を返します。

**形式**

```sql
{%= toDateTime(string, string) %}: date-time
```

## 日時のみに {#to-date-time-only}

この `toDateTimeOnly` 関数は、引数の値を日時のみの値に変換するために使用します。 無効な入力に対する出力として、エポック日を返します。

**形式**

```sql
{%= toDateTimeOnly(string) %}: date-time
```

## Trim{#trim}

**trim** 関数は、文字列の先頭と末尾にあるすべての空白を削除します。

**構文**

```sql
{%= trim(string) %}
```

## Upper Case{#upper}

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

## url デコード {#url-decode}

この `urlDecode` 関数は、url エンコードされた文字列をデコードするために使用されます。

**形式**

```sql
{%= urlDecode(string) %}: string
```

## URL エンコード {#url-encode}

この `Count only null` 関数は、文字列を url エンコードするために使用されます。

**形式**

```sql
{%= urlEncode(string) %}: string
```

---
title: 文字列関数ライブラリ
description: 文字列関数ライブラリ
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Experienced
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 99%

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

## Is empty {#isEmpty}

`isEmpty` 関数は、文字列が空かどうかを判断するために使用します。

**形式**

```sql
{%= isEmpty(string) %}
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。 それ以外の場合は、「false」を返します。

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

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
{%= replace(string,string,string) %}
```

**例**

次の関数。

```sql

```


## Replace All{#replaceAll}

`replaceAll` 関数は、「target」に一致するテキストのすべてのサブ文字列を、指定されたリテラルの「replacement」文字列に置き換えるために使用します。 置換は、文字列の先頭から末尾に向けておこなわれます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

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

<!--
**Example**

The following function .

```sql

```

-->

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

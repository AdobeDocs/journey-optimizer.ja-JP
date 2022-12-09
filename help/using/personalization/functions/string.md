---
title: ストリング関数ライブラリ
description: ストリング関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 8674ef9e-261b-49d9-800e-367f9f7ef979
source-git-commit: 1d9fc184bb67362aac608e9816fe3afe64eb055c
workflow-type: tm+mt
source-wordcount: '1678'
ht-degree: 0%

---

# ストリング関数 {#string}

式エディターで文字列関数を使用する方法について説明します。

## Camel ケース {#camelCase}

この関数は `camelCase` 、ストリングの各単語の最初の文字を大文字にします。

**書式**

```sql
{%= camelCase(string)%}
```

**一**

次の関数は、プロファイルの住所に含まれる単語の最初の文字を大文字にします。

```sql
{%= camelCase(profile.homeAddress.street) %}
```

## 連結 {#concate}

この関数は、2つの `concat` ストリングを1つに結合します。

**書式**

```sql
{%= concat(string,string) %}
```

**一**

次の関数は、1つのストリング内のプロファイルの市区町村と国名を組み合わせます。

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

## さ {#contains}

この関数を使用して、 `contains` ストリングに特定の部分文字列が含まれているかどうかを判断します。

**書式**

```sql
{%= contains(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 指定 | つい |
| --------- | ----------- |
| `STRING_1` | チェックを実行する文字列。 |
| `STRING_2` | 最初のストリング内で検索するストリングです。 |
| `CASE_SENSITIVE` | チェックが大文字と小文字を区別するかどうかを指定するオプションのパラメーター。 指定できる値は次のとおりです。 true (デフォルト)/false。 |

**例**

* 次の関数は、プロファイルの最初の名前に A 文字が含まれているかどうかを調べます (大文字または小文字)。 このような場合は、「true」を返します。それ以外の場合は false を返します。

   ```sql
   {%= contains(profile.person.name.firstName, "A", false) %}
   ```

* 次の例では、ユーザーの電子メールアドレスに「2010@gm」というストリングが含まれている場合に、大文字と小文字が区別されます。

   ```sql
   {%= contains(profile.person.emailAddress,"2010@gm") %}
   ```

## がありません{#doesNotContain}

この関数は、 `doesNotContain` ストリングに指定されたサブストリングが含まれていないかどうかを判別するために使用されます。

**書式**

```sql
{%= doesNotContain(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 指定 | つい |
| --------- | ----------- |
| `STRING_1` | チェックを実行する文字列。 |
| `STRING_2` | 最初のストリング内で検索するストリングです。 |
| `CASE_SENSITIVE` | チェックが大文字と小文字を区別するかどうかを指定するオプションのパラメーター。 指定できる値は次のとおりです。 true (デフォルト)/false。 |

**一**

次の例では、ユーザーの電子メールアドレスに文字列 &quot;2010@gm&quot; が含まれていない場合に、大文字と小文字が区別されます。

```sql
{%= doesNotContain(profile.person.emailAddress,"2010@gm")%}
```


## で終わらない{#doesNotEndWith}

この関数は、 `doesNotEndWith` ストリングの末尾に指定された部分文字列が含まれていないかどうかを判別するために使用されます。

**書式**

```sql
{%= doesNotEndWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリング内で検索するストリングです。 |
| `{CASE_SENSITIVE}` | チェックが大文字と小文字を区別するかどうかを指定するオプションのパラメーター。 指定できる値は次のとおりです。 true (デフォルト)/false。 |

**一**

次の例では、差出人の電子メールアドレスの末尾に「.com」が付いていない場合に、大文字と小文字を区別しています。

```sql
doesNotEndWith(person.emailAddress,".com")
```

## で始まらない{#doesNotStartWith}

この関数は、 `doesNotStartWith` ストリングが特定の部分文字列で始まらないことを確認するために使用されます。

**書式**

```sql
{%= doesNotStartWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリング内で検索するストリングです。 |
| `{CASE_SENSITIVE}` | チェックが大文字と小文字を区別するかどうかを指定するオプションのパラメーター。 指定できる値は次のとおりです。 true (デフォルト)/false。 |

**一**

次の例では、人物の名前が「Joe」で始まらない場合に、大文字と小文字が区別されています。

```sql
{%= doesNotStartWith(person.name,"Joe")%}
```

## エンコード64{#encode64}

この関数は、 `encode64` URL に含まれている場合に、作成者情報 (PI) を保存するためにストリングをエンコードするために使用されます。

**書式**

```sql
{%= encode64(string) %}
```

## で終わる{#endsWith}

この関数は、 `endsWith` ストリングが指定された部分文字列で終わるかどうかを調べるために使用されます。

**書式**

```sql
{%= endsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリング内で検索するストリングです。 |
| `{CASE_SENSITIVE}` | チェックが大文字と小文字を区別するかどうかを指定するオプションのパラメーター。 指定できる値は次のとおりです。 true (デフォルト)/false。 |

**一**

次の例では、人物の電子メールアドレスが「.com」で終わる場合に、大文字と小文字を区別しています。

```sql
{%= endsWith(person.emailAddress,".com") %}
```


## Str{#equals}

`equals`この関数を使用して、指定したストリングと大文字小文字の区別が一致するかどうかを判断します。

**書式**

```sql
{%= equals(STRING_1, STRING_2) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリングと比較するストリングです。 |

**一**

次の例では、人物の名前が「John」である場合に、大文字と小文字を区別しています。

```sql
{%=equals(profile.person.name,"John") %}
```

## 大文字と小文字を区別{#equalsIgnoreCase}

この関数を使用して `equalsIgnoreCase` 、大文字と小文字を区別せずに、指定したストリングとストリングが等しいかどうかを判別します。

**書式**

```sql
{%= equalsIgnoreCase(STRING_1, STRING_2) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリングと比較するストリングです。 |

**一**

次のクエリーは、人物の名前が「John」の場合、大文字と小文字を区別せずに判別します。

```sql
{%= equalsIgnoreCase(profile.person.name,"John") %}
```

## 電子メールドメインの抽出 {#extractEmailDomain}

`extractEmailDomain`この関数は、電子メールアドレスのドメインを抽出するために使用されます。

**書式**

```sql
{%= extractEmailDomain(string) %}
```

**一**

次のクエリーは、個人用電子メールアドレスの電子メールドメインを抽出します。

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

## Url ホストの取得 {#get-url-host}

`getUrlHost`この関数は、URL のホスト名を取得するために使用されます。

**書式**

```sql
{%= getUrlHost(string) %}: string
```

**一**

```sql
{%= getUrlHost("http://www.myurl.com/contact") %}
```

&quot;Www.myurl.com&quot; を返します。

## Url パスを取得します。 {#get-url-path}

`getUrlPath`この関数は、URL のドメイン名の後にあるパスを取得するために使用されます。

**書式**

```sql
{%= getUrlPath(string) %}: string
```

**一**

```sql
{%= getUrlPath("http://www.myurl.com/contact.html") %}
```

「/Contact.html」を返します。

## Get url protocol {#get-url-protocol}

`getUrlProtocol`この関数は、URL のプロトコルを取得するために使用されます。

**書式**

```sql
{%= getUrlProtocol(string) %}: string
```

**一**

```sql
{%= getUrlProtocol("http://www.myurl.com/contact.html") %}
```

「Http」を返します。

## インデックスの作成 {#index-of}

`indexOf`この関数を使用して、2番目のパラメーターが最初に出現する位置の位置 (最初の引数) を返します。一致するアイテムがない場合は、-1 を返します。

**書式**

```sql
{%= indexOf(STRING_1, STRING_2) %}: integer
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のパラメーターで検索するストリング |

**一**

```sql
{%= indexOf("hello world","world" ) %}
```

6を返します。

## が空 {#isEmpty}

この関数は、 `isEmpty` ストリングが空かどうかを判別するために使用されます。

**書式**

```sql
{%= isEmpty(string) %}
```

**一**

次の関数は、プロファイルの携帯電話番号が空の場合は true を返します。 それ以外の場合は、false を返します。

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

## は空白ではありません。 {#is-not-empty}

この関数は、 `isNotEmpty` ストリングが空でないかどうかを判別するために使用されます。

**書式**

```sql
{= isNotEmpty(string) %}: boolean
```

**一**

次の関数は、プロファイルの携帯電話番号が空でない場合は true を返します。 それ以外の場合は、false を返します。

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

## 最後のインデックス {#last-index-of}

`lastIndexOf`この関数を使用して、2番目のパラメーターが最後に出現した位置の (最初の引数内の) 位置を返します。一致するアイテムがない場合は、-1 を返します。

**書式**

```sql
{= lastIndexOf(STRING_1, STRING_2) %}: integer
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のパラメーターで検索するストリング |

**一**

```sql
{%= lastIndexOf("hello world","o" ) %}
```

7を返します。

## 左トリム {#leftTrim}

この関数は、 `leftTrim` ストリングの先頭から空白を削除するために使用されます。

**書式**

```sql
{%= leftTrim(string) %}
```

## 長さ {#length}

`length`この関数は、ストリングまたは式の文字数を取得するために使用されます。

**書式**

```sql
{%= length(string) %}
```

**一**

次の関数は、プロファイルの市区町村名の長さを返します。

```sql
{%= length(profile.homeAddress.city) %}
```

## という感じで{#like}

この関数は、 `like` 指定したパターンにストリングが一致するかどうかを判別するために使用されます。

**書式**

```sql
{%= like(STRING_1, STRING_2) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリングと比較する式。 式 `%` を作成するためにサポートされている特殊文字は、およびを `_` 使用できます。 <ul><li>`%` は、0個以上の文字を表すために使用されます。</li><li>`_` は、1つの文字を表すために使用されます。</li></ul> |

**一**

次のクエリーは、プロファイルに &quot;es&quot; が含まれているすべての都市を取得します。

```sql
{%= like(profile.homeAddress.city, "%es%")%}
```

## 小文字{#lower}

この関数は、 `lowerCase` ストリングを小文字に変換します。

**?**

```sql
{%= lowerCase(string) %}
```

**一**

この関数は、プロファイルの最初の名前を小文字に変換します。

```sql
{%= lowerCase(profile.person.name.firstName) %}
```

## 該当{#matches}

この関数は、 `matches` ストリングが特定の正規表現に一致するかどうかを判別するために使用されます。 正規表現での一致パターンについて詳しくは、このドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html) を [ 参照してください。

**書式**

```sql
{%= matches(STRING_1, STRING_2) %}
```

**一**

次の例では、人物の名前が &quot;John&quot; で始まる場合に、大文字と小文字が区別されません。

```sql
{%= matches(person.name.,"(?i)^John") %}
```

## 隠す {#mask}

`Mask`この関数は、ストリングの一部を「X」文字に置き換えるために使用されます。

**書式**

```sql
{%= mask(string,integer,integer) %}
```

**一**

次のクエリーは、最初と最後の2文字を除外して、「123456789」という文字を「X」という文字列に置き換えます。

```sql
{%= mask("123456789",1,2) %}
```

クエリーが戻り `1XXXXXX89` ます。

## ハッシュ {#md5}

`md5`この関数は、ストリングの md5 ハッシュを計算し、返すために使用されます。

**書式**

```sql
{%= md5(string) %}: string
```

**一**

```sql
{%= md5("hello world") %}
```

&quot;5eb63bbb223c8f5acdc8f5acdc3&quot; という値を返します。

## が不等号{#notEqualTo}

`notEqualTo`この関数を使用して、指定したストリングと一致するストリングがないかどうかを判別します。

**書式**

```sql
{%= notEqualTo(STRING_1, STRING_2) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリングと比較するストリングです。 |

**一**

次の例では、人名が &quot;John&quot; でない場合に、大文字と小文字が区別されます。

```sql
{%= notEqualTo(profile.person.name,"John") %}
```

## は無視されます。等しくない {#not-equal-with-ignore-case}

この関数は、 `notEqualWithIgnoreCase` 大文字と小文字を区別するために使用されます。

**書式**

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリングと比較するストリングです。 |

**一**

次のクエリーは、人物の名前が「john」ではなく、大文字と小文字が区別されていないかどうかを判別します。

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

## 正規表現グループ{#regexGroup}

`Group`この関数は、指定された正規表現に基づいて特定の情報を抽出するために使用されます。

**書式**

```sql
{%= regexGroup(STRING, EXPRESSION, GROUP) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING}` | チェックを実行する文字列。 |
| `{EXPRESSION}` | 最初のストリングと一致する正規表現を指定します。 |
| `{GROUP}` | 比較対象となる条件式グループ。 |

**一**

次のクエリーは、電子メールアドレスからドメイン名を抽出するために使用されます。

```sql
{%= regexGroup(emailAddress,"@(\\w+)", 1) %}
```

## 置き {#replace}

`replace`この関数を使用して、ストリング内の特定の部分を別の部分文字列に置き換えます。

**書式**

```sql
{%= replace(STRING_1,STRING_2,STRING_3) %}:string
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | 部分文字列を置換する必要があるストリングです。 |
| `{STRING_2}` | 置換する部分を変更します。 |
| `{STRING_3}` | 置換する部分文字列。 |

**一**

```sql
{%= replace("Hello John, here is your monthly newsletter!","John","Mark") %}
```

「Hello マーク」を返します。この場合は、「毎月のニュースレター」が表示されます。

## すべて置換{#replaceAll}

`replaceAll`この関数は、指定されたリテラルの「置換」ストリングを使用して、「ターゲット」に一致するテキストのすべての部分文字列を置き換えるために使用されます。置換は、ストリングの最初から最後まで実行されます。例えば、「aa」を「a」と指定すると、「aa」が「ab」ではなく「ba」に置き換えられます。

**書式**

```sql
{%= replaceAll(string,string,string) %}
```

## 右トリム {#rightTrim}

この関数は、 `rightTrim` ストリングの末尾から空白文字を削除するために使用されます。

**書式**

```sql
{%= rightTrim(string) %}
```

## 分割 {#split}

`split`この関数は、指定された文字を使用してストリングを分割するために使用されます。

**書式**

```sql
{%= split(string,string) %}
```

## 開始点{#startsWith}

この関数を使用して `startsWith` 、ストリングが特定の部分文字列で開始されるかどうかを判断します。

**書式**

```sql
{%= startsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 指定 | つい |
| --------- | ----------- |
| `{STRING_1}` | チェックを実行する文字列。 |
| `{STRING_2}` | 最初のストリング内で検索するストリングです。 |
| `{CASE_SENSITIVE}` | チェックが大文字と小文字を区別するかどうかを指定するオプションのパラメーター。 デフォルトでは、この値は true に設定されています。 |

**一**

次の例では、人物の名前が「Joe」で始まる場合に、大文字と小文字が区別されます。

```sql
{%= startsWith(person.name,"Joe") %}
```

## ストリングを整数に {#string-to-integer}

この関数は、 `string_to_integer` ストリング値を整数値に変換するために使用されます。

**書式**

```sql
{= string_to_integer(string) %}: int
```

## 文字列を数値に {#string-to-number}

この関数は、 `stringToNumber` ストリングを数値に変換するために使用されます。 無効な入力については、出力と同じストリングが返されます。

**書式**

```sql
{%= stringToNumber(string) %}: double
```

## サブストリング {#sub-string}

`Count string`この関数を使用して、開始インデックスと終了インデックスの間にあるストリング式のサブストリングを返します。**書式**

```sql
{= substr(string, integer, integer) %}: string
```

## タイトルの大文字/小文字{#titleCase}

TitleCase **関数は、** ストリングの各単語の最初の文字を大文字にするために使用されます。

**?**

```sql
{%= titleCase(string) %}
```

**一**

この関数は、米国ワシントン在住にいて、この関数がワシントンの番地を返します。

```sql
{%= titleCase(profile.person.location.Street) %}
```

## ブールに {#to-bool}

`toBool`この関数は、引数の値をブール値に変換するために使用されます。型によって異なります。

**書式**

```sql
{= toBool(string) %}: boolean
```

## 日付/時刻 {#to-date-time}

この関数は、 `toDateTime` ストリングを日付に変換するために使用されます。 無効な入力については、紀元日付が出力されます。

**書式**

```sql
{%= toDateTime(string, string) %}: date-time
```

## 日付時刻のみ {#to-date-time-only}

この関数は、 `toDateTimeOnly` 引数の値を日付時刻のみの値に変換するために使用されます。. 無効な入力については、紀元日付が出力されます。

**書式**

```sql
{%= toDateTimeOnly(string) %}: date-time
```

## 裁断{#trim}

Trim **関数は** 、ストリングの先頭と末尾のすべての空白を削除します。

**?**

```sql
{%= trim(string) %}
```

## 大文字{#upper}

**この関数は、** ストリングを大文字に変換します。

**?**

```sql
{%= upperCase(string) %}
```

**一**

この関数は、profile last name を大文字に変換します。

```sql
{%= upperCase(profile.person.name.lastName) %}
```

## url デコード {#url-decode}

この関数は、 `urlDecode` url エンコードされたストリングのデコードに使用されます。

**書式**

```sql
{%= urlDecode(string) %}: string
```

## Url エンコード {#url-encode}

この関数は、 `Count only null` ストリングを url エンコードするために使用されます。

**書式**

```sql
{%= urlEncode(string) %}: string
```

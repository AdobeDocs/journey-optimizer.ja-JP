---
title: 関数ライブラリ
description: 関数ライブラリ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 98%

---

# 文字列関数{#string}

![](../../assets/do-not-localize/badge.png)


TBC CJM文字列関数

## like

`like` 関数は、文字列が指定のパターンと一致するかどうかを判定するために使用されます。

**形式**

```sql
like ({STRING_1},{STRING_2})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列列と照合される式です。式の作成に使用できる特殊文字として、`%` と `_` の 2 つがサポートされています。 <ul><li>`%` は、0 個以上の文字を表すために使用されます。</li><li>`_` は、1 文字を表すために使用されます。</li></ul> |

**例**

次の クエリでは、「es」というパターンを含むすべての市区町村を取得します。

```sql
like (city ,"%es%")
```

## startsWith

`startsWith` 関数は、文字列が指定の部分文字列で始まるかどうかを判定するために使用されます。

**形式**

```sql
startsWith({STRING_1},{STRING_2}, {BOOLEAN})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{BOOLEAN}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の名前が「Joe」で始まるかどうかを判定します。

```sql
startsWith(person.name,"Joe")
```

## doesNotStartWith

`doesNotStartWith` 関数は、文字列が指定の部分文字列で始まらないかどうかを判定するために使用されます。

**形式**

```sql
doesNotStartWith({STRING_1},{STRING_2}, {BOOLEAN})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{BOOLEAN}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の名前が「Joe」で始まらないかどうかを判断します。

```sql
doesNotStartWith(person.name,"Joe")
```

## endsWith

`endsWith` 関数は、文字列が指定の部分文字列で終わるかどうかを判定するために使用されます。

**形式**

```sql
endsWith({STRING_1},{STRING_2}, {BOOLEAN})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{BOOLEAN}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の E メールアドレスが「.com」で終わるかどうかを判定します。

```sql
endsWith(person.emailAddress,".com")
```

## doesNotEndWith

`doesNotEndWith` 関数は、文字列が指定の部分文字列で終わらないかどうかを判定するために使用されます。

**形式**

```sql
doesNotEndWith({STRING_1},{STRING_2}, {BOOLEAN})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{BOOLEAN}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の E メールアドレスが「.com」で終わらないかどうかを判定します。

```sql
doesNotEndWith(person.emailAddress,".com")
```

## contains

`contains` 関数は、文字列が指定の部分文字列を含んでいるかどうかを判定するために使用されます。

**形式**

```sql
contains({STRING_1},{STRING_2}, {BOOLEAN})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{BOOLEAN}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の E メールアドレスが「2010@gm」という文字列を含んでいるかどうかを判定します。

```sql
contains(person.emailAddress,"2010@gm")
```

## doesNotContain

`doesNotContain` 関数は、文字列が指定の部分文字列を含んでいないかどうかを判定するために使用されます。

**形式**

```sql
doesNotContain({STRING_1},{STRING_2}, {BOOLEAN})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{BOOLEAN}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の E メールアドレスが「2010@gm」という文字列を含んでいないかどうかを判定します。

```sql
doesNotContain(person.emailAddress,"2010@gm")
```

## equals

`equals` 関数は、文字列が指定の文字列に等しいかどうかを判定するために使用されます。

**形式**

```sql
equals({STRING_1},{STRING_2})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の名前が「John」かどうかを判定します。

```sql
equals(person.name,"John")
```

## notEqualTo

`notEqualTo` 関数は、文字列が指定の文字列に等しくないかどうかを判定するために使用されます。

**形式**

```sql
notEqualTo({STRING_1},{STRING_2})
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次の クエリでは、大文字と小文字を区別したうえで、人の名前が「John」でないかどうかを判定します。

```sql
notEqualTo(person.name,"John")
```

## matches

`matches` 関数は、文字列が特定の正規表現と一致するかどうかを判定するために使用されます。正規表現でのパターンマッチングについて詳しくは、[こちらのドキュメント](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)を参照してください。

**形式**

```sql
matches({STRING_1},STRING_2})
```

**例**

次の クエリでは、大文字と小文字を区別せずに、人の名前が「John」で始まるかどうかを判定します。

```sql
matches(person.name.,"(?i)^John")
```

## 正規表現グループ

`regexGroup` 関数は、指定された正規表現に基づいて特定の情報を抽出するために使用されます。

**形式**

```sql
regexGroup({STRING},{EXPRESSION})
```

**例**

次の クエリは、E メールアドレスからドメイン名を抽出するために使用します。

```sql
regexGroup(emailAddress,"@(\w+)", 1)
```

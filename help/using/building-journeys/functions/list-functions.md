---
product: journey optimizer
title: リスト関数
description: リスト関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: リスト，関数，式，ジャーニー，配列，コレクション
version: Journey Orchestration
source-git-commit: 0331f8fe2439d41c08ad88a6d0bd95dd150bab90
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 86%

---

# リスト関数 {#list-functions}

リスト関数を使用すると、ジャーニー式内で値のコレクションを操作および操作できます。 これらの機能は、カスタマージャーニーで配列やリストをフィルタリング、並べ替え、変換および分析するために不可欠です。

リスト関数は、次の場合に使用します。

* 条件に基づいてコレクションから特定の項目をフィルタリングして抽出
* リスト要素の昇順または降順での並べ替えと整理
* 重複の削除とリストからの一意の値の取得
* コレクション内に値が存在するかどうかを確認します
* リストから返される項目の数を制限
* リストを様々な形式またはデータタイプに変換する
* リスト間の共通要素の検索などの設定操作の実行

リスト関数は、複雑なデータ構造を操作するための強力なツールを提供し、コレクションの内容に基づく高度なデータ操作と条件付きロジックを可能にします。

## distinct {#distinct}

指定されたリストのユニークな値またはオブジェクトを返します。null エントリは無視されます。

+++構文

`distinct(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターはオプションで、listObject に対してのみ使用できます。パラメーターを指定しないと、すべての属性の値が同じ場合、オブジェクトは重複していると見なされます。パラメーターを指定していて、指定された属性が同じ値を持つ場合、オブジェクトは重複していると見なされます。 |

+++

+++シグネチャと戻り値のタイプ

`distinct(<listInteger>)`

整数のリストを返します。

`distinct(<listDecimal>)`

小数のリストを返します。

`distinct(<listString>)`

文字列のリストを返します。

`distinct(<listDateTimeOnly>)`

タイムゾーンを考慮しない日時のリストを返します。

`distinct(<listDateTime>)`

日時のリストを返します。

`distinct(<listDateOnly>)`

日付のリストを返します。

`distinct(<listBoolean>)`

ブール値のリストを返します。

`distinct(<listDuration>)`

期間のリストを返します。

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

オブジェクトのリストを返します。

+++

+++例

`distinct([10,2,10,null])`

`[10, 2]` を返します。

+++

## distinctWithNull {#distinctWithNull}

指定されたリストのユニークな値またはオブジェクトを返します。リストに null エントリが少なくとも 1 つ含まれる場合、返されるリストに null エントリが含まれます。

+++構文

`distinctWithNull(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly | 処理するリスト。 |

+++

+++シグネチャと戻り値のタイプ

`distinctWithNull(<listInteger>)`

整数のリストを返します。

`distinctWithNull(<listDecimal>)`

小数のリストを返します。

`distinctWithNull(<listString>)`

文字列のリストを返します。

`distinctWithNull(<listDateTimeOnly>)`

タイムゾーンを考慮しない日時のリストを返します。

`distinctWithNull(<listDateTime>)`

日時のリストを返します。

`distinctWithNull(<listDateOnly>)`

日付のリストを返します。

`distinctWithNull(<listBoolean>)`

ブール値のリストを返します。

`distinctWithNull(<listDuration>)`

期間のリストを返します。

+++

+++例

`distinctWithNull([10,2,10,null])`

[10, 2, null] を返します。

+++

**注意：** パラメーター `<listObject>` は、この関数ではサポートされていません。

## filter {#filter}

指定されたキー値の 1 つに一致するキー属性を持つオブジェクトで構成される listObject（オブジェクトリスト）を返します。

+++構文

`filter(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToFilter | listObject（オブジェクトリスト） | フィルタリングの対象となるオブジェクトリスト。 フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | 指定されたリストのオブジェクト内の属性名。フィルタリングのキーとして使用されます |
| keyValueList | リスト | フィルタリングに使用するキー値の配列 |

+++

+++シグネチャと戻り値のタイプ

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

listObject を返します。

+++

+++例

受信イベント「myevent」で渡されるペイロードの例を次に示します。

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

次の式を使用できます。

```json
filter(
 @event{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

「product2」と「product3」を id とする 2 つのオブジェクトから成る listObject を返します。

+++

## getListItem {#getListItem}

指定されたインデックスのリスト項目を返します。

+++構文

`getListItem(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |
| index | 整数 |

+++

+++シグネチャと戻り値のタイプ

`getListItem(<listInteger>,<index>)`

整数を返します。

`getListItem(<listDecimal>,<index>)`

小数を返します。

`getListItem(<listString>,<index>)`

文字列を返します。

`getListItem(<listDateTimeOnly>,<index>)`

タイムゾーンを無視して日時を返します。

`getListItem(<listDateTime>,<index>)`

日時を返します。

`getListItem(<listDateOnly>,<index>)`

日付のリストを返します。

`getListItem(<listBoolean>,<index>)`

ブール値を返します。

`getListItem(<listDuration>,<index>)`

期間を返します。

+++

+++例

`getListItem([10, 2, 3], 1)`

「2」を返します

`getListItem(["A", "B", "C"], 2)`

「C」を返します。

値「20.45.2.3434」を持つイベントフィールド「event.appVersion」の例

`split(@event{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` を返します

`getListItem(split(@event{event.appVersion}, "\\."), 0)`

「20」を返します

+++

## in {#in}

最初の引数値がリストに含まれているかどうかを確認します。確認は、各引数値に対して Equal を使用して実行されます。引数の値が見つかった場合は true を返し、それ以外の場合は false を返します。

`<expression>` のタイプは、リストの項目と一致する必要があります。なお、リストの項目のタイプは互いに一致する必要があります。

+++構文

`in(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| ブール値 | ブール値 |
| Integer | Integer |
| 小数 | 小数 |
| 期間 | 期間 |
| 日時 | 日時 |
| 日時のみ | 日時のみ |
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

+++

+++シグネチャと戻り値のタイプ

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

ブール値を返します。

+++

+++例

`in(4,[4,5,3,4])`

true を返します。

`in(8,[4,5,3,4])`

false を返します。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`

+++

## intersect {#intersect}

2 つの入力リストで共通する値を返します。2 つのリストのいずれかが null の場合、空のリストを返します。

+++構文

`intersect(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト 1 | リスト |
| リスト 2 | リスト |

+++

+++シグネチャと戻り値のタイプ

`intersect(listString,listString)`: listString

`intersect(listDecimal,listDecimal)`: listDecimal

`intersect(listInteger,listInteger)`: listInteger

`intersect(listDateTime,listDateTime)`: listDateTime

`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly

`intersect(listDateOnly,listDateOnly)`: listDateOnly

`intersect(listDuration,listDuration)`: listDuration

`intersect(listBoolean,listBoolean)`: listBoolean

リストを返します。

+++

+++例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

[&quot;sports&quot;, &quot;news&quot;] を返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "documentary"]
)
```

プロファイル属性と指定されたカテゴリリストの間の共通項目を返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @event{myEvent.sport_interests}
)
```

プロファイル属性と指定されたイベントフィールドの間の共通項目を返します。

+++

## limit {#limit}

リストの先頭または末尾の N 個の要素を返します。

+++構文

`limit(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 考慮するリスト。listObject の場合は、フィールド参照にする必要があります。 |
| numberOfItems | 整数 | 指定されたリストから返される項目の数。 |
| firstOrLastItems | ブール値 | このパラメーターはオプションです（デフォルトは true）。true の場合は、先頭の項目を返します。false の場合は、末尾の項目を返します。 |

+++

+++シグネチャと戻り値のタイプ

`limit(<listString>,<integer>)`

`limit(<listString>,<integer>,<boolean>)`

文字列のリストを返します。

`limit(<listInteger>,<integer>)`

`limit(<listInteger>,<integer>,<boolean>)`

整数のリストを返します。

`limit(<listDecimal>,<integer>)`

`limit(<listDecimal>,<integer>,<boolean>)`

小数のリストを返します。

`limit(<listBoolean>,<integer>)`

`limit(<listBoolean>,<integer>,<boolean>)`

ブール値のリストを返します。

`limit(<listDateOnly>,<integer>)`

`limit(<listDateOnly>,<integer>,<boolean>)`

日付のリストを返します。

`limit(<listDateTimeOnly>,<integer>)`

`limit(<listDateTimeOnly>,<integer>,<boolean>)`

タイムゾーンを考慮しない日時のリストを返します。

`limit(<listDateTime>,integer>)`

`limit(<listDateTime>,<integer>,<boolean>)`

日時のリストを返します。

`limit(<listDuration>,<integer>)`

`limit(<listDuration>,<integer>,<boolean>)`

期間のリストを返します。

`limit(<listObject>,<integer>)`

`limit(<listObject>,<integer>,<boolean>)`

オブジェクトのリストを返します。

+++

+++例

`limit(["A", "B", "C", "D", "E"], 3)`

`["A","B","C"]` を返します。

`limit(["A", "B", "C", "D", "E"], 3, false)`

`["C","D","E"]` を返します。

+++

## listSize {#listSize}

リスト内の要素の数をカウントします。

+++構文

`listSize(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合、フィールド参照である必要があります。listObject に null オブジェクトを含めることはできません。 |

+++

+++シグネチャと戻り値のタイプ

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

整数を返します。

`listSize(<listObject>)`

+++

+++例

`listSize([10,2,3])`

3 を返します。

`listSize(@event{my_event.productListItems})`

指定されたオブジェクト配列内のオブジェクト数を返します（listObject 型）。

+++

## serializeList {#serializeList}

指定されたリスト（listObject 以外の任意の型）を文字列に変換します。

+++構文

`serializeList(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | stString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly | 文字列に変換するリスト。 |
| 区切り記号 | 文字列 | 出力文字列内の各リスト要素間の区切り記号。 |
| addQuotes | ブール値 | このパラメーターは、出力文字列の各要素に引用符を含める（true）か、含まない（false）かを示します。 |

+++

+++シグネチャと戻り値のタイプ

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

文字列を返します。

+++

+++例

`serializeList(["Hello","World"], " ", false)`

「Hello World」を返します。

`serializeList(["Hello", "World"], ",", true)`

「&quot;Hello&quot;,&quot;World&quot;」を返します。

+++

## sort {#sort}

値のリストやオブジェクトを自然な順序に並べ替えます。

+++構文

`sort(<parameters>)`

+++

+++パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToSort | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 並べ替えるリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターは listObject に対してのみ使用します。指定されたリストのオブジェクト内の属性名は、並べ替えのキーとして使用されます。 |
| sortingOrder | ブール値 | 昇順（true）または降順（false） |

+++

+++シグネチャと戻り値のタイプ

`sort(<listInteger>,<boolean>)`

整数のリストを返します。

`sort(<listDecimal>,<boolean>)`

小数のリストを返します。

`sort(<listString>,<boolean>)`

文字列のリストを返します。

`sort(<listDateTimeOnly>,<boolean>)`

タイムゾーンを考慮しない日時のリストを返します。

`sort(<listDateTime>,<boolean>)`

日時のリストを返します。

`sort(<listDateOnly>,<boolean>)`

日付のリストを返します。

`sort(<listBoolean>,<boolean>)`

ブール値のリストを返します。

`sort(<listObject>,<string>,<boolean>)`

オブジェクトのリストを返します。

+++

+++例

`sort(["A", "C", "B"], true)`

`["A","B","C"]` を返します。

`sort([1, 3, 2], false)`

`[3, 2, 1]` を返します。

`sort(@event{my_event.productListItems}, "SKU", true)`

SKU 属性で並べ替えられた listObject を返します（昇順）

+++


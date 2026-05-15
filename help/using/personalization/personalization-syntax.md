---
solution: Journey Optimizer
product: journey optimizer
title: Personalizationの構文
description: パーソナライゼーション構文の使用方法を説明します。
feature: Personalization
topic: Personalization
role: Developer
level: Intermediate
keywords: 式，エディター，構文，パーソナライゼーション
exl-id: 5a562066-ece0-4a78-92a7-52bf3c3b2eea
TQID: https://experienceleague.adobe.com/kZEw2lITdt8SMWMe-UT2vPzdoiAjB2vbItmK9zt-WJo
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: fe338112-e2ce-4876-8989-fc4d497613f1
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: c5ecc28ec44a9c608f4fe5011e061cad62d92e2b
workflow-type: tm+mt
source-wordcount: 1299
ht-degree: 0%

---

# Personalizationの構文 {#personalization-syntax}

[!DNL Journey Optimizer]のPersonalizationは、同じ式で一緒に動作する2つの補完的な構文を使用します。

* **Handlebars** （`{{...}}`） – プロファイル属性のレンダリング、配列のループ、および呼び出しブロックヘルパーに使用されます。 詳しくは、[HandlebarsJS ドキュメント ](https://handlebarsjs.com/)を参照してください。
* **Profile Query Language （PQL）** （`{%= ... %}`） – 組み込み関数の呼び出し（例：`upperCase()`、`formatDate()`、`dateDiff()`）および条件式の評価に使用されます。

どのコンテキストにいるのかを理解することは、ランタイムエラーを回避するための鍵となります。 例えば、`{{...}}`内に配置されたPQL関数呼び出しは、HandlebarsがPQL式として評価するのではなくヘルパーとして解決しようとするため、失敗します。

**例：**

| ユースケース | 構文 |
|----------|--------|
| プロファイル属性のレンダリング | `{{profile.person.name.firstName}}` |
| PQL関数の呼び出し | `{%= upperCase(profile.person.name.firstName) %}` |
| 条件付きブロック | `{%#if profile.loyalty.tier = "gold"%}...{%/if%}` |
| 配列のループ | `{{#each profile.orders}}...{{/each}}` |

属性構造は、Adobe Experience Platform XDM スキーマで定義されます。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html){target="_blank"}。

>[!TIP]
>
>これらの構文を実際のシナリオ（日付の書式設定、カウントダウン、条件付きフォールバックなど）に適用する、すぐに使用できる式については、**[Personalization レシピ](personalization-recipes.md)** ページを参照してください。

## 構文の一般ルール {#general-rules}

* 識別子は、Handlebars構文に予約されている次の特殊文字を除いて、任意のUnicode文字にすることができます。

  ```
  Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
  ```

* 構文では大文字と小文字が区別されます。

* 単語&#x200B;**true**、**false**、**null**、**undefined**&#x200B;は、パス式の最初の部分でのみ使用できます。

* Handlebarsでは、{{expression}}によって返される値は&#x200B;**HTML-escaped**&#x200B;です。 式に`&`が含まれている場合、返されたHTML エスケープ出力は`&amp;`として生成されます。 Handlebarsに値をエスケープさせたくない場合は、「トリプルスタッシュ」を使用します。

  フィールド `profile.person.name`の値が「Mark &amp; Mary」であるとします。 構文`{{profile.person.name}}`には`Mark &amp; Mary`が表示され、`{{{profile.person.name}}}`には`Mark & Mary`が表示されます。

* リテラル関数の引数に関して、テンプレート言語パーサーは、単一のエスケープされていないバックスラッシュ （`\`）記号をサポートしていません。 この文字は、追加のバックスラッシュ （`\`）記号でエスケープする必要があります。 例：

  `{%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}`

* 文字列値の中に&#x200B;**リテラルの二重引用符**&#x200B;を含めるには（例：JSON出力を生成する場合）、バックスラッシュ（`\"`）でエスケープします。

  ```handlebars
  { "message": "Hello \"{{profile.person.name.firstName}}\"" }
  ```

  出力：`{ "message": "Hello \"John\"" }`

  または、HTMLでエンコードしない特殊文字が値に含まれている場合は、トリプルスタッシュ `{{{ }}}`を使用してエスケープされていないHTMLを出力します。

## 予約済みキーワード {#reserved-keywords}

特定のキーワードはProfile Query Language（PQL）で予約されており、パーソナライゼーション式でフィールド名や変数名として直接使用することはできません。 XDM スキーマに、予約されたキーワードに一致する名前を持つフィールドが含まれている場合は、エクスプレッションでそれらを参照するためにバックティック （`` ` ``）を使用してエスケープする必要があります。

**予約済みキーワード：**

* `next`
* `last`
* `this`

**例：**

プロファイルスキーマに`next`という名前のフィールドがある場合は、それをバックティックでラップする必要があります。

```
{{profile.person.`next`.name}}
```

バックティックがないと、パーソナライゼーションエディターは検証に失敗し、エラーが発生します。

>[!NOTE]
>
>予約済みキーワードのバックティック エスケープは、`{{...}}`個のHandlebars パスと`{%= ... %}`個のPQL エクスプレッションの両方に適用されます。これは、これらのキーワードがパス解決レベルで予約されているためです。 これは、バックティックエスケープがPQL式の内部でのみサポートされるハイフネーション付きフィールド名とは異なります。 [ ハイフネーションされた属性キー](#hyphenated-keys)を参照してください。

## 特殊属性キーのPQL構文ルール {#pql-special-keys}

予約済みキーワード以外にも、2つのケースでPQL エクスプレッションでバックティック エスケープが必要になります。

### ハイフネーションされた属性キー {#hyphenated-keys}

XDM スキーマにハイフン付きのフィールド名（例：`my-field`、`event-type`）または数字で始まるまたは含まれる名前が含まれている場合は、キーをPQL エクスプレッション内のバックティックにラップします。

```sql
{%= profile.events.`order-total` > 100 %}
```

>[!NOTE]
>
>バックティック エスケープは、PQL エクスプレッション （`{%= ... %}`）内でのみサポートされています。 Handlebars補間（`{{...}}`）ではサポートされていません。 ただし、ハイフネーションされたフィールド名は`{{...}}` ブロック （例：`{{profile.my-custom-field}}`）で直接参照できます。バックティック構文のみが失敗します。

PQL式でバックティックを使用しない場合、ハイフンは減算演算子として解釈され、PQL構文エラーが発生します。

### コンテキスト属性の数値イベント ID {#numeric-event-ids}

イベント IDが数値（例：`1697323153`）であるコンテキストイベント属性を参照する場合は、バックティックにラップします。 これは`formatDate()`のような関数の内部でも適用されます。

```handlebars
{% let ts = formatDate(toDateTime(context.journey.events.`1697323153`.timestamp), "dd/MM/yyyy") %}
{{ts}}
```

## 型強制 {#type-coercion}

PQLは強く型付けされています。 値を比較または渡す場合、両側は同じタイプである必要があります。 一般的なケース：

| シナリオ | Solution |
|----------|----------|
| 文字列として格納された数値 | 算術または比較の前に`stringToNumber()`を使用：`{%= stringToNumber(profile.loyalty.pointsBalance) > 500 %}` |
| 文字列として格納された整数 | 算術の前に`string_to_integer()`または`stringToNumber()`を使用 |
| 文字列として格納されたブール値 | `toBool()`を使用して変換：`{%= toBool(profile.consents.email.val) = true %}` |

## 使用可能な名前空間 {#namespaces}

* **プロファイル**

  この名前空間を使用すると、[Adobe Experience Platform Data Model （XDM） ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html){target="_blank"}で説明されているプロファイルスキーマで定義されているすべての属性を参照できます。

  属性は、[!DNL Journey Optimizer] パーソナライゼーションブロックで参照する前に、スキーマで定義する必要があります。

  条件でプロファイル属性を活用する方法について詳しくは、[この節](functions/helpers.md#if-function)を参照してください。

  +++参照サンプル

   * `{{profile.person.name.fullName}}`
   * `{{profile.person.name.firstName}}`
   * `{{profile.person.gender}}`
   * `{{profile.personalEmail.address}}`
   * `{{profile.mobilePhone.number}}`
   * `{{profile.homeAddress.city}}`
   * `{{profile.faxPhone.number}}`

  +++

* **オーディエンス**

  セグメント化サービスについて詳しくは、[このドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target="_blank"}を参照してください。

* **オファー**

  この名前空間を使用すると、既存のオファー決定を参照できます。

  オファーを参照するには、オファーを定義する様々な情報を含むパスを宣言する必要があります。 このパスの構造は次のとおりです。

  `offers.Type.[Placement Id].[Activity Id].Attribute`

  どこで：

   * `offers`は、オファー名前空間に属するパス式を識別します
   * `Type`は、オファー表示域の種類を決定します。 使用可能な値は`image`、`html`、`text`です
   * `Placement Id`と`Activity Id`はプレースメントとアクティビティの識別子です
   * `Attributes`は、オファータイプに依存するオファー固有の属性です。 例：画像の`deliveryUrl`

  決定APIとオファー表示域について詳しくは、[このページ ](../offers/api-reference/offer-delivery-api/decisioning-api.md)を参照してください

  すべての参照は、[このページ ](../personalization/personalization-build-expressions.md)で説明されている検証メカニズムを使用して、オファースキーマに対して検証されます

  +++参照サンプル

   * 画像がホストされている場所：

     `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl`

   * 画像をクリックした場合のターゲット URL:

     `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl`

   * 決定エンジンからのオファーのテキストコンテンツ：

     `offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

   * 決定エンジンからのオファーのHTML コンテンツ：

     `offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

  +++

## ヘルパー {#helpers-all}

Handlebars ヘルパーは、パラメーターが後に続く可能性がある簡単な識別子です。 各パラメーターはHandlebars式です。 これらのヘルパーには、テンプレート内の任意のコンテキストからアクセスできます。

これらのブロックヘルパーは、ヘルパー名の前の`#`によって識別され、同じ名前の一致するクロージング `/`が必要です。

ブロックは、ブロックの開口部（`{{# }}`）と閉じ（`{{/}}`）を持つ式です。

ヘルパー関数について詳しくは、[この節](functions/helpers.md)を参照してください。

## リテラルタイプ {#literal-types}

[!DNL Adobe Journey Optimizer]は次のリテラル型をサポートしています：

| リテラル | 定義 |
| ------- | ---------- |
| 文字列 | 二重引用符で囲まれた文字で構成されるデータタイプ。 <br>例：`"prospect"`、`"jobs"`、`"articles"` |
| ブーリアン | trueまたはfalseのデータタイプ。 |
| 整数 | 整数を表すデータタイプ。 正、負、またはゼロにすることができます。 <br>例：`-201`、`0`、`412` |
| 配列 | 他のリテラル値のグループとして構成されるデータタイプ。 角括弧を使用してグループ化し、カンマを使用して異なる値を区切ります。<br> **メモ：**&#x200B;配列内の項目のプロパティに直接アクセスすることはできません。<br> 例：`[1, 4, 7]`、`["US", "FR"]` |

>[!CAUTION]
>
>**xEvent**&#x200B;変数は、パーソナライゼーション式では使用できません。 xEventを参照すると、検証エラーが発生します。

## ベストプラクティス {#best-practices}

パーソナライゼーション式を作成する前に、これらの構文ルールを確認します。 ほとんどのランタイムエラーは、HandlebarsとPQLのコンテキストを混在させることから発生します。

**正しい条件付きブロック構文を使用**

常に`{%#if%}` / `{%else if%}` / `{%else%}` / `{%/if%}`を使用してください。 `{% if %}` / `{% elseif %}` / `{% endif %}`構文はサポートされていません。

```handlebars
{%#if profile.loyalty.tier = "gold"%}
Gold member content
{%else if profile.loyalty.tier = "silver"%}
Silver member content
{%else%}
Default content
{%/if%}
```

**Handlebars ブロック**&#x200B;内のPQL関数を呼び出さない`{{...}}`

`{{...}}`はHandlebars変数とヘルパーのみを解決します。PQLは評価されません。 `{{...}}`内の`upperCase()`のようなPQL関数をラップすると、「ヘルパーが見つかりませんでした」エラーが発生します。 代わりに`{%= ... %}`を使用してください：

| 不正確 | 正解 |
|-----------|---------|
| `{{upperCase(cleanName)}}` | `{%= upperCase(cleanName) %}` |

**`{{#each}}`と`{%#if%}`**&#x200B;を組み合わせる場合は、名前付きループ エイリアスを使用します

`this.field`はHandlebars レンダラーによって解決されますが、`{%#if%}`条件内のPQL エバリュエーターによって解決されません。 両方のコンテキストがフィールドを解決できるように、`as |item|`を使用して名前付きエイリアスを定義します。

```handlebars
{{#each profile.orders as |order|}}
  {%#if order.status = "pending"%}
  Order {{order.id}} is pending.
  {%/if%}
{{/each}}
```

**ループする前にPQL関数の結果を変数に割り当てます**

`topN`などのPQL UDFは、`{{#each}}`内で直接呼び出すことはできません。 最初に`{% let %}`で評価し、次に結果を繰り返します。

```handlebars
{% let topOrders = topN(profile.orders, price, 3) %}
{{#each topOrders}}
  {{this.name}} — {{this.price}}&euro;
{{/each}}
```

**関数呼び出しの繰り返しを避けるために`{% let %}`を使用する**

計算された値が複数回必要な場合は、変数に格納します。 これにより、読みやすさが向上し、冗長な評価を防ぐことができます。

```handlebars
{% let cleanName = replaceAll(profile.person.name.firstName, "[^a-zA-Z]", "") %}
Hi {{cleanName}}, your code is: WELCOME-{%= upperCase(cleanName) %}
```

**`dateDiff`**&#x200B;の正しい引数順序を使用する

`dateDiff(start, end)`は前の日付を最初に使用します。 将来の日付までの残り日数を計算するには、現在の日付を最初の引数として渡します。

```handlebars
{% let daysLeft = dateDiff(getCurrentZonedDateTime(), stringToDate(profile.loyalty.expiryDate)) %}
```

**`==`**&#x200B;ではなく、`=`を使用してPQLで等価比較を行います

PQLは、等号に1つの`=`演算子を使用します。 `==`を使用すると、構文エラーが発生します。

**ハイフネーションされたフィールド名にバックティックを使用する – PQL式のみ**

XDM スキーマフィールド名にハイフン （例：`order-total`）が含まれる場合は、ハイフンが減算演算子として解析されないように、ハイフンをバックティックで折り返します。 これは、`{{...}}`個のHandlebars ブロックではなく、`{%= ... %}`個のPQL式でのみサポートされています。

```sql
{%= profile.events.`order-total` > 100 %}
```

すぐに使用できるエクスプレッションについては、[Personalization レシピ ](personalization-recipes.md)を参照してください。

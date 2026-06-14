---
solution: Journey Optimizer
product: journey optimizer
title: パーソナライゼーション構文
description: パーソナライゼーション構文の使用方法を説明します。
feature: Personalization
topic: Personalization
role: Developer
level: Intermediate
keywords: 式, エディター, 構文, パーソナライゼーション
exl-id: 5a562066-ece0-4a78-92a7-52bf3c3b2eea
TQID: https://experienceleague.adobe.com/kZEw2lITdt8SMWMe-UT2vPzdoiAjB2vbItmK9zt-WJo
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: fda7be7c-b81e-42c0-95a9-616e5b893c03
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
subfeature_v2:
  - id: ac5d9310-7772-40fb-9d78-864562e1bfd6
  - id: e51e8901-97d9-4f7d-a835-503025a90e32
source-git-commit: 378c98d4dc9552de3eed68eda59d9917c2b56347
workflow-type: tm+mt
source-wordcount: 1325
ht-degree: 47%

---

# パーソナライゼーション構文 {#personalization-syntax}

>[!BEGINSHADEBOX]

**このページでは、**&#x200B;一般的なルール、予約キーワード、型強制、使用可能な名前空間、ベストプラクティスなど、Adobe Journey OptimizerのHandlebarsとPQL パーソナライゼーション構文について説明します。

>[!ENDSHADEBOX]

[!DNL Journey Optimizer]のPersonalizationは、同じ式で一緒に動作する2つの補完的な構文を使用します。

* **Handlebars** （`{{...}}`） – プロファイル属性のレンダリング、配列のループ、および呼び出しブロックヘルパーに使用されます。 詳しくは、[HandlebarsJS ドキュメント &#x200B;](https://handlebarsjs.com/)を参照してください。
* **Profile Query Language （PQL）** （`{%= ... %}`） – 組み込み関数の呼び出し（例：`upperCase()`、`formatDate()`、`dateDiff()`）および条件式の評価に使用されます。

どのコンテキストにいるのかを理解することは、ランタイムエラーを回避するための鍵となります。 例えば、`{{...}}`内に配置されたPQL関数呼び出しは、HandlebarsがPQL式として評価するのではなくヘルパーとして解決しようとするため、失敗します。

**例：**

| ユースケース | 構文 |
|----------|--------|
| プロファイル属性のレンダリング | `{{profile.person.name.firstName}}` |
| PQL関数の呼び出し | `{%= upperCase(profile.person.name.firstName) %}` |
| 条件付きブロック | `{%#if profile.loyalty.tier = "gold"%}...{%/if%}` |
| 配列のループ | `{{#each profile.orders}}...{{/each}}` |

属性の構造は、Adobe Experience Platform XDM スキーマで定義されます。 [学習を増やす](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}。

>[!TIP]
>
>これらの構文を実際のシナリオ（日付の書式設定、カウントダウン、条件付きフォールバックなど）に適用する、すぐに使用できる式については、**[Personalization レシピ](personalization-recipes.md)** ページを参照してください。

## 構文の一般的なルール {#general-rules}

* 識別子には、Handlebars 構文用に予約されている次の特殊文字を除く任意の Unicode 文字を使用できます。

  ```
  Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
  ```

* 構文では大文字と小文字が区別されます。

* **true**、**false**、**null** および **undefined**&#x200B;という語は、パス式の最初の部分でのみ使用できます。

* Handlebars では、{{expression}} から返される値は **HTML エスケープ**&#x200B;されています。 式に「`&`」が含まれている場合、返される HTML エスケープ出力は「`&amp;`」として生成されます。 Handlebars の値をエスケープしない場合は、「トリプルスタッシュ」を使用します。

  フィールド `profile.person.name` の値が「Mark &amp; Mary」であるとします。 構文 `{{profile.person.name}}` には `Mark &amp; Mary` が表示され、`{{{profile.person.name}}}` には `Mark & Mary` が表示されます。

* リテラル関数の引数に関して、テンプレート言語パーサーはエスケープされない単一のバックスラッシュ（`\`）記号をサポートしていません。 この文字は、バックスラッシュ（`\`）記号を追加してエスケープする必要があります。 例：

  `{%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}`

* 文字列値の中に&#x200B;**リテラルの二重引用符**&#x200B;を含めるには（例：JSON出力を生成する場合）、バックスラッシュ（`\"`）でエスケープします。

  ```handlebars
  { "message": "Hello \"{{profile.person.name.firstName}}\"" }
  ```

  出力：`{ "message": "Hello \"John\"" }`

  または、HTMLでエンコードしない特殊文字が値に含まれている場合は、トリプルスタッシュ `{{{ }}}`を使用してエスケープされていないHTMLを出力します。

## 予約済みのキーワード {#reserved-keywords}

特定のキーワードは、Profile Query Language（PQL）で予約され、パーソナライゼーション式のフィールド名または変数名として直接使用できません。 XDM スキーマに予約済みのキーワードと一致する名前のフィールドが含まれている場合、式で参照するには、バックティック（`` ` ``）を使用してエスケープする必要があります。

**予約済みのキーワードは次のとおりです。**

* `next`
* `last`
* `this`

**例：**

プロファイルスキーマに `next` という名前のフィールドがある場合は、バックティックで囲む必要があります。

```
{{profile.person.`next`.name}}
```

バックティックがないと、パーソナライゼーションエディターは検証に失敗し、エラーが発生します。

>[!NOTE]
>
>予約済みキーワードのバックティック エスケープは、`{{...}}`個のHandlebars パスと`{%= ... %}`個のPQL エクスプレッションの両方に適用されます。これは、これらのキーワードがパス解決レベルで予約されているためです。 これは、バックティックエスケープがPQL式の内部でのみサポートされるハイフネーション付きフィールド名とは異なります。 [&#x200B; ハイフネーションされた属性キー](#hyphenated-keys)を参照してください。

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

| シナリオ | ソリューション |
|----------|----------|
| 文字列として格納された数値 | 算術または比較の前に`stringToNumber()`を使用：`{%= stringToNumber(profile.loyalty.pointsBalance) > 500 %}` |
| 文字列として格納された整数 | 算術の前に`string_to_integer()`または`stringToNumber()`を使用 |
| 文字列として格納されたブール値 | `toBool()`を使用して変換：`{%= toBool(profile.consents.email.val) = true %}` |

## 使用可能な名前空間 {#namespaces}

* **プロファイル**

  この名前空間を使用すると、プロファイルスキーマで定義されているすべての属性を参照できます。このスキーマについて詳しくは、[Adobe Experience Platform データモデル（XDM）のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}を参照してください。

  属性は、[!DNL Journey Optimizer] のパーソナライゼーションブロックで参照する前に、スキーマで定義しておく必要があります。

  条件でプロファイル属性を活用する方法について詳しくは、[この節](functions/helpers.md#if-function)を参照してください。

  +++サンプルリファレンス

   * `{{profile.person.name.fullName}}`
   * `{{profile.person.name.firstName}}`
   * `{{profile.person.gender}}`
   * `{{profile.personalEmail.address}}`
   * `{{profile.mobilePhone.number}}`
   * `{{profile.homeAddress.city}}`
   * `{{profile.faxPhone.number}}`

  +++

* **オーディエンス**

  セグメント化サービスについて詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja){target="_blank"}を参照してください。

* **オファー**

  この名前空間では、既存のオファー決定を参照できます。

  オファーを参照するには、オファーを定義する様々な情報を使用してパスを宣言する必要があります。 このパスの構造は次のようになります。

  `offers.Type.[Placement Id].[Activity Id].Attribute`

  ここで：

   * `offers` はオファー名前空間に属するパス式を識別します。
   * `Type` はオファー表示域のタイプを決定します。 `image`、`html` および `text` などの値が使用されます。
   * `Placement Id` と `Activity Id` は配置とアクティビティの識別子です。
   * `Attributes` は、オファータイプに依存するオファー固有の属性です。 例：`deliveryUrl`（画像の場合）

  決定 API とオファー表示域について詳しくは、[このページ](../offers/api-reference/offer-delivery-api/decisioning-api.md)を参照してください。

  すべての参照は、[このページ](../personalization/personalization-build-expressions.md)で説明されている検証メカニズムを使用して、オファースキーマに対して検証されます

  +++サンプルリファレンス

   * 画像がホストされる場所：

     `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl`

   * 画像をクリックしたときのターゲット URL：

     `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl`

   * 決定エンジンから得られるオファーのテキストコンテンツ：

     `offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

   * 決定エンジンから得られるオファーの HTML コンテンツ：

     `offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

  +++

## ヘルパー {#helpers-all}

Handlebars ヘルパーは、パラメーターの後に付けられる単純な識別子です。 各パラメーターは、Handlebars 式です。 これらのヘルパーは、テンプレート内の任意のコンテキストからアクセスできます。

これらのブロックヘルパーは、ヘルパー名の先頭にある `#` で識別され、対となる同じ名前の `/` タグで閉じる必要があります。

ブロックは、ブロック開始タグ（`{{# }}`）と終了タグ（`{{/}}`）を持つ式です。

ヘルパー関数について詳しくは、[この節](functions/helpers.md)を参照してください。

## リテラル型 {#literal-types}

[!DNL Adobe Journey Optimizer] では、次のリテラル型をサポートしています。

| リテラル | 定義 |
| ------- | ---------- |
| 文字列 | 1 つ以上の文字で構成され、二重引用符で囲まれたデータタイプです。 <br>例：`"prospect"`、`"jobs"`、`"articles"` |
| ブール | true か false のいずれかであるデータタイプです。 |
| 整数 | 整数を表すデータタイプです。 正、負、ゼロのいずれかです。 <br>例：`-201`、`0`、`412` |
| 配列 | 他のリテラル値のグループとして構成されるデータ型です。 複数の値を区切る場合は、角括弧で囲んでグループ化し、カンマで区切ります。<br> **メモ：**&#x200B;配列内の項目のプロパティに直接アクセスすることはできません。<br> 例：`[1, 4, 7]`、`["US", "FR"]` |

>[!CAUTION]
>
>**xEvent** 変数は、パーソナライズ式では使用できません。 xEvent を参照すると、検証エラーが発生します。

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

| 不正確 | 正確 |
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

すぐに使用できるエクスプレッションについては、[Personalization レシピ &#x200B;](personalization-recipes.md)を参照してください。

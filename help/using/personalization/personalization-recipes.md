---
title: パーソナライゼーションのレシピ
description: Adobe Journey Optimizerの一般的なパーソナライゼーションパターンと実例
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
feature_v2: id: fda7be7c-b81e-42c0-95a9-616e5b893c03
subfeature_v2: id: cb09dcb7-3367-4b63-b02c-8a1356eb876eid: ac5d9310-7772-40fb-9d78-864562e1bfd6
source-git-commit: f552e98f370f96e9a99d2f1d604f840ac6069d65
workflow-type: tm+mt
source-wordcount: 1524
ht-degree: 0%

---

# パーソナライゼーションのレシピ {#personalization-recipes}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、Adobe Journey Optimizer コンテンツに直接コピーできる日付、配列、文字列、条件付きロジック、およびPQL エッジ ケースの、すぐに使用できるパーソナライズのレシピを見つけることができます。

>[!ENDSHADEBOX]

このページでは、Adobe Journey Optimizerの最も一般的なユースケース向けに、すぐに使用できるパーソナライゼーションパターンを提供します。 あらゆる例でパーソナライゼーションエディターの構文を使用しており、電子メール、SMS、プッシュコンテンツに直接コピーできます。

使用可能な関数の完全な参照については、[ ヘルパー関数](functions/helpers.md)、[日付/時刻関数](functions/dates.md)、[文字列関数](functions/string.md)、および[配列関数](functions/arrays-list.md)を参照してください。

>[!TIP]
>
>例をコピーする前に、[Personalizationのベストプラクティス ](personalization-syntax.md#best-practices)を確認して、最も一般的な構文エラーを回避します。

## 日付と時刻のレシピ {#date-time-recipes}

### レシピ 1 – 現在の日付を読みやすい形式で表示する {#recipe-current-date}

`formatDate`と`getCurrentZonedDateTime()`を使用して、任意の形式で今日の日付をレンダリングします。

```sql
{%= formatDate(getCurrentZonedDateTime(), "MMMM dd, yyyy") %}
```

出力（例）: `April 11, 2026`

**一般的な形式パターン：**

| パターン | 出力例 |
|---------|---------------|
| `"dd/MM/yyyy"` | `11/04/2026` |
| `"MM/dd/yyyy"` | `04/11/2026` |
| `"EEEE, MMMM dd"` | `Saturday, April 11` |
| `"yyyy-MM-dd"` | `2026-04-11` |

>[!NOTE]
>
>年の境界で予期しない結果を避けるには、`Y` （週ベースの年）ではなく小文字の`y` （暦年）を使用します。 完全な参照については、[ パターン文字](functions/dates.md#pattern-characters)を参照してください。

### レシピ 2 – 有効期限またはイベント日までのカウントダウン {#recipe-countdown}

`dateDiff`を使用して、プロファイル日付属性までの残り日数を計算し、動的にレンダリングします。

```handlebars
{% let daysLeft = dateDiff(getCurrentZonedDateTime(), stringToDate(profile.loyalty.expiryDate)) %}
{%#if daysLeft > 0%}
Your reward points expire in {{daysLeft}} day{%#if daysLeft > 1%}s{%/if%}. Use them before they're gone!
{%else%}
Your reward points have expired.
{%/if%}
```

出力（例）: `Your reward points expire in 7 days. Use them before they're gone!`

### レシピ 3 – 動的な終了日のX日前 {#recipe-days-before}

プロファイル属性のX日前の日付を計算するには（例：コンテンツや件名で参照）、負のオフセットで`addDays`を使用します。

```sql
{%= formatDate(addDays(stringToDate(profile.subscription.endDate), -7), "MMMM dd, yyyy") %}
```

出力（例）: `April 04, 2026` *（4月11日の7日前）*

特定の時刻（例：午前9時）も設定するには、`setHours`と組み合わせます。

```sql
{%= formatDate(setHours(addDays(stringToDate(profile.subscription.endDate), -7), 9), "dd/MM/yyyy HH:mm") %}
```

### レシピ 4 – 現在の時間をHH:MMとしてのみ表示 {#recipe-time-only}

`extractHours`と`extractMinutes`を使用して、時間の部分のみを表示し、先頭にゼロのガードを数分だけ表示します。

```handlebars
{% let h = extractHours(getCurrentZonedDateTime()) %}
{% let m = extractMinutes(getCurrentZonedDateTime()) %}
Your appointment is at {{h}}:{%#if m < 10%}0{%/if%}{{m}}.
```

出力（例）: `Your appointment is at 14:05.`

### レシピ 5 – 週末と平日の区別 {#recipe-weekend}

`dayOfWeek`を使用して、日に基づいてコンテンツを適応させます。 関数は、1 （月曜日）から7 （日曜日）を返します。 1つの`=`演算子を使用します（`==`ではなくPQL構文）。

```handlebars
{%#if dayOfWeek(getCurrentZonedDateTime()) = 6 or dayOfWeek(getCurrentZonedDateTime()) = 7%}
We're closed on weekends — our team will follow up on the next business day.
{%else%}
Our team will get back to you within 24 hours.
{%/if%}
```

>[!NOTE]
>
>`dayOfWeek()`は、日に基づいて&#x200B;**コンテンツ**&#x200B;を適応させます。 曜日に基づいてジャーニー内でプロファイルを異なる方法でルーティングする場合は、ジャーニーの条件アクティビティで組み込みの&#x200B;**時間条件→曜日** オプションを使用します。 [詳細情報](../building-journeys/condition-activity.md#date_condition)

## 配列とループのレシピ {#array-recipes}

### レシピ 6 — プロファイル配列からのすべての項目をリストする {#recipe-list-items}

`{{#each}}`を使用してプロファイル配列を繰り返し処理し、各項目をレンダリングします。 これは、パーソナライゼーションエディター（電子メール、SMS、プッシュ通知）でのみ使用できます。

```handlebars
{{#each profile.purchases.recentItems}}
  - {{this.name}}: {{this.price}}&euro;
{{/each}}
```

出力（例）:

```
- Running shoes: 89&euro;
- Water bottle: 15&euro;
- Gym bag: 45&euro;
```

>[!NOTE]
>
>ジャーニー条件アクティビティでは`{{#each}}`はサポートされていません。 条件の配列フィルタリングには、[ コレクション管理関数](../building-journeys/expression/collection-management-functions.md)を使用します。

### レシピ 7 – 価格で配列から上位N個の項目を表示します {#recipe-first-n}

`topN`を使用して、上位N個の項目を数値フィールドで並べ替えて取得します。 `topN`はPQL関数であるため、最初に`{% let %}`を使用して変数に割り当て、次に`{{#each}}`を使用してループします。

```handlebars
{% let topOrders = topN(profile.orders, price, 3) %}
{{#each topOrders}}
  {{this.name}} — {{this.price}}&euro;
{{/each}}
```

>[!NOTE]
>
>`topN(profile.orders, price, 3)`は順序を`price`で降順に並べ替え、上位3つを返します。元の配列順序の最初の3つの項目を単に返すわけではありません。

または、`head`を使用して、1つの最上位アイテムのみを取得します。

```sql
{%= head(profile.purchases.recentItems).name %}
```

### レシピ 8 – 配列項目ごとにコンテンツを条件付きでレンダリングする {#recipe-conditional-loop}

`{{#each}}`内の`{%#if%}`を使用して、一致する項目に対してのみ出力をレンダリングします。 PQL エバリュエーターが条件で属性参照を解決できるように、`as |order|`を使用してループエイリアスを定義します。

```handlebars
{{#each profile.orders as |order|}}
  {%#if order.status = "pending"%}
  Order {{order.id}} is pending — we'll notify you when it ships.
  {%/if%}
{{/each}}
```

>[!NOTE]
>
>`this.status`はHandlebars エクスプレッションで機能しますが、`{%#if%}`内のPQL エバリュエーターによって解決されません。 名前付きループエイリアス（例：`order`）を使用すると、ハンドルバーとPQLの両方のコンテキストで属性を使用できるようになります。

## 文字列と書式設定のレシピ {#string-recipes}

### レシピ 9 - replaceAllを使用して文字列をクリーニングし、再利用する {#recipe-replaceall-reuse}

`replaceAll`は新しい値を返します。元の値は変更されません。 `{% let %}`を使用して結果を保存し、関数呼び出しを繰り返さずに複数回参照します。

```handlebars
{% let cleanName = replaceAll(profile.person.name.firstName, "[^a-zA-Z]", "") %}
Hi {{cleanName}},
Your exclusive code is: WELCOME-{%= upperCase(cleanName) %}
```

出力（例）:

```
Hi John,
Your exclusive code is: WELCOME-JOHN
```

### レシピ 10 — JSON出力で値を二重引用符で囲む {#recipe-json-quotes}

文字列内にリテラル二重引用符を含めるには（例：カスタムペイロード用のJSONの生成）、バックスラッシュ（`\"`）でエスケープします。

```handlebars
{ "greeting": "Hello \"{{profile.person.name.firstName}}\"" }
```

出力：`{ "greeting": "Hello \"John\"" }`

### レシピ 11 – 日付コンポーネントを大文字で書式設定する {#recipe-uppercase-date}

`formatDate`を`upperCase`と組み合わせて、月または日の名前を大文字でレンダリングします。

```sql
{%= upperCase(formatDate(getCurrentZonedDateTime(), "MMMM")) %}
```

出力（例）: `APRIL`

大文字の日付文字列の場合：

```sql
{%= upperCase(formatDate(profile.person.birthDateTime, "EEEE MMMM dd yyyy")) %}
```

出力（例）: `WEDNESDAY JANUARY 01 2020`

## 条件付きロジックのレシピ {#conditional-recipes}

### レシピ 12 — パーソナライズされたコンテンツのIF/ELSEIF/ELSE {#recipe-if-elseif}

マルチブランチの条件付きロジックには、`{%#if%}`、`{%else if%}`および`{%else%}`を使用します。 このパターンは、メールコンテンツとフラグメントで機能します。

```handlebars
{%#if profile.loyalty.tier = "gold"%}
As a Gold member, enjoy free shipping on all orders.
{%else if profile.loyalty.tier = "silver"%}
As a Silver member, enjoy free shipping on orders over &euro;50.
{%else%}
Join our loyalty program to unlock exclusive benefits.
{%/if%}
```

### レシピ 13 — ヌルセーフ属性表示 {#recipe-null-safe}

プロファイル属性がnullまたは欠落している可能性がある場合に、空の値のレンダリングを避けるために、条件付きフォールバックを使用します。

```handlebars
{%#if profile.person.name.firstName%}
Hi {{profile.person.name.firstName}},
{%else%}
Hi there,
{%/if%}
```

または、`isEmpty`を使用して三項スタイルのパターンを持つインライン：

```handlebars
Hi {%#if isEmpty(profile.person.name.firstName)%}valued customer{%else%}{{profile.person.name.firstName}}{%/if%},
```

## PQL edgeのケースレシピ {#pql-edge-cases}

### レシピ 14 — ハイフン付きの属性キーを参照する {#recipe-hyphenated-key}

XDM スキーマフィールド名にハイフン（`order-total`、`event-type`など）が含まれる場合は、PQL式の内部でハイフンをバックティックにラップして、ハイフンが減算演算子として解釈されないようにします。

```sql
{%= profile.events.`order-total` > 100 %}
```

>[!NOTE]
>
>バックティックは、PQL エクスプレッション （`{%= ... %}`）内でのみサポートされています。 プレーンハンドルバーの補間（`{{...}}`）では受け付けられません。 ハイフネーション付きのフィールド値を直接レンダリングする必要がある場合は、PQL式を使用して検証するか、最初に`{% let %}`を使用して変数に格納します。

### レシピ 15 — コンテキスト属性で数値イベント IDを参照する {#recipe-numeric-event-id}

IDが数値文字列（例：`1697323153`）であるジャーニーコンテキストイベントを使用する場合、IDをバックティックでラップし、`{% let %}`を`toDateTime()`と`formatDate()`で使用します。

```handlebars
{% let appointmentDate = formatDate(toDateTime(context.journey.events.`1697323153`.timestamp), "dd/MM/yyyy HH:mm") %}
Your appointment: {{appointmentDate}}
```

出力（例）: `Your appointment: 18/03/2026 14:30`

### レシピ 16 – 型強制：文字列フィールドと数値を比較する {#recipe-type-coercion}

PQLは強く型付けされています。 プロファイルフィールドが文字列として保存されていて、数値で比較する必要がある場合は、最初に`stringToNumber()`で変換します。

```sql
{%= stringToNumber(profile.loyalty.pointsBalance) > 500 %}
```

文字列として保存されたブール型フィールドの場合：

```sql
{%= toBool(profile.consents.email.val) = true %}
```

## クイックリファレンス {#quick-reference}

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

>[!BEGINTABS]

>[!TAB 概要]

**TL;DR**

このページでは、Journey Optimizerの電子メール、SMS、プッシュコンテンツで使用する日付、配列、文字列、条件付きロジック、PQL edge ケースなど、すぐに使用できる16種類のパーソナライゼーションレシピをコピー&amp;ペーストして使用できます。

**インテント**

* すぐに使用できる日付/時間パターンをコピー（現在の日付、カウントダウン、オフセット日、時間表示、週末の検出）
* 配列とループのパターンをコピー（リスト項目、上位N項目、条件付き項目別レンダリング）
* 文字列の書式設定パターンのコピー（文字列のクリーニングと再利用、JSON引用符、大文字の日付コンポーネント）
* コンディショナルロジックパターンをコピー（マルチブランチ if/elseif/else、null-safe属性表示）
* PQL エッジケース（ハイフネートキー、数値イベント ID、型強制）の処理

>[!TAB 用語集]

* **Personalization recipe**：パーソナライゼーションエディターの構文を使用した、一般的なパーソナライゼーションのユースケースに対応した、すぐに使用できるコピー&amp;ペーストのパターン。 *（製品固有）*
* **`formatDate`**：指定された形式パターンを使用して日付を文字列に変換する関数（例：`"MMMM dd, yyyy"`）。
* **`dateDiff`**: 2つの日付の数値の差を計算する関数。
* **`getCurrentZonedDateTime()`**：現在の日時をタイムゾーンに応じた形式で返す関数。
* **`topN`**：配列を指定された数値フィールドで降順に並べ替え、上位N個の項目を返すPQL関数。 Handlebars ループで使用する前に、`{% let %}`を介して割り当てる必要があります。
* **`{% let %}`**：計算値を保存するためのHandlebars変数割り当て構文。後続のHandlebars コンテキストでPQL関数の結果を参照する必要がある場合に必要です。
* **`replaceAll`**：文字列内のパターンのすべての出現を置き換える文字列関数。元の文字列を変更せずに新しい文字列を返します。

>[!TAB 用語]

* **正規名：** パーソナライゼーションレシピ – バリアント：パターン、テンプレート、例、パターンのコピー&amp;ペースト
* **混同しないでください：** `{%= ... %}` （PQL式の構文 – 評価され、計算値を返します） ≠ `{{...}}` （Handlebars補間 – 変数またはテンプレート式をレンダリングします）
* **混同しないでください：** `{%#if%}` / `{%/if%}` （Journey Optimizerの条件付き構文、パーセント中括弧） ≠ `{{#if}}` / `{{/if}}` （標準のHandlebarsの条件付き構文）
* **混同しないでください：** `topN(array, field, n)` （フィールドを降順で並べ替え、上位Nを返します） ≠ `head(array)` （配列の最初の項目のみを返します）
* **混乱しないでください：** `dayOfWeek()` （メッセージのコンテンツで使用され、日に基づいて表示を調整する） ≠ ジャーニー時間条件「曜日」オプション （ジャーニー条件アクティビティで使用され、プロファイルのルートが異なる）
* **混同しないでください：**&#x200B;日付形式パターン `y` （暦年 – 正解）≠ `Y` （週ベースの年 – 年の境界で予期しない結果が発生する可能性があります）

>[!TAB  ガードレールと制限]

* `{{#each}}`はジャーニー条件アクティビティではサポートされていません。ジャーニー条件の配列フィルタリングにコレクション管理関数を使用してください。
* ハイフネーション付きの属性キーのバックティックエスケープは、PQL式（`{%= ... %}`）内でのみサポートされています。バックティックは、プレーンハンドルバー補間（`{{...}}`）では受け付けられません。
* `topN`はPQL関数であり、`{{#each}}` ループ ターゲットとして使用する前に`{% let %}`変数に割り当てる必要があります。
* `{%#if%}` ブロック内でループ変数を使用する場合、名前付きループエイリアスを宣言します（例：`as |order|`）。`this.status`は、`{%#if%}`内のPQL エバリュエーターによって解決されません。
* 暦年の`formatDate` パターンで小文字の`y`を使用します。`Y` （週ベースの年）は、年末の境界で予期しない値が生成される場合があります。

>[!TAB FAQ]

**Q: パーソナライゼーションにおける`{%= ... %}`と`{{...}}`の違いは何ですか？**

`{%= ... %}`はPQL式の構文です。この構文は評価され、計算された値（数値、文字列、ブール値）を返します。 `{{...}}`はHandlebars補間です。変数またはテンプレート式をレンダリングします。 どちらもパーソナライゼーションコンテンツに表示されますが、目的が異なります。

**Q: Handlebars `{{#each}}` ループ内でPQL関数の結果を使用するにはどうすればよいですか？**

PQL関数の結果を`{% let variableName = pqlFunction(...) %}`を使用して変数に割り当て、`{{#each variableName}}`を使用して反復処理します。

**Q: `{{#each}}`をジャーニー条件アクティビティで使用できますか？**

いいえ。 `{{#each}}`は、メッセージのパーソナライゼーションコンテンツ（電子メール、SMS、プッシュ通知）でのみ使用できます。 ジャーニー条件での配列フィルタリングの場合は、コレクション管理関数を使用します。

**Q：名前にハイフンが含まれるフィールドを参照する方法を教えてください。**

ハイフネーションされたキーをPQL式の内部でバックティックにラップします：`{%= profile.events.\`order-total\&#39; > 100 %}`. Backticks are not supported in plain Handlebars interpolation — use a `{% let %}&#39;変数を必要に応じて中間ステップとして使用します。

**Q: `topN`さんが`{{#each}}` ループの前に`{% let %}`を必要とするのはなぜですか？**

`topN`は、PQL リストを返すPQL関数です。 `{% let %}`変数に割り当てると、結果はHandlebars コンテキストで利用できるようになり、`{{#each}}`で反復できるようになります。

>[!ENDTABS]

<!-- ai-section-version: 1 | source-hash: 20c7ee0f -->


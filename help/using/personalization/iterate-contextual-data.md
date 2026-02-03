---
solution: Journey Optimizer
product: journey optimizer
title: コンテキストデータの反復処理
description: Handlebars 構文を使用して、様々なコンテキストソースからの配列を反復処理する方法について説明します
feature: Personalization
topic: Personalization
role: Developer
level: Intermediate
keywords: 式, エディター, Handlebars, 反復, 配列, コンテキスト, パーソナライゼーション
source-git-commit: a0e8ca1b45818014993c37ac41f25e30ee1d1bb5
workflow-type: ht
source-wordcount: '3008'
ht-degree: 100%

---

# コンテキストデータの反復処理 {#personalization-contexts}

Handlebars 反復構文を使用して、イベント、カスタムアクション応答、他のコンテキストデータなど、様々なソースからのデータの動的なリストをメッセージに表示する方法について説明します。

## 概要 {#overview}

Journey Optimizer では、[メッセージのパーソナライゼーション](personalize.md)中に複数のソースからのコンテキストデータにアクセスできます。ネイティブチャネル（[メール](../email/get-started-email-design.md)、[プッシュ](../push/create-push.md)、[SMS](../sms/create-sms.md)）で Handlebars 構文を使用して、これらのソースからの配列を反復処理し、製品リスト、レコメンデーション、その他の繰り返し要素などの動的コンテンツを表示できます。

**使用可能なコンテキストソース：**

* **[イベント](#event-data)**：ジャーニーイベント（ビジネスイベント、単一イベント）からのデータ
* **[カスタムアクションの応答](#custom-action-responses)**：カスタムアクションを介した外部 API 呼び出しから返されたデータ
* **[データセット参照](#dataset-lookup)**：Adobe Experience Platform データセットから取得した強化されたデータ
* **[技術プロパティ](#technical-properties)**：ジャーニー ID や補足識別子などのジャーニーメタデータ
* **[ジャーニーコンテキスト](#other-contexts)**：実行中にアクセス可能なその他のジャーニー関連データ

このガイドでは、メッセージ内の各ソースからの配列を反復処理する方法と、ジャーニーアクティビティを設定する際に配列を操作する方法について説明します。メッセージのパーソナライゼーションの基本を理解するには、[Handlebars 反復構文](#syntax)から始めるか、[ジャーニー式での配列の操作](#arrays-in-journeys)を参照して、配列データをカスタムアクションやデータセット参照に渡す方法を学んでください。

## Handlebars 反復構文 {#syntax}

Handlebars には、配列を反復処理する `{{#each}}` [ヘルパー](functions/helpers.md)が用意されています。基本構文は次のとおりです。

```handlebars
{{#each arrayPath as |item|}}
  <!-- Access item properties here -->
  {{item.property}}
{{/each}}
```

**主なポイント：**

* `arrayPath` を配列データへのパスに置き換えます
* `item` を任意の変数名（例：`product`、`response`、`element`）に置き換えます
* `{{item.propertyName}}` を使用して各項目のプロパティにアクセスします
* マルチレベルの配列に対して複数の `{{#each}}` ブロックをネストできます

## イベントデータの反復処理 {#event-data}

イベントデータは、ジャーニーが[イベント](../event/about-events.md)によりトリガーされた際に使用できます。これは、買い物かごの内容、注文項目、フォームの送信など、ジャーニーが開始された時点でキャプチャされたデータを表示するのに役立ちます。

>[!TIP]
>
>イベントデータを他のソースと組み合わせることができます。例について詳しくは、[複数のコンテキストソースの組み合わせ](#combine-sources)を参照してください。

### イベントのコンテキストパス

```handlebars
context.journey.events.<event_ID>.<fieldPath>
```

* `<event_ID>`：ジャーニーで設定されたイベントの一意の ID
* `<fieldPath>`：イベントスキーマ内のフィールドまたは配列へのパス

### 例：イベントからの買い物かご項目

[イベントスキーマ](../event/experience-event-schema.md)に `productListItems` 配列（標準 [XDM 形式](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/product-list-item.html?lang=ja){target="_blank"}）が含まれている場合は、以下のサンプルに示すように買い物かごの内容を表示できます。

+++ サンプルコードを表示

```handlebars
{{#each context.journey.events.event_ID.productListItems as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    <p>Quantity: {{product.quantity}}</p>
    <p>Price: ${{product.priceTotal}}</p>
  </div>
{{/each}}
```

+++

### 例：イベントでネストされた配列

ネストされた構造には、ネストされた `{{#each}}` ブロックを使用します。

+++ サンプルコードを表示

```handlebars
{{#each context.journey.events.event_ID.categories as |category|}}
  <h2>{{category.name}}</h2>
  <ul>
    {{#each category.items as |item|}}
      <li>{{item.title}}</li>
    {{/each}}
  </ul>
{{/each}}
```

+++

ネストについて詳しくは、[ベストプラクティス](#best-practices)を参照してください。

## カスタムアクション応答の反復処理 {#custom-action-responses}

[カスタムアクション](../action/about-custom-action-configuration.md)応答には、外部 API 呼び出しから返されたデータが含まれます。これは、ロイヤルティポイント、製品レコメンデーション、在庫ステータス、パーソナライズされたオファーなど、システムからのリアルタイム情報を表示するのに役立ちます。

>[!NOTE]
>
>この機能を使用するには、応答ペイロードを使用してカスタムアクションを設定する必要があります。詳しくは、[この節](../action/action-response.md#config-response)を参照してください。また、カスタムアクション応答をイベントデータやデータセット参照と組み合わせることもできます。例について詳しくは、[複数のコンテキストソースの組み合わせ](#combine-sources)を参照してください。

### カスタムアクションのコンテキストパス

```handlebars
context.journey.actions.<actionName>.<fieldPath>
```

* `<actionName>`：ジャーニーで設定された[カスタムアクション](../action/about-custom-action-configuration.md)の名前
* `<fieldPath>`：応答ペイロード内のフィールドまたは配列へのパス

### 例：API からの製品レコメンデーション

カスタムアクションから返された製品レコメンデーションの配列を反復処理し、メッセージに個別のカードとして表示するには、以下の例を参照してください。

+++ サンプルコードを表示

**API 応答：**

```json
{
  "recommendations": [
    {
      "productId": "12345",
      "productName": "Summer Jacket",
      "price": 89.99,
      "imageUrl": "https://example.com/jacket.jpg"
    },
    {
      "productId": "67890",
      "productName": "Running Shoes",
      "price": 129.99,
      "imageUrl": "https://example.com/shoes.jpg"
    }
  ]
}
```

**メッセージのパーソナライゼーション：**

```handlebars
<h2>Recommended for You</h2>
<div class="recommendations">
  {{#each context.journey.actions.GetRecommendations.recommendations as |item|}}
    <div class="product-card">
      <img src="{{item.imageUrl}}" alt="{{item.productName}}" />
      <h3>{{item.productName}}</h3>
      <p class="price">${{item.price}}</p>
    </div>
  {{/each}}
</div>
```

+++

### 例：カスタムアクションからのネストされた配列

ネストされた配列（各オブジェクトに別の配列が含まれるオブジェクトの配列）を含むカスタムアクション応答を反復処理するには、以下の例を参照してください。これは、ネストされた `{{#each}}` ループを使用して複数のレベルのデータにアクセスする方法を示しています。

+++ サンプルコードを表示

**API 応答：**

```json
{    
  "id": "84632848268632",    
  "responses": [
    { "productIDs": [1111, 2222, 3333] },
    { "productIDs": [4444, 5555, 6666] },
    { "productIDs": [7777, 8888, 9999] }
  ]
}
```

**メッセージのパーソナライゼーション：**

```handlebars
<h2>Product Groups</h2>
{{#each context.journey.actions.GetProducts.responses as |response|}}
  <div class="product-group">
    <ul>
      {{#each response.productIDs as |productID|}}
        <li>Product ID: {{productID}}</li>
      {{/each}}
    </ul>
  </div>
{{/each}}
```

+++

より複雑なネストパターンについて詳しくは、[ベストプラクティス](#best-practices)を参照してください。

### 例：ロイヤルティ層のメリット

ロイヤルティステータスに基づいて動的なメリットを表示するには、以下の例を参照してください。

+++ サンプルコードを表示

**API 応答：**

```json
{
  "loyaltyTier": "gold",
  "benefits": [
    { "name": "Free shipping", "icon": "truck" },
    { "name": "20% discount", "icon": "percent" },
    { "name": "Priority support", "icon": "headset" }
  ]
}
```

**メッセージのパーソナライゼーション：**

```handlebars
<h2>Your {{context.journey.actions.GetLoyaltyInfo.loyaltyTier}} Member Benefits</h2>
<ul class="benefits">
  {{#each context.journey.actions.GetLoyaltyInfo.benefits as |benefit|}}
    <li>
      <span class="icon-{{benefit.icon}}"></span>
      {{benefit.name}}
    </li>
  {{/each}}
</ul>
```

+++

## データセット参照結果の反復処理 {#dataset-lookup}

[データセット参照アクティビティ](../building-journeys/dataset-lookup.md)を使用すると、ジャーニーの実行中に [Adobe Experience Platform データセット](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja){target="_blank"}からデータを取得できます。強化されたデータは、配列として保存され、メッセージ内で反復処理できます。

>[!AVAILABILITY]
>
>データセット参照アクティビティは、制限された組織のみが使用できます。アクセスするには、アドビ担当者にお問い合わせください。

データセット参照アクティビティの設定について詳しくは、[この節](../building-journeys/dataset-lookup.md)を参照してください。 データセット参照は、イベントデータと組み合わせると特に強力です。実用的なユースケースについて詳しくは、[例：データセット参照を使用して強化されたイベントデータ](#combine-sources)を参照してください。

### データセット参照のコンテキストパス

```handlebars
context.journey.datasetLookup.<activityID>.entities
```

* `<activityID>`：データセット参照アクティビティの一意の ID
* `entities`：データセットから取得した強化されたデータの配列

### 例：データセットからの製品詳細

データセット参照アクティビティを使用して、SKU に基づいて製品情報を取得する場合は、以下のサンプルを参照してください。

+++ サンプルコードを表示

**データセット参照の設定：**

* 参照キー：`list(@event{purchase_event.products.sku})`
* 返されるフィールド：`["SKU", "category", "price", "name"]`

**メッセージのパーソナライゼーション：**

```handlebars
<h2>Product Details</h2>
<table>
  <thead>
    <tr>
      <th>Product Name</th>
      <th>Category</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    {{#each context.journey.datasetLookup.3709000.entities as |product|}}
      <tr>
        <td>{{product.name}}</td>
        <td>{{product.category}}</td>
        <td>${{product.price}}</td>
      </tr>
    {{/each}}
  </tbody>
</table>
```

+++

### 例：データセットデータを使用してフィルタリングされた反復

反復中にデータセット参照結果をフィルタリングし、特定の条件に一致する項目（例：特定のカテゴリからの製品）のみを表示するには、`{{#each}}` ループ内で条件付き `{{#if}}` ステートメントを使用します。以下の例を参照してください。

+++ サンプルコードを表示

```handlebars
<h2>Household Products</h2>
{{#each context.journey.datasetLookup.3709000.entities as |product|}}
  {{#if product.category = "household"}}
    <div class="product">
      <h3>{{product.name}}</h3>
      <p>Price: ${{product.price}}</p>
    </div>
  {{/if}}
{{/each}}
```

+++

条件付きフィルタリングについて詳しくは、[ベストプラクティス](#best-practices)を参照してください。

### 例：データセット参照からの合計の計算

データセット参照結果を反復処理しながら合計を計算して表示するには、以下の例を参照してください。

+++ サンプルコードを表示

```handlebars
{% let householdTotal = 0 %}
{{#each context.journey.datasetLookup.3709000.entities as |product|}}
  {%#if product.category = "household"%}
    {% let householdTotal = householdTotal + product.price %}
  {%/if%}
{{/each}}

<p>Your household products total: ${{householdTotal}}</p>
```

+++

## ジャーニーの技術プロパティの使用 {#technical-properties}

ジャーニーの技術プロパティには、ジャーニー ID や補足識別子など、ジャーニー実行に関するメタデータへのアクセス権が用意されてします。これらは、反復パターンと組み合わせると、特に特定のジャーニーインスタンスに基づいて配列をフィルタリングする際に役立つ場合があります。

### 使用可能な技術プロパティ

```handlebars
context.journey.technicalProperties.journeyUID
context.journey.technicalProperties.supplementalId
```

### 例：補足識別子を使用した配列項目のフィルタリング

配列を含むイベントトリガージャーニーで補足識別子を使用する際は、フィルタリングして、現在のジャーニーインスタンスに関連する項目のみを表示できます。補足識別子について詳しくは、[このガイド](../building-journeys/supplemental-identifier.md)を参照してください。

**シナリオ**：複数の予約でジャーニーがトリガーされますが、このジャーニーインスタンスをトリガーした特定の予約（補足 ID で識別）の情報のみを表示する必要があります。

+++ サンプルコードを表示

```handlebars
{{#each context.journey.events.event_ID.bookingList as |booking|}}
  {%#if booking.bookingInfo.bookingNum = context.journey.technicalProperties.supplementalId%}
    <div class="booking-details">
      <h3>Your Booking: {{booking.bookingInfo.bookingNum}}</h3>
      <p>Destination: {{booking.bookingInfo.bookingCountry}}</p>
      <p>Date: {{booking.bookingInfo.bookingDate}}</p>
    </div>
  {%/if%}
{{/each}}
```

+++

### 例：トラッキング用のジャーニー ID を含める

トラッキングの目的でメッセージにジャーニー ID を含めるには、以下の例を参照してください。

+++ サンプルコードを表示

```handlebars
<footer>
  <p>Journey Reference: {{context.journey.technicalProperties.journeyUID}}</p>
</footer>
```

+++

## 複数のコンテキストソースの組み合わせ {#combine-sources}

様々なソースからのデータを同じメッセージに組み合わせて、リッチでパーソナライズされたエクスペリエンスを作成できます。この節では、複数のコンテキストソースを組み合わせて使用する実用的な例を示します。

**組み合わせることができるコンテキストソース：**

* [イベントデータ](#event-data) + [カスタムアクション応答](#custom-action-responses)
* [イベントデータ](#event-data) + [データセット参照](#dataset-lookup)
* [複数のソース](#combine-sources) + [技術プロパティ](#technical-properties)

### 例：リアルタイムの在庫を含む買い物かご項目

イベントデータ（買い物かごの内容）とカスタムアクションデータ（在庫ステータス）を組み合わせるには、以下のサンプルを参照してください。

+++ サンプルコードを表示

```handlebars
<h2>Your Cart</h2>
{{#each context.journey.events.cartEvent.productListItems as |product|}}
  <div class="cart-item">
    <h3>{{product.name}}</h3>
    <p>Quantity: {{product.quantity}}</p>
    <p>Price: ${{product.priceTotal}}</p>
  </div>
{{/each}}

<h2>We Also Recommend</h2>
{{#each context.journey.actions.GetRecommendations.items as |recommendation|}}
  <div class="recommendation">
    <h4>{{recommendation.name}}</h4>
    <p>${{recommendation.price}}</p>
    {{#if recommendation.inStock}}
      <span class="badge">In Stock</span>
    {{else}}
      <span class="badge out-of-stock">Out of Stock</span>
    {{/if}}
  </div>
{{/each}}
```

+++

### 例：データセット参照を使用して強化されたイベントデータ

[イベント SKU](#event-data) と[データセット参照](#dataset-lookup)からの詳細な製品情報を組み合わせるには、以下のサンプルを参照してください。

+++ サンプルコードを表示

```handlebars
<h2>Your Order Details</h2>
{{#each context.journey.events.orderEvent.productListItems as |item|}}
  <div class="order-item">
    <p><strong>SKU:</strong> {{item.SKU}}</p>
    <p><strong>Quantity:</strong> {{item.quantity}}</p>
    
    <!-- Enrich with dataset lookup data -->
    {{#each context.journey.datasetLookup.1234567.entities as |enrichedProduct|}}
      {{#if enrichedProduct.SKU = item.SKU}}
        <p><strong>Product Name:</strong> {{enrichedProduct.name}}</p>
        <p><strong>Category:</strong> {{enrichedProduct.category}}</p>
        <img src="{{enrichedProduct.imageUrl}}" alt="{{enrichedProduct.name}}" />
      {{/if}}
    {{/each}}
  </div>
{{/each}}
```

+++

### 例：複数のソースと技術プロパティの組み合わせ

複数のコンテキストソース（プロファイルデータ、イベントデータ、カスタムアクション、技術プロパティ）を 1 つのメッセージに組み合わせるには、以下のサンプルを参照してください。

+++ サンプルコードを表示

```handlebars
<div class="personalized-content">
  <!-- Profile data -->
  <h1>Hello {{profile.person.name.firstName}},</h1>
  
  <!-- Event data iteration -->
  <h2>Your Recent Purchases</h2>
  {{#each context.journey.events.purchaseEvent.items as |purchase|}}
    <div class="purchase">
      <p>{{purchase.productName}} - ${{purchase.price}}</p>
    </div>
  {{/each}}
  
  <!-- Custom action response iteration -->
  <h2>Recommended for You</h2>
  {{#each context.journey.actions.GetPersonalizedRecs.recommendations as |rec|}}
    <div class="recommendation">
      <h3>{{rec.title}}</h3>
      <p>{{rec.description}}</p>
    </div>
  {{/each}}
  
  <!-- Technical properties -->
  <footer>
    <p class="fine-print">Journey ID: {{context.journey.technicalProperties.journeyUID}}</p>
  </footer>
</div>
```

+++

## その他のコンテキストタイプ {#other-contexts}

このガイドでは配列の反復処理に焦点を当てていますが、通常は反復を必要としないその他のコンテキストタイプもパーソナライゼーションに使用できます。これらは、ループ処理ではなく直接アクセスされます。

* **[プロファイル属性](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}**（`profile.*`）：Adobe Experience Platform の個々のプロファイルフィールド
* **[オーディエンス](../audience/about-audiences.md)**（`inAudience()`）：オーディエンスメンバーシップの確認
* **[オファーの決定](../offers/get-started/starting-offer-decisioning.md)**：意思決定管理オファー
* **[ターゲット属性](../orchestrated/activities/channels.md#add-personalization)**（オーケストレートキャンペーンのみ）：キャンペーンキャンバスで計算される属性
* **トークン**（`context.token`）：セッションまたは認証トークン

これらのソースを使用した完全なパーソナライゼーション構文と例について詳しくは、以下を参照してください。

* [パーソナライゼーションの追加](personalization-build-expressions.md)
* [パーソナライゼーション構文](personalization-syntax.md)

## ジャーニー式での配列の操作 {#arrays-in-journeys}

前の節では、Handlebars を使用したメッセージのパーソナライゼーションでの配列の反復処理に焦点を当てていますが、ジャーニーアクティビティを設定する際にも配列を操作します。この節では、特にカスタムアクションにデータを渡す場合やデータセット参照で配列を使用する際に、ジャーニー式のイベントからの配列データを使用する方法について説明します。

>[!IMPORTANT]
>
>ジャーニー式では、Handlebars のパーソナライゼーションとは異なる構文が使用されます。ジャーニー設定（カスタムアクションのパラメーターや条件など）では、`first`、`all`、`serializeList` などの関数を含む[ジャーニー式エディター](../building-journeys/expression/expressionadvanced.md)を使用します。メッセージコンテンツでは、`{{#each}}` ループを含む Handlebars 構文を使用します。

### カスタムアクションパラメーターへの配列値の受け渡し {#arrays-to-custom-actions}

[カスタムアクション](../action/about-custom-action-configuration.md)を設定する際、多くの場合、イベント配列から値を抽出し、パラメーターとして渡す必要があります。この節では、一般的なパターンについて説明します。

コレクションを渡す方法について詳しくは、[カスタムアクションパラメーターへのコレクションの受け渡し](../building-journeys/collections.md#passing-collection)を参照してください。

#### 配列からの 1 つの値の抽出

**ユースケース**：イベント配列から特定のフィールドを取得し、GET リクエストでクエリパラメーターとして渡します。

+++ サンプルコードを表示

**シナリオの例**：製品リストから価格が 0 を超える最初の SKU を抽出します。

**イベントスキーマの例**：

```json
{
  "commerce": {
    "productListItems": [
      { "SKU": "SKU-1", "priceTotal": 10.0 },
      { "SKU": "SKU-2", "priceTotal": 0.0 },
      { "SKU": "SKU-3", "priceTotal": 20.0 }
    ]
  }
}
```

**カスタムアクション設定**：

1. カスタムアクションで、クエリパラメーター（例：`sku`）を `string` タイプで設定します
2. 動的な値を許可するには、`Variable` としてマークします

**アクションパラメーターのジャーニー式**：

```javascript
@event{YourEventName.commerce.productListItems.first(currentEventField.priceTotal > 0).SKU}
```

**説明**：

* `@event{YourEventName}`：ジャーニーイベントを参照します
* `.first(currentEventField.condition)`：条件に一致する最初の配列項目を返します
* `currentEventField`：イベント配列内の各項目をループ処理する際に表します
* `.SKU`：一致した項目から SKU フィールドを抽出します
* 結果：`"SKU-1"`（アクションパラメーターに適した文字列）

`first` 関数について詳しくは、[コレクション管理関数](../building-journeys/expression/collection-management-functions.md)を参照してください。

+++

#### 配列からの値のリストの作成

**ユースケース**：クエリパラメーターとして渡す ID のコンマ区切りリストを作成します（例：`/products?ids=sku1,sku2,sku3`）。

+++ サンプルコードを表示

**カスタムアクション設定**：

1. クエリパラメーター（例：`ids`）を `string` タイプで設定します
2. `Variable` としてマークします

**ジャーニー式**：

```javascript
serializeList(
  @event{YourEventName.commerce.productListItems.all(currentEventField.priceTotal > 0).SKU},
  ",",
  true
)
```

**説明**：

* `.all(currentEventField.condition)`：条件に一致するすべての配列項目を返します（リストを返します）
* `currentEventField`：イベント配列内の各項目をループ処理する際に表します
* `.SKU`: SKU 値のみを含めるようにリストをプロジェクト化します
* `serializeList(list, delimiter, addQuotes)`：リストを文字列に結合します
   * `","`：区切り文字としてコンマを使用します
   * `true`：各文字列要素を引用符で囲みます
* 結果：`"SKU-1,SKU-3"`（クエリパラメーターに適しています）

詳細情報：

* [`all`](../building-journeys/expression/collection-management-functions.md)
* [`serializeList`](../building-journeys/functions/list-functions.md#serializeList)

カスタムアクションのコレクション処理について詳しくは、[カスタムアクションパラメーターへのコレクションの受け渡し](../building-journeys/collections.md#passing-collection)を参照してください。

+++

#### カスタムアクションへのオブジェクトの配列の受け渡し

**ユースケース**：オブジェクトの完全な配列をリクエスト本文で送信します（本文を含む POST または GET の場合）。

+++ サンプルコードを表示

**リクエスト本文の例**：

```json
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "Product A",
        "price": 20.1,
        "color": "blue"
      }
    ]
  }
}
```

**カスタムアクション設定**：

1. リクエスト本文で、`products` を `listObject` タイプとして定義します
2. `Variable` としてマークします
3. オブジェクトフィールド `id`、`name`、`price`、`color` を定義します（それぞれがマッピング可能になります）

**ジャーニーキャンバス設定**：

1. 詳細設定モードで、コレクション式を設定します。

   ```javascript
   @event{YourEventName.commerce.productListItems.all(currentEventField.priceTotal > 0)}
   ```

1. コレクションマッピング UI で、次の操作を実行します。
   * `id` → `productListItems.SKU` にマッピング
   * `name` → `productListItems.name` にマッピング
   * `price` → `productListItems.priceTotal` にマッピング
   * `color` → `productListItems.color` にマッピング

Journey Optimizer は、アクションペイロード構造に一致するオブジェクトの配列を構築します。

>[!NOTE]
>
>イベント配列を操作する場合は、`currentEventField` を使用して各項目を参照します。データソースコレクション（Adobe Experience Platform）には、`currentDataPackField` を使用します。カスタムアクション応答コレクションには、`currentActionField` を使用します。

詳しくは、[カスタムアクションパラメーターへのコレクションの受け渡し](../building-journeys/collections.md#passing-collection)を参照してください。

+++

### データセット参照での配列の使用 {#arrays-with-dataset-lookup}

[データセット参照アクティビティ](../building-journeys/dataset-lookup.md)を使用する際、値の配列を参照キーとして渡して、強化されたデータを取得できます。

**例**：イベント配列内のすべての SKU の製品詳細を参照します。

+++ サンプルコードを表示

**データセット参照の設定**：

参照キーフィールドでは、`list()` を使用して配列パスをリストに変換します。

```javascript
list(@event{purchaseEvent.productListItems.SKU})
```

これにより、データセットで参照するすべての SKU 値のリストが作成されます。結果は、`context.journey.datasetLookup.<activityID>.entities` の配列として使用でき、メッセージ内で反復処理できます（[データセット参照結果の反復処理](#dataset-lookup)を参照）。

+++

### 制限とパターン {#array-limitations}

ジャーニーで配列を操作する際は、次の制限に注意してください。

#### ジャーニーフローで配列に動的なループはない

ジャーニーでは、配列内の各項目に対して 1 つのアクションノードが複数回実行される動的なループを作成できません。これは、制御できないパフォーマンスの問題を防ぐことを目的としています。

**実行できない内容**：

* カスタムアクションを配列項目ごとに 1 回動的に実行する
* 配列の長さに基づいて複数のジャーニー分岐を作成する

**代わりに推奨されるパターン**：

1. **すべての項目を一度に送信**：配列全体またはシリアル化されたリストを、すべての項目を処理する単一のカスタムアクションに渡します。[配列からの値のリストの作成](#arrays-to-custom-actions)を参照してください。

2. **外部集計を使用**：外部 API で複数の ID を受け入れ、1 回の呼び出しで組み合わされた結果を返すようにします。

3. **AEP で事前計算**：[計算属性](../audience/computed-attributes.md)を使用して、プロファイルレベルで配列から値を事前計算します。

4. **単一値の抽出**：必要な値が 1 つのみの場合は、`first` または `head` を使用して抽出します。詳しくは、[配列からの 1 つの値の抽出](#arrays-to-custom-actions)を参照してください。

詳しくは、[ガードレールと制限](../start/guardrails.md)を参照してください。

#### 配列サイズの考慮事項

大規模な配列は、ジャーニーのパフォーマンスに影響を与える場合があります。

* **イベント配列**：イベントペイロードの合計を 50 KB 未満に抑えます
* **カスタムアクション応答**：応答ペイロードは 100 KB 未満にする必要があります
* **データセット参照結果**：参照キーと返されるエンティティの数を制限します

### 完全な例：カスタムアクションに対するイベント配列 {#complete-example}

カスタムアクションでイベント配列を使用する方法を示す完全なワークフローを以下に示します。

**シナリオ**：ユーザーが買い物かごを放棄すると、買い物かごのデータを外部のレコメンデーション API に送信してパーソナライズされた提案を取得し、メールで表示します。

+++ サンプルコードを表示

**手順 1：カスタムアクションを設定**

カスタムアクション「GetCartRecommendations」を作成します。

* **メソッド**：POST
* **URL**：`https://api.example.com/recommendations`
* **リクエスト本文**：

```json
{
  "cartItems": [
    {
      "sku": "string",
      "price": 0,
      "quantity": 0
    }
  ]
}
```

* `cartItems` を `listObject` および `Variable` タイプとしてマークします
* `sku`（文字列）、`price`（数値）、`quantity`（整数） のフィールドを定義します

詳しくは、[カスタムアクションの設定](../action/about-custom-action-configuration.md)を参照してください。

**手順 2：応答ペイロードを設定**

カスタムアクションで、応答を設定します。

```json
{
  "recommendations": [
    {
      "productId": "string",
      "productName": "string",
      "price": 0,
      "imageUrl": "string"
    }
  ]
}
```

詳しくは、[API 呼び出し応答の使用](../action/action-response.md)を参照してください。

**手順 3：ジャーニー内のアクションを関連付け**

1. 買い物かごの放棄イベントの後に、カスタムアクションを追加します
1. `cartItems` コレクションの詳細設定モードの場合：

   ```javascript
   @event{cartAbandonment.commerce.productListItems.all(currentEventField.quantity > 0)}
   ```

1. コレクションフィールドをマッピングします。
   * `sku` → `productListItems.SKU`
   * `price` → `productListItems.priceTotal`
   * `quantity` → `productListItems.quantity`

**手順 4：メールで応答を使用**

メールコンテンツで、レコメンデーションを反復処理します。

```handlebars
<h2>We noticed you left these items in your cart</h2>
{{#each context.journey.events.cartAbandonment.productListItems as |item|}}
  <div class="cart-item">
    <p>{{item.name}} - Quantity: {{item.quantity}}</p>
  </div>
{{/each}}

<h2>You might also like</h2>
{{#each context.journey.actions.GetCartRecommendations.recommendations as |rec|}}
  <div class="recommendation">
    <img src="{{rec.imageUrl}}" alt="{{rec.productName}}" />
    <h3>{{rec.productName}}</h3>
    <p>${{rec.price}}</p>
  </div>
{{/each}}
```

**手順 5：設定をテスト**

ライブジャーニーを実行する前に、アクション設定の「テストリクエストを送信」機能を使用してカスタムアクションをテストし、作成されたリクエストと値を確認します。

1. [ジャーニーテストモード](../building-journeys/testing-the-journey.md)を使用します
2. `productListItems` 配列を含むサンプルイベントデータでトリガーします
3. カスタムアクションが正しい配列構造を受け取ることを確認します
4. [アクションテストログ](../action/action-response.md#test-mode-logs)を確認します
5. メールをプレビューして、両方の配列が正しく表示されていることを確認します

詳しくは、[カスタムアクションのトラブルシューティング](../action/troubleshoot-custom-action.md)を参照してください。

+++

## ベストプラクティス {#best-practices}

コンテキストデータを反復処理して、維持可能でパフォーマンスの高いパーソナライゼーションを作成する際は、次のベストプラクティスに従います。

### わかりやすい変数名の使用

反復処理している内容を明確に示す変数名を選択します。これにより、コードの読みやすさが向上し、維持が容易になります。詳しくは、[パーソナライゼーション構文](personalization-syntax.md)を参照してください。

+++ サンプルコードを表示

```handlebars
<!-- Good -->
{{#each products as |product|}}
{{#each users as |user|}}
{{#each recommendations as |recommendation|}}

<!-- Less clear -->
{{#each items as |item|}}
{{#each array as |element|}}
```

+++

### ループ内の式フラグメント

`{{#each}}` ループ内で[式フラグメント](use-expression-fragments.md)を使用する際は、ループ範囲の変数をフラグメントパラメーターとして渡すことができないことに注意してください。ただし、フラグメントは、フラグメント外部のメッセージコンテンツで定義されているグローバル変数にアクセスできます。

+++ サンプルコードを表示

**サポートされているパターン - グローバル変数の使用：**

```handlebars
{% let globalDiscount = 15 %}

{{#each context.journey.actions.GetProducts.items as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    {{fragment id='ajo:fragment123/variant456' mode='inline'}}
  </div>
{{/each}}
```

`globalDiscount` はメッセージ内でグローバルに定義されているので、フラグメントはこれを参照できます。

**サポートされていないパターン - ループ変数の受け渡し：**

```handlebars
{{#each products as |product|}}
  <!-- This will NOT work as expected -->
  {{fragment id='ajo:fragment123/variant456' currentProduct=product}}
{{/each}}
```

**回避策**：フラグメントを使用する代わりに、パーソナライゼーションロジックをループ内に直接含めるか、ループの外でフラグメントを呼び出します。

+++

例やその他の回避策などについて詳しくは、[ループ内の式フラグメントの使用](use-expression-fragments.md#fragments-in-loops)を参照してください。



### 空の配列の処理

配列が空の場合にフォールバックコンテンツを指定するには、 `{{else}}` 句を使用します。詳しくは、[ヘルパー関数](functions/helpers.md)を参照してください。

+++ サンプルコードを表示

```handlebars
{{#each context.journey.actions.GetRecommendations.items as |item|}}
  <div>{{item.name}}</div>
{{else}}
  <p>No recommendations available at this time.</p>
{{/each}}
```

+++

### 条件付きヘルパーとの組み合わせ

条件付きコンテンツの場合は、ループ内で `{{#if}}` を使用します。 詳しくは、[条件付きルール](create-conditions.md)を参照し、[カスタムアクション応答](#custom-action-responses)および[データセット参照](#dataset-lookup)の節の例を参照してください。

+++ サンプルコードを表示

```handlebars
{{#each context.journey.actions.GetProducts.items as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    {{#if product.onSale}}
      <span class="badge">On Sale!</span>
    {{/if}}
    {{#if product.newArrival}}
      <span class="badge">New</span>
    {{/if}}
  </div>
{{/each}}
```

+++

### パフォーマンスの反復の制限

大規模な配列の場合は、反復回数を制限することを考慮します。

+++ サンプルコードを表示

```handlebars
<!-- Display only first 5 items -->
{{#each context.journey.actions.GetProducts.items as |product|}}
  {{#if @index < 5}}
    <div>{{product.name}}</div>
  {{/if}}
{{/each}}
```

+++

### 配列メタデータへのアクセス

Handlebars には、ループ内で高度な反復パターンを実行するのに役立つ特別な変数が用意されています。

* `@index`：現在の反復インデックス（0 ベース）
* `@first`：最初の反復の場合は True
* `@last`：最後の反復の場合は True

+++ サンプルコードを表示

```handlebars
{{#each products as |product|}}
  <div class="product {{#if @first}}featured{{/if}}">
    {{@index}}. {{product.name}}
  </div>
{{/each}}
```

+++

>[!NOTE]
>
>これらの Handlebars 変数（`@index`、`@first`、`@last`）は、メッセージのパーソナライゼーションの `{{#each}}` ループ内でのみ使用できます。ジャーニー式で配列を操作する場合（カスタムアクションに渡す前に配列から最初の項目を取得するなど）は、[`head`](../personalization/functions/arrays-list.md#head)、[`first`](../building-journeys/expression/collection-management-functions.md)、[`all`](../building-journeys/expression/collection-management-functions.md) などの配列関数を使用します。詳しくは、[ジャーニー式での配列の操作](#arrays-in-journeys)を参照してください。

## トラブルシューティング {#troubleshooting}

反復に問題がありますか？この節では、一般的な問題と解決策について説明します。

### 配列に表示されない

**問題**：配列の反復にコンテンツが表示されません。

+++ 考えられる原因と解決策を表示

**考えられる原因と解決策**：

1. **パスが正しくない**：コンテキストソースに基づいて、配列への正確なパスを確認します。
   * [イベント](#event-data)の場合：`context.journey.events.<event_ID>.<fieldPath>`
   * [カスタムアクション](#custom-action-responses)の場合：`context.journey.actions.<actionName>.<fieldPath>`
   * [データセット参照](#dataset-lookup)の場合：`context.journey.datasetLookup.<activityID>.entities`

2. **配列が空である**：`{{else}}` 句を追加して、配列にデータがないかどうかを確認します。例について詳しくは、[ベストプラクティス](#best-practices)を参照してください。

3. **データがまだ使用できない**：ジャーニーフロー内のメッセージアクティビティの前に、カスタムアクション、イベント、データセット参照アクティビティが実行されていることを確認します。

+++

### 構文エラー

**問題**：式の検証が失敗するか、メッセージがレンダリングされません。

+++ 一般的なミスを表示

**一般的なミス**：

* 終了タグが欠落している：すべての `{{#each}}` には `{{/each}}` が必要です。適切な構造について詳しくは、[Handlebars 反復構文](#syntax)を参照してください。
* 変数名が正しくない：ブロック全体で変数名を一貫して使用します。命名規則について詳しくは、[ベストプラクティス](#best-practices)を参照してください。
* パス区切り文字が正しくない：スラッシュやその他の文字ではなく、ドット（`.`）を使用します

+++

### ループ内で式フラグメントが機能しない

**問題**：式フラグメントが `{{#each}}` ループ内で使用された際、期待されるコンテンツが表示されないか、空または期待されない出力が表示されます。

+++ 考えられる原因と解決策を表示

**考えられる原因と解決策**：

1. **ループ変数をパラメーターとして渡そうとしている**：式フラグメントは、ループ範囲の変数（現在の反復項目など）をパラメーターとして受け取ることができません。これは既知の制限です。

   **解決策**：次のいずれかの回避策を使用します。

   * フラグメントがアクセスできるグローバル変数をメッセージ内に定義する
   * フラグメントを使用する代わりに、パーソナライゼーションロジックをループ内に直接含める
   * ループ固有のデータを必要としない場合は、ループの外でフラグメントを呼び出す

2. **フラグメントが使用できないパラメーターを想定している**：フラグメントが特定の入力パラメーターを受け取るようにデザインされた場合、これらのパラメーターをループ内から渡すことができないと、フラグメントは正しく動作しません。

   **解決策**：フラグメントがアクセスできるグローバル変数を使用するようにアプローチを再構築します。例について詳しくは、[ベストプラクティス - ループ内の式フラグメント](#best-practices)を参照してください。

3. **変数範囲が正しくない**：フラグメントが、ループ範囲内にのみ存在する変数を参照しようとしている可能性があります。

   **解決策**：フラグメントに必要な変数をメッセージレベル（ループの外）で定義し、グローバルにアクセスできるようにします。

説明、例、推奨されるパターンなどについて詳しくは、[ループ内の式フラグメントの使用](use-expression-fragments.md#fragments-in-loops)を参照してください。

+++

### 反復のテスト

[ジャーニーテストモード](../building-journeys/testing-the-journey.md)を使用して、反復を確認します。 これは、[カスタムアクション](#custom-action-responses)や[データセット参照](#dataset-lookup)を使用する際に特に重要です。

+++ テスト手順を表示

1. ジャーニーを[テストモード](../building-journeys/testing-the-journey.md)で開始します
2. サンプルデータを使用してイベントまたはカスタムアクションをトリガーします
3. [メッセージプレビュー](../content-management/preview.md)を確認し、反復が正しく表示されることを確認します
4. テストモードのログでエラーがないか確認します（[カスタムアクションテストモードログ](../action/action-response.md#test-mode-logs)を参照）

+++

## 関連トピック {#related-topics}

**パーソナライゼーションの基本：**[パーソナライゼーションの基本を学ぶ](personalize.md) | [パーソナライゼーションの追加](personalization-build-expressions.md) | [パーソナライゼーション構文](personalization-syntax.md) | [ヘルパー関数](functions/helpers.md) | [条件付きルールの作成](create-conditions.md)

**ジャーニー設定：**[イベントについて](../event/about-events.md) | [カスタムアクションの設定](../action/about-custom-action-configuration.md) | [カスタムアクションパラメーターへのコレクションの受け渡し](../building-journeys/collections.md#passing-collection) | [カスタムアクションでの API 呼び出し応答の使用](../action/action-response.md) | [カスタムアクションのトラブルシューティング](../action/troubleshoot-custom-action.md) | [ジャーニーでの Adobe Experience Platform データの使用](../building-journeys/dataset-lookup.md) | [ジャーニーでの補助識別子の使用](../building-journeys/supplemental-identifier.md) | [ガードレールと制限](../start/guardrails.md) | [ジャーニーのテスト](../building-journeys/testing-the-journey.md)

**ジャーニー式関数：**[高度な式エディター](../building-journeys/expression/expressionadvanced.md) | [コレクション管理関数](../building-journeys/expression/collection-management-functions.md)（first、all、last） | [リスト関数](../building-journeys/functions/list-functions.md)（serializeList、filter、sort） | [配列関数](../personalization/functions/arrays-list.md)（head、tail）

**パーソナライゼーションのユースケース：**[買い物かご放棄メール](personalization-use-case-helper-functions.md) | [注文ステータス通知](personalization-use-case.md)

**メッセージデザイン：**[メールデザインの基本を学ぶ](../email/get-started-email-design.md) | [プッシュ通知の作成](../push/create-push.md) | [SMS メッセージの作成](../sms/create-sms.md) | [コンテンツのプレビューとテスト](../content-management/preview-test.md)


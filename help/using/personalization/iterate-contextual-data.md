---
solution: Journey Optimizer
product: journey optimizer
title: コンテキストデータの反復
description: Handlebars 構文を使用して、様々なコンテキストソースの配列を反復する方法について説明します
feature: Personalization
topic: Personalization
role: Developer
level: Intermediate
keywords: 式，エディター，ハンドルバー，反復，配列，コンテキスト，パーソナライゼーション
source-git-commit: a0e8ca1b45818014993c37ac41f25e30ee1d1bb5
workflow-type: tm+mt
source-wordcount: '3008'
ht-degree: 0%

---

# コンテキストデータの反復 {#personalization-contexts}

Handlebars 反復構文を使用して、イベント、カスタムアクション応答、その他のコンテキストデータなど、メッセージ内の様々なソースのデータの動的リストを表示する方法を説明します。

## 概要 {#overview}

Journey Optimizerでは、[ メッセージのパーソナライゼーション ](personalize.md) の際に、複数のソースからのコンテキストデータにアクセスできます。 ネイティブチャネル（[email](../email/get-started-email-design.md)、[push](../push/create-push.md)、[SMS](../sms/create-sms.md)）の Handlebars 構文を使用してこれらのソースの配列を反復し、製品リスト、レコメンデーション、その他の繰り返し要素などの動的コンテンツを表示できます。

**使用可能なコンテキストソース：**

* **[イベント](#event-data)**：ジャーニーイベント（ビジネスイベント、単一イベント）からのデータ
* **[カスタムアクションの応答](#custom-action-responses)**：カスタムアクションを介した外部 API 呼び出しから返されたデータ
* **[データセットルックアップ](#dataset-lookup)**:Adobe Experience Platform データセットから取得したエンリッチメントされたデータ
* **[技術プロパティ](#technical-properties)**:ジャーニーメタデータ（ジャーニー ID や追加の識別情報など）
* **[ジャーニーコンテキスト](#other-contexts)**：実行中にアクセス可能なその他のジャーニー関連データ

このガイドでは、メッセージ内のこれらの各ソースからの配列を繰り返し処理する方法と、ジャーニーアクティビティを設定する際に配列を操作する方法について説明します。 メッセージのパーソナライゼーションの基本を理解するには、[ ハンドルバーの反復構文 ](#syntax) から始めてください。または、[ジャーニー式で配列を操作する ](#arrays-in-journeys) に移動して、配列データをカスタムアクションやデータセット検索に渡す方法を学習してください。

## ハンドルバーのイテレーション構文 {#syntax}

Handlebars は、配列に対して繰り返し処理するための `{{#each}}` [ ヘルパー ](functions/helpers.md) を提供します。 基本的な構文を次に示します。

```handlebars
{{#each arrayPath as |item|}}
  <!-- Access item properties here -->
  {{item.property}}
{{/each}}
```

**ポイント：**

* `arrayPath` を配列データへのパスに置き換えます
* 任意の変数名で `item` を置き換えます（例：`product`、`response`、`element`）
* `{{item.propertyName}}` を使用して各項目のプロパティにアクセスする
* 複数レベルの配列に対して複数の `{{#each}}` ブロックをネストできます

## イベントデータの反復 {#event-data}

イベントデータは、ジャーニーが [ イベント ](../event/about-events.md) によってトリガーされた場合に使用できます。 これは、ジャーニーの開始時に取り込まれたデータ（買い物かごの内容、注文項目、フォーム送信など）を表示する場合に便利です。

>[!TIP]
>
>イベントデータを他のソースと組み合わせることができます。 例については、[ 複数のコンテキストソースの組み合わせ ](#combine-sources) を参照してください。

### イベントのコンテキストパス

```handlebars
context.journey.events.<event_ID>.<fieldPath>
```

* `<event_ID>`：ジャーニーで設定したイベントの一意の ID
* `<fieldPath>`：イベントスキーマ内のフィールドまたは配列へのパス

### 例：イベントからの買い物かご項目

[ イベントスキーマ ](../event/experience-event-schema.md) に `productListItems` 配列（標準 [XDM 形式 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/product-list-item.html?lang=ja){target="_blank"}）が含まれている場合は、以下のサンプルで説明されているように、買い物かごの中身を表示できます。

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

### 例：イベント内でネストされた配列

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

ネストについて詳しくは、[ ベストプラクティス ](#best-practices) を参照してください。

## カスタムアクション応答の反復 {#custom-action-responses}

[ カスタムアクション ](../action/about-custom-action-configuration.md) 応答には、外部 API 呼び出しから返されたデータが含まれます。 これは、ロイヤルティポイント、製品レコメンデーション、在庫ステータス、パーソナライズされたオファーなど、システムからリアルタイムの情報を表示する場合に役立ちます。

>[!NOTE]
>
>この機能を使用するには、カスタムアクションを応答ペイロードで設定する必要があります。 詳しくは、[ この節 ](../action/action-response.md#config-response) を参照してください。 カスタムアクション応答をイベントデータやデータセット検索と組み合わせることもできます。例として、[ 複数のコンテキストソースの組み合わせ ](#combine-sources) を参照してください。

### カスタムアクションのコンテキストパス

```handlebars
context.journey.actions.<actionName>.<fieldPath>
```

* `<actionName>`：ジャーニーで設定した [ カスタムアクション ](../action/about-custom-action-configuration.md) の名前
* `<fieldPath>`：応答ペイロード内のフィールドまたは配列へのパス

### 例：API からの製品レコメンデーション

カスタムアクションから返された製品レコメンデーションの配列を繰り返し処理し、メッセージに個々のカードとして表示するには、以下の例を参照してください。

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

ネストされた配列（各オブジェクトに別の配列が含まれるオブジェクトの配列）を含んだカスタムアクション応答を繰り返し処理するには、以下の例を参照してください。 これは、ネストされた `{{#each}}` ループを使用して、複数レベルのデータにアクセスする方法を示しています。

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

より複雑なネストパターンについては、[ ベストプラクティス ](#best-practices) を参照してください。

### 例：ロイヤルティ層のメリット

ロイヤルティステータスに基づいて動的な特典を表示するには、次の例を参照してください。

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

## データセット検索結果の繰り返し {#dataset-lookup}

[ データセットルックアップアクティビティ ](../building-journeys/dataset-lookup.md) を使用すると、ジャーニーの実行時に [Adobe Experience Platform データセット ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja){target="_blank"} からデータを取得できます。 エンリッチメントされたデータは配列として保存され、メッセージ内で繰り返し処理できます。

>[!AVAILABILITY]
>
>データセットルックアップアクティビティは、限られた組織セットでのみ使用できます。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

データセットルックアップアクティビティの設定について詳しくは、[ この節 ](../building-journeys/dataset-lookup.md) を参照してください。 データセットルックアップは、イベントデータと組み合わせると特に強力です。実用的なユースケースについては、[ 例：データセットルックアップを使用して強化されたイベントデータ ](#combine-sources) を参照してください。

### データセット検索のコンテキストパス

```handlebars
context.journey.datasetLookup.<activityID>.entities
```

* `<activityID>`：データセットルックアップアクティビティの一意の ID
* `entities`：データセットから取得したエンリッチメントされたデータの配列

### 例：データセットからの製品詳細

データセットルックアップアクティビティを使用して、SKU に基づいて製品情報を取得する場合は、以下のサンプルを参照してください。

+++ サンプルコードを表示

**データセットルックアップ設定：**

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

### 例：データセットデータを使用してイテレーションをフィルタリングする

イテレーション中にデータセットのルックアップ結果をフィルタリングして、特定の条件に一致する項目（特定のカテゴリの製品など）のみを表示するには、`{{#if}}` ループ内で条件付き `{{#each}}` ステートメントを使用します。 以下の例を参照してください。

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

条件付きフィルタリングについて詳しくは、[ ベストプラクティス ](#best-practices) を参照してください。

### 例：データセットルックアップからの合計の計算

データセットのルックアップ結果を繰り返し処理しながら合計を計算して表示するには、以下の例を参照してください。

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

## ジャーニーのテクニカルプロパティの使用 {#technical-properties}

ジャーニーのテクニカルプロパティでは、ジャーニー ID や追加の識別子など、ジャーニーの実行に関するメタデータへのアクセスを提供します。 これらは、イテレーションパターンと組み合わせる場合に役立ちます。特に、特定のジャーニーインスタンスに基づいて配列をフィルタリングする場合に便利です。

### 利用可能な技術プロパティ

```handlebars
context.journey.technicalProperties.journeyUID
context.journey.technicalProperties.supplementalId
```

### 例：追加の識別子を使用した配列項目のフィルタリング

配列を使用したイベントトリガージャーニーで補足的な識別子を使用する場合は、フィルタリングして、現在のジャーニーインスタンスに関連する項目のみを表示できます。 追加の識別子について詳しくは、[ このガイド ](../building-journeys/supplemental-identifier.md) を参照してください。

**シナリオ**:1 つのジャーニーが複数の予約でトリガーされますが、このジャーニーインスタンスをトリガーした特定の予約（追加の ID によって識別）の情報のみを表示したい場合。

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

### 例：トラッキングにジャーニー ID を含める

トラッキング目的でメッセージにジャーニー ID を含めるには、以下の例を参照してください。

+++ サンプルコードを表示

```handlebars
<footer>
  <p>Journey Reference: {{context.journey.technicalProperties.journeyUID}}</p>
</footer>
```

+++

## 複数のコンテキストソースの組み合わせ {#combine-sources}

異なるソースのデータを同じメッセージ内で組み合わせて、パーソナライズされた豊富なエクスペリエンスを作成できます。 この節では、複数のコンテキストソースを組み合わせて使用する実践的な例を示します。

**組み合わせることができるコンテキストソース：**

* [ イベントデータ ](#event-data) + [ カスタムアクション応答 ](#custom-action-responses)
* [ イベントデータ ](#event-data) + [ データセットルックアップ ](#dataset-lookup)
* [ 複数のソース ](#combine-sources) + [ 技術的プロパティ ](#technical-properties)

### 例：リアルタイムの在庫を含む買い物かご項目

イベントデータ（買い物かごのコンテンツ）をカスタムアクションデータ（在庫ステータス）と組み合わせるには、以下のサンプルを表示します。

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

### 例：データセット参照を使用してエンリッチメントされたイベントデータ

[ イベント SKU](#event-data) を [ データセットルックアップ ](#dataset-lookup) の詳細な製品情報と組み合わせるには、以下のサンプルを表示します。

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

### 例：複数のソースを技術的なプロパティと組み合わせる

複数のコンテキストソース（プロファイルデータ、イベントデータ、カスタムアクション、技術プロパティ）を 1 つのメッセージに組み合わせるには、以下のサンプルを表示します。

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

このガイドでは配列の反復に重点を置いていますが、通常は反復を必要としないパーソナライゼーションには、他のコンテキストタイプも使用できます。 これらは、ループ処理ではなく直接アクセスされます。

* **[プロファイル属性 ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}** （`profile.*`）:Adobe Experience Platformの個々のプロファイルフィールド
* **[Audiences](../audience/about-audiences.md)** （`inAudience()`）：オーディエンスメンバーシップの確認
* **[オファーの決定](../offers/get-started/starting-offer-decisioning.md)**：意思決定管理オファー
* **[ターゲット属性](../orchestrated/activities/channels.md#add-personalization)** （オーケストレートキャンペーンのみ）：キャンペーンキャンバスで計算される属性
* **トークン** （`context.token`）：セッションまたは認証トークン

これらのソースを使用した完全なパーソナライゼーション構文と例については、以下を参照してください。

* [パーソナライゼーションの追加](personalization-build-expressions.md)
* [パーソナライゼーション構文](personalization-syntax.md)

## ジャーニー式での配列の操作 {#arrays-in-journeys}

前の節では、Handlebars を使用したメッセージパーソナライゼーションにおける配列の反復に焦点を当てましたが、ジャーニーアクティビティを設定する際にも配列を操作します。 この節では、イベントの配列データをジャーニー式で使用する方法、特に、カスタムアクションにデータを渡す場合や、データセット検索で配列を使用する場合について説明します。

>[!IMPORTANT]
>
>ジャーニー式は、Handlebars パーソナライゼーションとは異なる構文を使用します。 ジャーニー設定（カスタムアクションパラメーターや条件など）では、[ジャーニー式エディターを ](../building-journeys/expression/expressionadvanced.md)`first`、`all`、`serializeList` などの関数と共に使用します。 メッセージコンテンツでは、`{{#each}}` ループで Handlebars 構文を使用します。

### カスタムアクションパラメーターに配列値を渡す {#arrays-to-custom-actions}

[ カスタムアクション ](../action/about-custom-action-configuration.md) を設定する場合、多くの場合、イベント配列から値を抽出し、パラメーターとして渡す必要があります。 ここでは、一般的なパターンについて説明します。

[ コレクションをカスタムアクションパラメーターに渡す ](../building-journeys/collections.md#passing-collection) でコレクションを渡す方法の詳細を説明します。

#### 配列から 1 つの値を抽出します

**ユースケース**：イベント配列から特定のフィールドを取得し、GET リクエストのクエリパラメーターとして渡します。

+++ サンプルコードを表示

**サンプルシナリオ**：価格が 0 を超える最初の SKU を製品リストから抽出します。

**イベントスキーマの例**:

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

**カスタムアクション設定**:

1. カスタムアクションで、タイプ `sku` のクエリパラメーター（例：`string`）を設定します
2. 動的な値を許可する場合は「`Variable`」とマークします

**アクション パラメーターのジャーニー式**:

```javascript
@event{YourEventName.commerce.productListItems.first(currentEventField.priceTotal > 0).SKU}
```

**説明**:

* `@event{YourEventName}`：ジャーニーイベントを参照します
* `.first(currentEventField.condition)`：条件に一致する最初の配列項目を返します
* `currentEventField`：イベント配列内の各項目をループ処理するときに表します
* `.SKU`：一致した項目から SKU フィールドを抽出します
* 結果：`"SKU-1"` （アクションパラメーターに適した文字列）

`first` 関数について詳しくは、[ コレクション管理関数 ](../building-journeys/expression/collection-management-functions.md) を参照してください。

+++

#### 配列から値のリストを作成

**ユースケース**：クエリパラメーターとして渡す ID のコンマ区切りリストを作成します（例：`/products?ids=sku1,sku2,sku3`）。

+++ サンプルコードを表示

**カスタムアクション設定**:

1. タイプ `ids` のクエリパラメーター（例：`string`）を設定
2. `Variable` としてマーク

**ジャーニー式**:

```javascript
serializeList(
  @event{YourEventName.commerce.productListItems.all(currentEventField.priceTotal > 0).SKU},
  ",",
  true
)
```

**説明**:

* `.all(currentEventField.condition)`：条件に一致するすべての配列項目を返します（リストを返します）
* `currentEventField`：イベント配列内の各項目をループ処理するときに表します
* `.SKU`: SKU 値のみを含めるようにリストをプロジェクト化します
* `serializeList(list, delimiter, addQuotes)`：リストを文字列に結合します
   * `","`：区切り文字としてコンマを使用します
   * `true`：各文字列要素を引用符で囲みます
* 結果：`"SKU-1,SKU-3"` （クエリパラメーターに適しています）

詳しくは、以下を参照してください。

* [&#39;すべて&#39;](../building-journeys/expression/collection-management-functions.md)
* [&#39;serializeList&#39;](../building-journeys/functions/list-functions.md#serializeList)

カスタムアクションのコレクション処理については、[ カスタムアクションパラメーターへのコレクションの受け渡し ](../building-journeys/collections.md#passing-collection) を参照してください。

+++

#### オブジェクトの配列をカスタムアクションに渡す

**ユースケース**：リクエスト本文内のオブジェクトの完全な配列を送信します（本文を持つ POST またはGETの場合）。

+++ サンプルコードを表示

**リクエスト本文の例**:

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

**カスタムアクション設定**:

1. リクエスト本文で、`products` をタイプ `listObject` として定義します。
2. `Variable` としてマーク
3. オブジェクトフィールド `id`、`name`、`price`、`color` を定義します（それぞれがマッピング可能になります）。

**ジャーニー キャンバスの構成**:

1. 詳細設定モードで、コレクション式を設定します。

   ```javascript
   @event{YourEventName.commerce.productListItems.all(currentEventField.priceTotal > 0)}
   ```

1. コレクションマッピング UI で、次の操作を行います。
   * `id` の地図→ `productListItems.SKU`
   * `name` の地図→ `productListItems.name`
   * `price` の地図→ `productListItems.priceTotal`
   * `color` の地図→ `productListItems.color`

Journey Optimizerは、アクションペイロード構造に一致するオブジェクトの配列を作成します。

>[!NOTE]
>
>イベント配列を操作する場合は、`currentEventField` を使用して各項目を参照します。 データソースコレクション（Adobe Experience Platform）には、`currentDataPackField` を使用します。 カスタムアクションの応答コレクションには、`currentActionField` を使用します。

詳しくは、[ コレクションをカスタムアクションパラメーターに渡す ](../building-journeys/collections.md#passing-collection) を参照してください。

+++

### データセット検索での配列の使用 {#arrays-with-dataset-lookup}

[ データセットルックアップアクティビティ ](../building-journeys/dataset-lookup.md) を使用する場合、値の配列をルックアップキーとして渡して、エンリッチメントされたデータを取得できます。

**例**：イベント配列内のすべての SKU の製品の詳細を検索します。

+++ サンプルコードを表示

**データセットルックアップ設定**:

ルックアップキーフィールドで、`list()` を使用して配列パスをリストに変換します。

```javascript
list(@event{purchaseEvent.productListItems.SKU})
```

これにより、データセットで検索するすべての SKU 値のリストが作成されます。 結果は、メッセージで繰り返し処理できる `context.journey.datasetLookup.<activityID>.entities` の配列として利用できます（[ データセットルックアップ結果の繰り返し ](#dataset-lookup) を参照）。

+++

### 制限事項とパターン {#array-limitations}

ジャーニーで配列を使用する場合は、次の制限事項に注意してください。

#### ジャーニーフローで配列に動的なループはない

ジャーニーは、配列の各項目に対して 1 つのアクションノードが複数回実行される動的ループを作成できません。 これは、暴走パフォーマンスの問題を防ぐことを目的としています。

**できないこと**:

* カスタムアクションを配列項目ごとに 1 回動的に実行
* 配列の長さに基づいて複数のジャーニー分岐を作成します

**推奨されるパターン**:

1. **すべての項目を一度に送信**：配列全体またはシリアル化されたリストを、すべての項目を処理する単一のカスタムアクションに渡します。 [ 配列から値のリストを作成する ](#arrays-to-custom-actions) を参照してください。

2. **外部集計の使用**：外部 API で複数の ID を受け入れ、1 回の呼び出しで組み合わせた結果を返すようにします。

3. **AEPで事前計算**: [ 計算済み属性 ](../audience/computed-attributes.md) を使用して、プロファイルレベルで配列から値を事前計算します。

4. **単一値の抽出**:1 つの値のみが必要な場合は、`first` または `head` を使用して抽出します。 [ 配列から 1 つの値を抽出 ](#arrays-to-custom-actions) を参照してください。

詳しくは、[ ガードレールと制限事項 ](../start/guardrails.md) を参照してください。

#### 配列サイズに関する考慮事項

大規模な配列は、ジャーニーのパフォーマンスに影響を与える可能性があります。

* **イベント配列**：イベントペイロードの合計が 50 KB 未満に抑える
* **カスタムアクション応答**：応答ペイロードは 100 KB 未満にする必要があります
* **データセットルックアップ結果**：ルックアップキーと返されるエンティティの数を制限する

### 完全な例：カスタムアクションに対するイベント配列 {#complete-example}

カスタムアクションでイベント配列を使用する方法を示す完全なワークフローを次に示します。

**シナリオ**：ユーザーが買い物かごを放棄すると、外部のレコメンデーション API に買い物かごデータを送信してパーソナライズされた提案を取得し、メールに表示します。

+++ サンプルコードを表示

**手順 1：カスタムアクションの設定**

カスタムアクション「GetCartRecommendations」を作成します。

* **メソッド**: POST
* **URL**: `https://api.example.com/recommendations`
* **リクエスト本文**:

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

* `cartItems` をタイプ `listObject` および `Variable` としてマーク
* フィールドを定義：`sku` （文字列）、`price` （数値）、`quantity` （整数）

詳しくは、[ カスタムアクションの設定 ](../action/about-custom-action-configuration.md) を参照してください。

**手順 2：応答ペイロードの設定**

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

詳しくは、[API 呼び出し応答の使用 ](../action/action-response.md) を参照してください。

**手順 3：ジャーニー内のアクションを関連付ける**

1. 買い物かご放棄イベントの後に、カスタムアクションを追加します
1. `cartItems` コレクションの詳細設定モード：

   ```javascript
   @event{cartAbandonment.commerce.productListItems.all(currentEventField.quantity > 0)}
   ```

1. コレクションフィールドをマッピングします
   * `sku` → `productListItems.SKU`
   * `price` → `productListItems.priceTotal`
   * `quantity` → `productListItems.quantity`

**手順 4：メールでの応答の使用**

メールコンテンツで、レコメンデーションを繰り返し処理します。

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

**手順 5：設定をテストする**

ライブジャーニーを実行する前に、アクション設定の「テストリクエストを送信」機能を使用してカスタムアクションをテストし、作成されたリクエストと値を確認します。

1. [ ジャーニーテストモード ](../building-journeys/testing-the-journey.md) を使用
2. `productListItems` 配列を含むサンプルイベントデータを持つトリガー
3. カスタムアクションが正しい配列構造を受け取ることを確認します。
4. [ アクションテストログ ](../action/action-response.md#test-mode-logs) を確認します
5. メールをプレビューして、両方の配列が正しく表示されていることを確認します

詳しくは、[ カスタムアクションのトラブルシューティング ](../action/troubleshoot-custom-action.md) を参照してください。

+++

## ベストプラクティス {#best-practices}

コンテキストデータを繰り返し処理して、保守可能でパフォーマンスの高いパーソナライゼーションを作成する場合は、次のベストプラクティスに従ってください。

### わかりやすい変数名を使用

反復している内容を明確に示す変数名を選択します。 これにより、コードがより読みやすく、メンテナンスが容易になります。 詳しくは、[ パーソナライゼーション構文 ](personalization-syntax.md) を参照してください。

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

[ ループ内で ](use-expression-fragments.md) 式フラグメント `{{#each}}` を使用する場合、ループスコープ変数をフラグメントパラメーターとして渡すことはできません。 ただし、フラグメントは、フラグメント外のメッセージコンテンツで定義されたグローバル変数にアクセスできます。

+++ サンプルコードを表示

**サポートされているパターン – グローバル変数を使用：**

```handlebars
{% let globalDiscount = 15 %}

{{#each context.journey.actions.GetProducts.items as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    {{fragment id='ajo:fragment123/variant456' mode='inline'}}
  </div>
{{/each}}
```

フラグメントは、メッセージ内でグローバルに定義されているので、`globalDiscount` を参照できます。

**サポートされていません – ループ変数を渡しています：**

```handlebars
{{#each products as |product|}}
  <!-- This will NOT work as expected -->
  {{fragment id='ajo:fragment123/variant456' currentProduct=product}}
{{/each}}
```

**回避策**：フラグメントを使用する代わりに、パーソナライゼーションロジックをループに直接含めるか、ループの外でフラグメントを呼び出します。

+++

詳細な例やその他の回避策など、[ ループ内での式フラグメントの使用 ](use-expression-fragments.md#fragments-in-loops) について説明します。



### 空の配列を処理

配列が空の場合にフォールバックコンテンツを提供するには、`{{else}}` 句を使用します。 [ ヘルパー関数 ](functions/helpers.md) の詳細：

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

条件付きコンテンツの場合は、`{{#if}}` within ループを使用します。 [ 条件付きルール ](create-conditions.md) について詳しくは、[ カスタムアクション応答 ](#custom-action-responses) および [ データセットルックアップ ](#dataset-lookup) の節の例を参照してください。

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

### パフォーマンスのイテレーションを制限

大きな配列の場合は、繰り返し回数を制限することを検討してください。

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

Handlebars には、高度な繰り返しパターンに役立つ特別な変数がループ内に用意されています。

* `@index`：現在のイテレーションインデックス（0 から始まります）
* `@first`：最初のイテレーションでは True
* `@last`：最後のイテレーションでは True

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
>これらの Handlebars 変数（`@index`、`@first`、`@last`）は、メッセージのパーソナライゼーションの `{{#each}}` ループ内でのみ使用できます。 ジャーニー式で配列を操作する場合（カスタムアクションに渡す前に配列から最初の項目を取得する場合など）は、[`head`](../personalization/functions/arrays-list.md#head)、[`first`](../building-journeys/expression/collection-management-functions.md)、[`all`](../building-journeys/expression/collection-management-functions.md) などの配列関数を使用します。 詳しくは、[ジャーニー式での配列の操作 ](#arrays-in-journeys) を参照してください。

## トラブルシューティング {#troubleshooting}

反復に問題がありますか？ この節では、一般的な問題と解決策について説明します。

### アレイが表示されない

**問題**：配列の反復にコンテンツが表示されていません。

+++ 考えられる原因と解決策の表示

**考えられる原因と解決策**:

1. **パスが正しくありません**：コンテキストソースに基づいて、配列への正確なパスを確認してください。
   * [ イベント ](#event-data) の場合：`context.journey.events.<event_ID>.<fieldPath>`
   * [ カスタムアクション ](#custom-action-responses) の場合：`context.journey.actions.<actionName>.<fieldPath>`
   * [ データセット検索 ](#dataset-lookup) の場合：`context.journey.datasetLookup.<activityID>.entities`

2. **配列が空です**:`{{else}}` 句を追加して、配列にデータがないかどうかを確認します。 例については、[ ベストプラクティス ](#best-practices) を参照してください。

3. **まだデータを使用できません**：ジャーニーフローのメッセージアクティビティの前に、カスタムアクション、イベントまたはデータセットのルックアップアクティビティが実行されていることを確認します。

+++

### 構文エラー

**問題**：式の検証が失敗するか、メッセージがレンダリングされません。

+++ 一般的なエラーの表示

**よくある間違い**:

* 終了タグがありません：すべての `{{#each}}` には `{{/each}}` が必要です。 適切な構造を得るには、[Handlebars 反復構文 ](#syntax) を確認してください。
* 変数名が正しくありません：ブロック全体で変数名を一貫して使用してください。 命名規則については、[ ベストプラクティス ](#best-practices) を参照してください。
* パスの区切り文字が正しくありません。スラッシュなどの文字を使用せずにドット（`.`）を使用してください

+++

### ループで式フラグメントが機能しない

**問題**：式フラグメントが `{{#each}}` ループ内で使用された場合に期待されるコンテンツを表示しないか、空の出力または予期しない出力を表示します。

+++ 考えられる原因と解決策の表示

**考えられる原因と解決策**:

1. **ループ変数をパラメーターとして渡そうとして**：式フラグメントは、ループスコープ変数（現在の反復項目など）をパラメーターとして受け取ることができません。 これは既知の制限です。

   **解決策**：次のいずれかの回避策を使用します。

   * フラグメントがアクセスできるメッセージ内のグローバル変数を定義する
   * フラグメントを使用する代わりに、パーソナライゼーションロジックをループに直接含めます
   * ループ固有のデータが不要な場合は、ループの外部でフラグメントを呼び出します

2. **フラグメントは、使用できないパラメーターを想定しています**：フラグメントが特定の入力パラメーターを受け取るように設計されている場合、これらのパラメーターをループ内から渡すことができない限り、正しく機能しません。

   **解決策**：フラグメントがアクセスできるグローバル変数を使用するように、アプローチを再構築します。 例については、[ ベストプラクティス – ループ内の式フラグメント ](#best-practices) を参照してください。

3. **変数スコープが正しくありません**：フラグメントが、ループスコープ内にのみ存在する変数を参照しようとしている可能性があります。

   **解決策**：フラグメントに必要な変数をメッセージレベル（ループの外側）で定義して、グローバルにアクセスできるようにします。

詳細な説明、例、推奨されるパターンなど、[ ループ内での式フラグメントの使用 ](use-expression-fragments.md#fragments-in-loops) について説明します。

+++

### イテレーションのテスト

[ ジャーニーテストモード ](../building-journeys/testing-the-journey.md) を使用して、イテレーションを検証します。 これは、[ カスタムアクション ](#custom-action-responses) または [ データセット検索 ](#dataset-lookup) を使用する場合に特に重要です。

+++ テスト手順の表示

1. ジャーニーを [ テストモード ](../building-journeys/testing-the-journey.md) で開始します
2. イベントまたはカスタムアクションとサンプルデータのトリガー
3. [ メッセージプレビュー ](../content-management/preview.md) をチェックして、イテレーションが正しく表示されていることを確認します
4. エラーのテストモードログを確認します（[ カスタムアクションテストモードログ ](../action/action-response.md#test-mode-logs) を参照）

+++

## 関連トピック {#related-topics}

**Personalizationの基本事項：**[ パーソナライゼーションの概要 ](personalize.md) | [ パーソナライゼーションを追加 ](personalization-build-expressions.md) | [Personalization構文 ](personalization-syntax.md) | [ ヘルパー関数 ](functions/helpers.md) | [ 条件付きルールの作成 ](create-conditions.md)

**ジャーニー構成：** [ イベントについて ](../event/about-events.md) | [ カスタムアクションの設定 ](../action/about-custom-action-configuration.md) | [ コレクションをカスタムアクションパラメーターに渡す ](../building-journeys/collections.md#passing-collection) | [ カスタムアクションでの API 呼び出し応答の使用 ](../action/action-response.md) | [ カスタムアクションのトラブルシューティング ](../action/troubleshoot-custom-action.md) | [ ジャーニーでのAdobe Experience Platform データの使用 ](../building-journeys/dataset-lookup.md) | [ ジャーニーで追加の識別子を使用 ](../building-journeys/supplemental-identifier.md) | [ ガードレールと制限 ](../start/guardrails.md) | [ ジャーニーのテスト ](../building-journeys/testing-the-journey.md)

**ジャーニー式関数：** [ 高度な式エディター ](../building-journeys/expression/expressionadvanced.md) | [ コレクション管理関数 ](../building-journeys/expression/collection-management-functions.md) （first、all、last） | [ リスト関数 ](../building-journeys/functions/list-functions.md) （serializeList、filter、sort） | [ 配列関数 ](../personalization/functions/arrays-list.md) （head、tail）

**Personalizationのユースケース：** [ 買い物かごの放棄に関するメール ](personalization-use-case-helper-functions.md) | [ 注文ステータスの通知 ](personalization-use-case.md)

**メッセージデザイン：**[ メールデザインの概要 ](../email/get-started-email-design.md) | [ プッシュ通知の作成 ](../push/create-push.md) | [SMS メッセージの作成 ](../sms/create-sms.md) | [ コンテンツのプレビューとテスト ](../content-management/preview-test.md)


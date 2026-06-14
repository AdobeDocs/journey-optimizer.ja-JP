---
solution: Journey Optimizer
product: journey optimizer
title: Personalizationのユースケース&コロン；買い物かご放棄メール
description: ユースケースを通じて、メールメッセージの本文をパーソナライズする方法を説明します。
feature: Personalization, Use Cases
topic: Personalization
role: Developer
level: Intermediate
keywords: 式，エディター，ヘルパー，ユースケース，パーソナライゼーション
exl-id: 9c9598c0-6fb1-4e2f-b610-ccd1a80e516e
TQID: https://experienceleague.adobe.com/93bIkfyck5u-tQNGr7jGRORQiTa3gaMHn4H5RP-dpYo
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: fda7be7c-b81e-42c0-95a9-616e5b893c03
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
subfeature_v2:
  - id: cb09dcb7-3367-4b63-b02c-8a1356eb876e
source-git-commit: 378c98d4dc9552de3eed68eda59d9917c2b56347
workflow-type: tm+mt
source-wordcount: 1289
ht-degree: 81%

---

# パーソナライゼーションのユースケース：買い物かごの放棄メール {#personalization-use-case-helper-functions}

>[!BEGINSHADEBOX]

**このページ：** Adobe Journey OptimizerでupperCase、各、if ヘルパー関数を使用してメール本文をパーソナライズする、カート放棄の使用例に従います。

>[!ENDSHADEBOX]

この例では、メールメッセージの本文をパーソナライズします。 このメッセージは、買い物かごに商品が残っているが購入を完了していない顧客をターゲットにします。

次のタイプのヘルパー関数を使用します。

* `upperCase` 文字列関数：顧客の名を大文字で挿入します。 [学習を増やす](functions/string.md#upper)。
* `each` ヘルパー：買い物かごに入っている商品をリストします。 [学習を増やす](functions/helpers.md#each)。
* `if`ヘルパー：関連製品が買い物かごに入っている場合に製品固有のメモを挿入します。 [学習を増やす](functions/helpers.md#if-function)。
<!-- **Context**: personalization based on contextual data from the journey -->

➡️ [ヘルパー関数の使用方法について詳しくは、このビデオを参照してください。](#video)

開始する前に、次の要素の設定方法を理解しておく必要があります。

* 単一のイベント。 [学習を増やす](../event/about-events.md)。
* イベントで開始されるジャーニー。 [学習を増やす](../building-journeys/using-the-journey-designer.md)。
* ジャーニーでのメールメッセージ。 [詳細情報](../email/create-email.md)
* メールの本文。 [学習を増やす](../email/content-from-scratch.md)。

次の手順に従います。

1. [最初のイベントとジャーニーを作成します](#create-context)。
1. [メールメッセージを作成します](#configure-email)。
1. [顧客の名を大文字で挿入します](#uppercase-function)。
1. [買い物かごの内容をメールに追加します](#each-helper)。
1. [製品固有のメモを挿入します](#if-helper)。
1. [ジャーニーをテストし公開します](#test-and-publish)。

## 手順 1：最初のイベントと関連ジャーニーの作成 {#create-context}

買い物かごの内容は、ジャーニーからのコンテキスト情報です。 したがって、買い物かご固有の情報をメールに追加する前に、最初のイベントとメールをジャーニーに追加する必要があります。

1. スキーマに `productListItems` 配列が含まれるイベントを作成します。
1. この配列のすべてのフィールドを、このイベントのペイロードフィールドとして定義します。

   製品リスト項目データタイプについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/product-list-item.html?lang=ja){target="_blank"}を参照してください。

1. このイベントで開始されるジャーニーを作成します。
1. ジャーニーに&#x200B;**メール**&#x200B;アクティビティを追加します。

   ![&#x200B; フロー内のイベントとメールアクティビティを含むジャーニーキャンバス &#x200B;](assets/personalization-uc-helpers-8.png)

## 手順 2： メールの作成 {#configure-email}

1. **メール**&#x200B;アクティビティで、「**[!UICONTROL コンテンツを編集]**」をクリックしたあと、「**[!UICONTROL E メールデザイナー]**」をクリックします。

   ![&#x200B; コンテンツの編集およびDesignerの電子メール オプションを使用した電子メールアクティビティ &#x200B;](assets/personalization-uc-helpers-1.png)

1. E メールデザイナーホームページの左側のパレットから、3 つの構造コンポーネントをメッセージの本文にドラッグ＆ドロップします。

1. HTML コンテンツコンポーネントを、それぞれの新規構造コンポーネントにドラッグ＆ドロップします。

   ![3つの構造コンポーネントとHTML コンテンツコンポーネントを本文に含むメール Designer](assets/personalization-uc-helpers-2.png)

## 手順 3： 顧客の名（大文字）の挿入 {#uppercase-function}

1. E メールデザイナーのホームページで、顧客の名を追加する HTML コンポーネントをクリックします。
1. コンテキストツールバーで、「**[!UICONTROL ソースコードを表示]**」をクリックします。

   ![&#x200B; ソースコードを表示オプション付きのコンテキストツールバー](assets/personalization-uc-helpers-3.png)

1. **[!UICONTROL HTML を編集]**&#x200B;ウィンドウで、`upperCase` 文字列関数を追加します。
   1. 左側のメニューで、「**[!UICONTROL ヘルパー関数]**」を選択します。
   1. 検索フィールドを使用して、「uppercase」を検索します。
   1. 検索結果から、`upperCase` 関数を追加します。 それには、`{%= upperCase(string) %}: string` の横のプラス記号（+）をクリックします。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%= upperCase(string) %}
      ```

      ![&#x200B; ヘルパー関数でupperCase関数が選択された式エディター](assets/personalization-uc-helpers-4.png)

1. 式から「string」プレースホルダーを削除します。
1. 名トークンを追加します。
   1. 左側のメニューで、「**[!UICONTROL プロファイル属性]**」を選択します。
   1. **[!UICONTROL ユーザー]**／**[!UICONTROL 姓名]**&#x200B;を選択します。
   1. 式に&#x200B;**[!UICONTROL 名]**&#x200B;トークンを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%= upperCase(profile.person.name.firstName) %}
      ```

      ![&#x200B; プロファイル名トークンを含むupperCaseを表示する式エディター](assets/personalization-uc-helpers-5.png)

      ユーザー名データタイプについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/person-name.html?lang=ja){target="_blank"}を参照してください。

1. 「 **[!UICONTROL 検証]**」をクリックしてから、「**[!UICONTROL 保存]**」をクリックします。

   ![検証ボタンと保存ボタンを使用してHTML ウィンドウを編集](assets/personalization-uc-helpers-6.png)

1. メッセージを保存します。

## 手順 4：買い物かご内の商品リストの挿入 {#each-helper}

このステップでは、イベントデータを反復処理します。 異なるデータソース（イベント、カスタムアクション応答、その他のコンテキストデータ）に対する反復の包括的な例については、[Handlebars](iterate-contextual-data.md)を使用したコンテキストデータの反復を参照してください。

1. メッセージコンテンツを再度開きます。

1. E メールデザイナーのホームページで、買い物かごの内容を一覧表示する HTML コンポーネントをクリックします。
1. コンテキストツールバーで、「**[!UICONTROL ソースコードを表示]**」をクリックします。

   ![&#x200B; ソースコードを表示オプション付きのコンテキストツールバー](assets/personalization-uc-helpers-3.png)

1. **[!UICONTROL HTML を編集]**&#x200B;ウィンドウで、`each` ヘルパーを追加します。
   1. 左側のメニューで、「**[!UICONTROL ヘルパー関数]**」を選択します。
   1. 検索フィールドを使用して、「each」を検索します。
   1. 検索結果から、`each` ヘルパーを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {{#each someArray as |variable|}} {{/each}}
      ```

      ![各ヘルパーテンプレートを含む式エディター](assets/personalization-uc-helpers-9.png)

1. 式に `productListItems` 配列を追加します。

   1. 式から「someArray」プレースホルダーを削除します。
   1. 左側のメニューで、「**[!UICONTROL コンテキスト属性]**」を選択します。

      **[!UICONTROL コンテキスト属性]**&#x200B;は、ジャーニーコンテキストがメッセージに渡された後でのみ使用できます。

   1. **[!UICONTROL Journey Optimizer]**／**[!UICONTROL イベント]**／***[!UICONTROL event_name]*** を選択し、**[!UICONTROL productListItems]** ノードを展開します。

      この例では、*event_name* はイベントの名前を表します。

   1. 式に&#x200B;**[!UICONTROL 製品]**&#x200B;トークンを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {{#each context.journey.events.event_ID.productListItems.product as |variable|}} {{/each}}
      ```

      この例では、*event_ID* はイベントの ID を表します。

      ![&#x200B; コンテクスト属性にproductListItemsが含まれる式エディター](assets/personalization-uc-helpers-10.png)

   1. 式を次のように変更します。
      1. 「.product」文字列を削除します。
      1. 「variable」プレースホルダーを「product」に置き換えます。

      次の例は、変更された式を示しています。

      ```handlebars
      {{#each context.journey.events.event_ID.productListItems as |product|}}
      ```

1. 次のコードを、`{{#each}}` 開始タグと `{{/each}}` 終了タグの間に貼り付けます。

   ```html
   <table>
      <tbody>
         <tr>
            <td><b>#name</b></td>
            <td><b>#quantity</b></td>
            <td><b>$#priceTotal</b></td>
         </tr>
      </tbody>
   </table>
   ```

1. 商品名、数量および価格のパーソナライゼーショントークンを追加します。

   1. HTML テーブルからプレースホルダー「#name」を削除します。
   1. 前の検索結果から、**[!UICONTROL 名前]**&#x200B;トークンを式に追加します。

   次の手順を 2 回繰り返します。

   * プレースホルダー「#quantity」を&#x200B;**[!UICONTROL 数量]**&#x200B;トークンに置き換えます。
   * プレースホルダー「#priceTotal」を&#x200B;**[!UICONTROL 合計価格]**&#x200B;トークンに置き換えます。

   次の例は、変更された式を示しています。

   ```handlebars
   {{#each context.journey.events.event_ID.productListItems as |product|}}
      <table>
         <tbody>
            <tr>
            <td><b>{{product.name}}</b></td>
            <td><b>{{product.quantity}}</b></td>
            <td><b>${{product.priceTotal}}</b></td>
            </tr>
         </tbody>
      </table>
   {{/each}}
   ```

1. 「**[!UICONTROL 検証]**」をクリックしてから、「**[!UICONTROL 保存]**」をクリックします。

   ![各ブロックを設定した後、検証と保存を含む式エディター](assets/personalization-uc-helpers-11.png)

## 手順 5：製品固有のメモの挿入 {#if-helper}

1. E メールデザイナーのホームページで、メモを挿入する HTML コンポーネントをクリックします。
1. コンテキストツールバーで、「**[!UICONTROL ソースコードを表示]**」をクリックします。

   ![&#x200B; ソースコードを表示オプション付きのコンテキストツールバー](assets/personalization-uc-helpers-3.png)

1. **[!UICONTROL HTML を編集]**&#x200B;ウィンドウで、`if` ヘルパーを追加します。
   1. 左側のメニューで、「**[!UICONTROL ヘルパー関数]**」を選択します。
   1. 検索フィールドを使用して、「if」を検索します。
   1. 検索結果から、`if` ヘルパーを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%#if condition1%} render_1
         {%else if condition2%} render_2
         {%else%} default_render
      {%/if%}
      ```

      ![if ヘルパーテンプレートを使用した式エディター](assets/personalization-uc-helpers-12.png)

1. 式から次の条件を削除します。

   ```handlebars
   {%else if condition2%} render_2
   ```

   次の例は、変更された式を示しています。

   ```handlebars
   {%#if condition1%} render_1
      {%else%} default_render
   {%/if%}
   ```

1. 製品名トークンを条件に追加します。
   1. 式から「condition1」プレースホルダーを削除します。
   1. 左側のメニューで、「**[!UICONTROL コンテキスト属性]**」を選択します。
   1. **[!UICONTROL Journey Orchestration]**／**[!UICONTROL イベント]**／***[!UICONTROL event_name]*** を選択し、**[!UICONTROL productListItems]** ノードを展開します。

      この例では、*event_name* はイベントの名前を表します。

   1. 式に&#x200B;**[!UICONTROL 名前]**&#x200B;トークンを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name%}
         render_1
         {%else%} default_render
      {%/if%}
      ```

      if条件にproductListItems名トークンを含む![式エディター](assets/personalization-uc-helpers-13.png)

1. 式を次のように変更します。
   1. 式エディターで、`name` トークンの後に製品名を指定します。

      次の構文を使用します。ここで、*product_name* は製品の名前を表します。

      ```javascript
      = "product_name"
      ```

      この例では、製品名は「Juno Jacket」です。

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name = "Juno Jacket" %}
         render_1
         {%else%} default_render
      {%/if%}
      ```

   1. 「render_1」プレースホルダーをメモのテキストに置き換えます。

      例：

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name = "Juno Jacket" %}
         Due to longer than usual lead times on the Juno Jacket, please expect item to ship two weeks after purchase.
         {%else%} default_render
      {%/if%}
      ```

   1. 式から「default_render」プレースホルダーを削除します。
1. 「 **[!UICONTROL 検証]**」をクリックしてから、「**[!UICONTROL 保存]**」をクリックします。

   ![if ブロックを設定した後、「検証して保存」を使用してHTML ウィンドウを編集する](assets/personalization-uc-helpers-14.png)

1. メッセージを保存します。

## 手順 6：ジャーニーのテストと公開 {#test-and-publish}

1. 「**[!UICONTROL テスト]**」切替スイッチをオンにしてから、「**[!UICONTROL イベントをトリガー]**」をクリックします。

   ![&#x200B; テスト トグルをオンにしてジャーニー ボタンをトリガーするイベントボタン &#x200B;](assets/personalization-uc-helpers-15.png)

1. **[!UICONTROL イベント設定]**&#x200B;ウィンドウで、入力値を入力し、「**[!UICONTROL 送信]**」をクリックします。

   テストモードは、テストプロファイルでのみ機能します。

   入力値と送信ボタンを含む![&#x200B; イベント設定ウィンドウ &#x200B;](assets/personalization-uc-helpers-16.png)

   メールがテストプロファイルのアドレスに送信されます。

   この例では、Juno Jacket に関するメモがメールに含まれています。これは、この製品が買い物かごに入っているからです。

   ![&#x200B; メッセージ本文にJuno Jacketの配送伝票が表示されているメールの例](assets/personalization-uc-helpers-17.png)

1. エラーがないことを確認し、ジャーニーを公開します。


## 関連トピック {#related-topics}

### Handlebars 関数 {#handlebars}

* [ヘルパー](functions/helpers.md)

* [文字列関数](functions/string.md)

### ユースケース {#use-case}

* [プロファイル情報、コンテキストおよびオファーを使用したパーソナライゼーション](personalization-use-case.md)

* [決定ベースのオファーを使用したパーソナライゼーション](../offers/offers-e2e.md)

## チュートリアルビデオ {#video}

ヘルパー関数の使用方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3416781?captions=jpn&quality=12)

---
title: パーソナライズ機能の使用例&amp；コロン；買い物かご放棄のEメール
description: ヘルパー関数を使用してメッセージをパーソナライズする方法を説明します
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Intermediate
source-git-commit: d5060fcd70a02a24af579d5fa86c5225d417fdc4
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 3%

---


# パーソナライズ機能の使用例：買い物かご放棄のEメール {#personalization-use-case-helper-functions}

この例では、Eメールメッセージの本文をパーソナライズします。 このメッセージは、買い物かごに品目を残したが購入を完了していない顧客をターゲットにします。

次のタイプのヘルパー関数を使用します。

* 顧客の名を大文字で挿入する`upperCase`文字列関数。 [詳細情報](functions/string.md#upper)。
* `each`ヘルパー。買い物かご内の項目をリストします。 [詳細情報](functions/helpers.md#each)。
* `if`ヘルパー。関連製品が買い物かごに入っている場合に製品固有のメモを挿入します。 [詳細情報](functions/helpers.md#if-function)。

<!-- **Context**: personalization based on contextual data from the journey -->

開始する前に、次の要素の設定方法を理解しておく必要があります。
* 電子メールメッセージ。 [詳細](../create-message.md)
* 電子メールの本文。 [詳細情報](../create-email-content.md)。
* 単一のイベント。 [詳細情報](../event/about-events.md)。
* イベントで始まるジャーニー。 [詳細情報](../building-journeys/using-the-journey-designer.md)。

次の手順に従います。
1. [Eメールメッセージを作成します](#configure-email)。
2. [顧客の名を大文字で挿入します](#uppercase-function)。
3. [最初のイベントとジャーニーを作成します](#create-context)。
4. [買い物かごの内容をEメールに追加します](#each-helper)。
5. [製品固有のメモを挿入します](#if-helper)。
6. [ジャーニーのテストと公開](#test-and-publish).

## 手順1:Eメールの作成{#configure-email}

1. 電子メールメッセージを作成または変更し、「**[!UICONTROL 電子メールデザイナー]**」をクリックします。
   ![](../assets/personalization-uc-helpers-1.png)

2. Eメールデザイナーホームページの左側のパレットから、3つの構造コンポーネントをメッセージの本文にドラッグ&amp;ドロップします。

3. HTMLコンテンツコンポーネントを、新しい各構造コンポーネントにドラッグ&amp;ドロップします。

   ![](../assets/personalization-uc-helpers-2.png)

## 手順2:顧客の名を大文字で挿入する {#uppercase-function}

1. Eメールデザイナーのホームページで、顧客の名を追加するHTMLコンポーネントをクリックします。
2. コンテキストツールバーで、「**[!UICONTROL ソースコードを表示]**」をクリックします。

   ![](../assets/personalization-uc-helpers-3.png)

3. **[!UICONTROL HTML]**&#x200B;を編集ウィンドウで、`upperCase`文字列関数を追加します。
   1. リストで、「**[!UICONTROL ヘルパー関数]**」を選択します。
   2. 検索フィールドを使用して、「大文字」を検索します。
   3. 検索結果から、`upperCase`関数を追加します。 これをおこなうには、`{%= upperCase(string) %}: string`の横のプラス記号(+)をクリックします。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%= upperCase(string) %}
      ```

      ![](../assets/personalization-uc-helpers-4.png)

4. 式から「文字列」プレースホルダーを削除します。
5. 名トークンを追加します。
   1. リストで、「**[!UICONTROL プロファイル]**」を選択します。
   2. **[!UICONTROL プロファイル]** / **[!UICONTROL ユーザー]** / **[!UICONTROL 姓]**&#x200B;を選択します。
   3. 式に&#x200B;**[!UICONTROL 名]**&#x200B;トークンを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%= upperCase(profile.person.name.firstName) %}
      ```

      ![](../assets/personalization-uc-helpers-5.png)

      [個人名データ型](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/person-name.html)の詳細をご覧ください。

6. 「****&#x200B;を検証&#x200B;**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/personalization-uc-helpers-6.png)
7. メッセージを保存します。

## 手順3:最初のイベントと関連するジャーニーの作成 {#create-context}

買い物かごのコンテンツは、ジャーニーからのコンテキスト情報です。 したがって、買い物かご固有の情報を電子メールに追加する前に、最初のイベントと電子メールをジャーニーに追加する必要があります。

1. スキーマに`productListItems`配列が含まれるイベントを作成します。
2. この配列のすべてのフィールドを、このイベントのペイロードフィールドとして定義します。

   [製品リスト項目データ型](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/product-list-item.html)の詳細をご覧ください。

3. このイベントで始まるジャーニーを作成します。
4. ジャーニーにメッセージを追加します。
5. 終了アクティビティでジャーニーを終了します。

   メッセージをまだ公開していないので、ジャーニーをテストしたり公開したりすることはできません。

   ![](../assets/personalization-uc-helpers-7.png)

6. 「**[!UICONTROL OK]**」をクリックします。

   ジャーニーのコンテキストがメッセージに渡されたことを示すメッセージが表示されます。

   ![](../assets/personalization-uc-helpers-8.png)

## 手順4:買い物かごからの項目リストの挿入 {#each-helper}

1. メッセージを再度開きます。

   ![](../assets/personalization-uc-helpers-18.png)

2. Eメールデザイナーのホームページで、買い物かごの内容を表示するHTMLコンポーネントをクリックします。
3. コンテキストツールバーで、「**[!UICONTROL ソースコードを表示]**」をクリックします。

   ![](../assets/personalization-uc-helpers-3.png)

4. **[!UICONTROL HTML]**&#x200B;を編集ウィンドウで、`each`ヘルパーを追加します。
   1. リストで、「**[!UICONTROL ヘルパー関数]**」を選択します。
   2. 検索フィールドを使用して、「each」を検索します。
   3. 検索結果から、 `each`ヘルパーを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {{#each someArray as |variable|}} {{/each}}
      ```

      ![](../assets/personalization-uc-helpers-9.png)

5. 式に`productListItems`配列を追加します。

   1. 式から「someArray」プレースホルダーを削除します。
   2. リストで、「**[!UICONTROL コンテキスト]**」を選択します。

      「 **[!UICONTROL コンテキスト]** 」オプションは、ジャーニーコンテキストがメッセージに渡された後でのみ使用できます。

   3. **[!UICONTROL Journey Orchestration]** > **[!UICONTROL イベント]** > ***[!UICONTROL イベント名]***を選択し、**[!UICONTROL productListItems]**&#x200B;ノードを展開します。

      この例では、*event_name*&#x200B;はイベントの名前を表します。

   4. 式に&#x200B;**[!UICONTROL Product]**&#x200B;トークンを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {{#each context.journey.events.event_ID.productListItems.product as |variable|}} {{/each}}
      ```
      この例では、*event_ID*&#x200B;はイベントのIDを表します。

      ![](../assets/personalization-uc-helpers-10.png)

   5. 式を変更します。
      1. 「.product」文字列を削除します。
      2. 「変数」プレースホルダーを「product」に置き換えます。

      次の例は、変更された式を示しています。

      ```handlebars
      {{#each context.journey.events.event_ID.productListItems as |product|}}
      ```
6. 次のコードを、開始`{{#each}}`タグと終了`{/each}}`タグの間に貼り付けます。

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

7. 品目名、数量および価格のパーソナライゼーショントークンを追加します。

   1. HTML表からプレースホルダー「#name」を削除します。
   2. 前の検索結果から、式に&#x200B;**[!UICONTROL Name]**&#x200B;トークンを追加します。

   次の手順を2回繰り返します。
   * プレースホルダー「#quantity」を&#x200B;**[!UICONTROL Quantity]**&#x200B;トークンに置き換えます。
   * プレースホルダー「#priceTotal」を&#x200B;**[!UICONTROL Total price]**&#x200B;トークンに置き換えます。

   次の例は、変更された式を示しています。

   ```handlebars
   {{#each context.journey.events.event_ID.productListItems as |product|}}
      <table>
         <tbody>
            <tr>
               <td><b>{{context.journey.events.event_ID.productListItems.name}}</b></td>
               <td><b>{{context.journey.events.event_ID.productListItems.quantity}}</b></td>
               <td><b>${{context.journey.events.event_ID.productListItems.priceTotal}}</b></td>
            </tr>
         </tbody>
      </table>
   {{/each}}
   ```
8. 「****&#x200B;を検証&#x200B;**[!UICONTROL 保存]**」をクリックします。
   ![](../assets/personalization-uc-helpers-11.png)

## 手順5:製品固有のメモの挿入 {#if-helper}

1. Eメールデザイナーのホームページで、メモを挿入するHTMLコンポーネントをクリックします。
2. コンテキストツールバーで、「**[!UICONTROL ソースコードを表示]**」をクリックします。

   ![](../assets/personalization-uc-helpers-3.png)

3. **[!UICONTROL HTML]**&#x200B;を編集ウィンドウで、`if`ヘルパーを追加します。
   1. リストで、「**[!UICONTROL ヘルパー関数]**」を選択します。
   2. 検索フィールドを使用して、「if」を検索します。
   3. 検索結果から、 `if`ヘルパーを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%#if condition1%} render_1
         {%else if condition2%} render_2
         {%else%} default_render
      {%/if%}
      ```
      ![](../assets/personalization-uc-helpers-12.png)

4. 式からこの条件を削除します。

   ```handlebars
   {%else if condition2%} render_2
   ```

   次の例は、変更された式を示しています。

   ```handlebars
   {%#if condition1%} render_1
      {%else%} default_render
   {%/if%}
   ```

5. 製品名トークンを条件に追加します。
   1. 式から「条件1」プレースホルダーを削除します。
   2. リストで、「**[!UICONTROL コンテキスト]**」を選択します。
   3. **[!UICONTROL Journey Orchestration]** > **[!UICONTROL イベント]** > ***[!UICONTROL イベント名]***を選択し、**[!UICONTROL productListItems]**&#x200B;ノードを展開します。

      この例では、*event_name*&#x200B;はイベントの名前を表します。

   4. 式に&#x200B;**[!UICONTROL 名前]**&#x200B;トークンを追加します。

      式エディターには、次の式が表示されます。

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name%}
         render_1
         {%else%} default_render
      {%/if%}
      ```
      ![](../assets/personalization-uc-helpers-13.png)

6. 式を変更します。
   1. 式エディターで、`name`トークンの後に製品名を指定します。

      次の構文を使用します。 *product_name*&#x200B;は、製品の名前を表します。

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

   2. 「render_1」プレースホルダーを注記のテキストに置き換えます。

      例：

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name = "Juno Jacket" %}
         Due to longer than usual lead times on the Juno Jacket, please expect item to ship two weeks after purchase.
         {%else%} default_render
      {%/if%}
      ```
   3. 式から「default_render」プレースホルダーを削除します。
7. 「****&#x200B;を検証&#x200B;**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/personalization-uc-helpers-14.png)

8. メッセージを保存して公開します。

## 手順6:ジャーニーのテストと公開 {#test-and-publish}

1. ジャーニーを開きます。 ジャーニーが既に開いている場合は、ページを更新します。
2. **[!UICONTROL テスト]**&#x200B;トグルをオンにして、**[!UICONTROL イベントをトリガー]**&#x200B;をクリックします。

   テストモードは、メッセージを公開した後でのみ有効にできます。

   ![](../assets/personalization-uc-helpers-15.png)

3. **[!UICONTROL イベント設定]**&#x200B;ウィンドウで、入力値を入力し、「**[!UICONTROL 送信]**」をクリックします。

   テストモードは、テストプロファイルでのみ機能します。

   ![](../assets/personalization-uc-helpers-16.png)

   このEメールは、テストプロファイルのアドレスに送信されます。

   この例では、Juno Jacketに関するメモが電子メールに含まれています。これは、この製品が買い物かごに入っているからです。

   ![](../assets/personalization-uc-helpers-17.png)

4. エラーがないことを確認して、ジャーニーを公開します。


## 関連トピック

### Handlebars関数

[ヘルパー](functions/helpers.md)

[文字列関数](functions/string.md)

### 使用例

[プロファイル情報、コンテキスト、オファーを使用したパーソナライゼーション](personalization-use-case.md)

[判定ベースのオファーを使用したパーソナライゼーション](../offers/offers-e2e.md)

## チュートリアルビデオ{#helper-functions-video}

>[!VIDEO](https://video.tv.adobe.com/v/334244?quality=12)
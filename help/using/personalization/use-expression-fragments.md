---
solution: Journey Optimizer
product: journey optimizer
title: 式フラグメントの使用
description: ' [!DNL Journey Optimizer]  パーソナライゼーションエディターで式フラグメントを使用する方法を説明します。'
feature: Personalization, Fragments
topic: Personalization
role: Developer
level: Intermediate
keywords: 式，エディター，ライブラリ，パーソナライゼーション
exl-id: 74b1be18-4829-4c67-ae45-cf13278cda65
TQID: https://experienceleague.adobe.com/0N5waBGElHBnlsk1pHhKT8roaly-A6srIjb3UPIDNqY
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a653cc2e-bc85-4353-a306-399e5b247978id: d998adac-2f81-400b-a669-d07bb196e4ebid: df64005d-8f9a-422e-ba4d-c6f6dc3454b4id: fe338112-e2ce-4876-8989-fc4d497613f1
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 1313
ht-degree: 0%

---

# 式フラグメントの活用 {#use-expression-fragments}

**パーソナライゼーションエディター**&#x200B;を使用する場合は、現在のサンドボックスに作成または保存されたすべての式フラグメントを活用できます。

フラグメントは、[!DNL Journey Optimizer]個のキャンペーンとジャーニーをまたいで参照できる再利用可能なコンポーネントです。 この機能により、マーケティングユーザーが使用できる複数のカスタムコンテンツブロックを事前に構築し、デザインプロセスを改善してコンテンツをすばやく組み立てることができます。 [ フラグメントの詳細](../content-management/fragments.md)

➡️ [このビデオでフラグメントを管理、作成、使用する方法を説明します](../content-management/fragments.md#video-fragments)

## 式フラグメントの使用 {#use-expression-fragment}

コンテンツにエクスプレッションフラグメントを追加するには、次の手順に従います。

>[!NOTE]
>
>1つの配信に最大30個のフラグメントを追加できます。 フラグメントは、最大1 レベルまでネストできます。

1. [ パーソナライゼーションエディター](personalization-build-expressions.md)を開き、左側のペインで「**[!UICONTROL フラグメント]**」ボタンを選択します。

   リストには、現在のサンドボックスでフラグメントとして作成または保存されたすべてのエクスプレッションフラグメントが表示されます。 [ フラグメントの作成方法を学ぶ](../content-management/create-fragments.md)
作成日で並べ替えられます。最近追加された式フラグメントは、リストの最初に表示されます。

   ![](assets/expression-fragments-pane.png)

   このリストを更新することもできます。

   >[!NOTE]
   >
   >コンテンツの編集中に一部のフラグメントが変更または追加された場合、リストは最新の変更で更新されます。

1. エクスプレッションフラグメントの横にある「+」アイコンをクリックして、対応するフラグメント IDをエディターに挿入します。

   ![](assets/expression-fragment-add.png)

   >[!CAUTION]
   >
   >任意の&#x200B;**ドラフト**&#x200B;または&#x200B;**ライブ** フラグメントをコンテンツに追加できます。 ただし、**ドラフト**&#x200B;のステータスを持つフラグメントが使用されている場合、ジャーニーまたはキャンペーンをアクティブにすることはできません。 ジャーニーまたはキャンペーンの公開時に、ドラフトフラグメントにエラーが表示され、公開できるようにするには承認が必要です。

1. フラグメント IDが追加されると、対応する式フラグメントを開き、インターフェイスから[編集](../content-management/manage-fragments.md#edit-fragments)すると、変更が同期されます。 これらのフラグメントは、そのフラグメント IDを含むすべてのドラフトまたはライブジャーニー/キャンペーンに自動的に反映されます。

1. フラグメントの横にある「**[!UICONTROL その他のアクション]**」ボタンをクリックします。 表示されるコンテキストメニューから、「**[!UICONTROL フラグメントを表示]**」を選択して、そのフラグメントに関する詳細情報を取得します。 **[!UICONTROL フラグメント ID]**&#x200B;も表示され、ここからコピーできます。

   ![](assets/expression-fragment-view.png)

1. エクスプレッションフラグメントを別のウィンドウで開いて、そのコンテンツとプロパティを編集できます。コンテキストメニューの「**[!UICONTROL フラグメントを開く]**」オプションを使用するか、**[!UICONTROL フラグメント情報]** ペインから使用します。 [ フラグメントの編集方法を学ぶ](../content-management/manage-fragments.md#edit-fragments)

   ![](assets/expression-fragment-open.png)

1. その後、[ パーソナライゼーションエディター](personalization-build-expressions.md)のすべてのパーソナライゼーション機能とオーサリング機能を使用して、通常どおりコンテンツをカスタマイズして検証できます。

1. 場合によっては、変数のみを計算する必要があるので、式フラグメントのコンテンツを非表示にすることができます。 これを行うには、`render`属性を使用して`false`に設定します。 例：

   ```
   Hi {{profile.person.name.firstName|fragment id='ajo:fragmentId/variantId' mode ='inline' render=false}}
   ```

>[!NOTE]
>
>複数の改行を含む式フラグメントを作成し、[SMS](../sms/create-sms.md#sms-content)または[ プッシュ ](../push/design-push.md)のコンテンツで使用すると、改行は保持されます。 したがって、[SMS](../sms/send-sms.md)または[ プッシュ ](../push/send-push.md) メッセージを送信する前に、必ずテストしてください。

## 暗黙的な変数の使用 {#implicit-variables}

暗黙的な変数は、既存のフラグメント機能を強化して、コンテンツの再利用性とスクリプトユースケースの効率を向上させます。 フラグメントでは、入力変数を使用して、キャンペーンおよびジャーニーのコンテンツで使用できる出力変数を作成できます。

この機能は、例えば、現在のキャンペーンやジャーニーに基づいてメールのトラッキングパラメーターを初期化し、これらのパラメーターをメールコンテンツに追加されたパーソナライズされたリンクに使用するために使用できます。

次のような使用例が考えられます。

1. **フラグメントで入力変数を使用します。**

   フラグメントがキャンペーン/ジャーニーアクションコンテンツで使用される場合、フラグメントの外部で宣言された変数を活用できます。 次に例を示します。

   ![](../personalization/assets/variable-in-a-fragment.png)

   `utm_content`変数の上に、キャンペーンコンテンツで宣言されていることがわかります。 フラグメント **ヒーローブロック**&#x200B;を使用すると、`utm_content` パラメーター値が追加されるリンクが表示されます。 最終結果は`https://luma.enablementadobe.com?utm_campaign= Product_launch&utm_content= start_shopping`です。

1. **フラグメントの出力変数を使用します。**

   フラグメント内で計算または定義された変数は、コンテンツで使用できます。 次の例では、フラグメント **F1**&#x200B;が一連の変数を宣言します。

   ![](../personalization/assets/personalize-with-variables.png)

   メールコンテンツでは、次のパーソナライゼーションを実行できます。

   ![](../personalization/assets/use-fragment-variable.png)

   フラグメント F1は、次の変数を初期化します：`utm_campaign`および`utm_content`。 次に、メッセージコンテンツ内のリンクに、これらのパラメーターが追加されます。 最終結果は`https://luma.enablementadobe.com?utm_campaign= Product_launch&utm_content= start_shopping`です。

>[!NOTE]
>
>実行時に、システムはフラグメント内の内容を拡張し、パーソナライゼーションコードを上から下に解釈します。 このことを念頭に置くと、より複雑なユースケースにも対応できます。 例えば、フラグメント F1が変数を下の別のフラグメント F2に渡すことができます。 また、ビジュアルフラグメント F1を使用して、ネストされた式フラグメント F2に変数を渡すこともできます。

## ループ内での式フラグメントの使用 {#fragments-in-loops}

`{{#each}}` ループ内の式フラグメントを使用する場合は、変数スコープがどのように機能するかを理解することが重要です。 式フラグメントは、メッセージコンテンツで定義されたグローバル変数にアクセスできますが、ループ固有の変数をパラメーターとして受け取ることはできません。

### サポートされているパターン：グローバル変数の使用 {#global-variables-in-loops}

式フラグメントは、フラグメントがループ内から呼び出された場合でも、フラグメントの外部で定義されたグローバル変数を参照できます。 これは、フラグメントを反復的なコンテキストで使用する必要がある場合に推奨されるアプローチです。

**例：ループ内のグローバル変数を含むフラグメントの使用**

メッセージコンテンツで、グローバル変数を定義し、それを参照するフラグメントを使用します。

```handlebars
{% let globalDiscount = 15 %}

{{#each context.journey.actions.GetProducts.items as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    <p>Price: ${{product.price}}</p>
    {{fragment id='ajo:fragment123/variant456' mode='inline'}}
  </div>
{{/each}}
```

式フラグメント （fragment123）では、`globalDiscount`変数を参照できます。

```handlebars
<p class="discount-info">Save {{globalDiscount}}% on all items!</p>
```

このパターンは、ループ コンテキストに関係なく、グローバル変数がフラグメント内を含め、メッセージ全体でアクセス可能であるため機能します。

### サポートされていません：ループ変数をフラグメントパラメーターとして渡します {#loop-variables-limitations}

現在のイテレーション項目（例：上記の例の`product`）をパラメーターとして式フラグメントに渡すことはできません。 フラグメントは、周囲の`{{#each}}` ブロックからループ範囲の変数に直接アクセスできません。

**例：動作しないもの**

```handlebars
{{#each context.journey.actions.GetProducts.items as |product|}}
  <!-- This will NOT work as expected -->
  {{fragment id='ajo:fragment123/variant456' mode='inline' currentProduct=product}}
{{/each}}
```

フラグメントは`product`をパラメーターとして受け取ることができず、ループ固有の変数に渡すパラメーターが現在の実装でサポートされていないため、内部で使用できません。

### 推奨される回避策 {#fragments-in-loops-workarounds}

ループからのデータで式フラグメントを使用する必要がある場合は、次の方法を検討します。

1. **メッセージにロジックを直接含める**: ループ固有のロジックにフラグメントを使用する代わりに、`{{#each}}` ブロック内にパーソナライゼーションコードを直接追加します。

   ```handlebars
   {{#each context.journey.actions.GetProducts.items as |product|}}
     <div class="product">
       <h3>{{product.name}}</h3>
       <p>Price: ${{product.price}}</p>
       {{#if product.price > 100}}
         <span class="premium-badge">Premium Product</span>
       {{/if}}
     </div>
   {{/each}}
   ```

2. **ループ外でフラグメントを使用**: フラグメントのコンテンツがループに依存しない場合は、イテレーションブロックの前後でフラグメントを呼び出します。

   ```handlebars
   {{fragment id='ajo:fragment123/variant456' mode='inline'}}
   
   {{#each context.journey.actions.GetProducts.items as |product|}}
     <div class="product">
       <h3>{{product.name}}</h3>
       <p>Price: ${{product.price}}</p>
     </div>
   {{/each}}
   ```

3. **複数のグローバル変数を設定**：複数のイテレーションにわたってフラグメントに異なる値を渡す必要がある場合は、各フラグメント呼び出しの前にグローバル変数を設定します（ただし、柔軟性が制限されます）。

>[!NOTE]
>
>コンテキストデータの繰り返しとループの操作については、[ コンテキストデータの繰り返しに関する包括的なガイド ](iterate-contextual-data.md)を参照してください。これには、ベストプラクティス、トラブルシューティングのヒント、高度なパターンが含まれます。

## 編集可能フィールドをカスタマイズ {#customize-fields}

式フラグメントの特定の部分が変数を使用して編集可能になっている場合は、特定の構文を使用してデフォルト値を上書きできます。 [ フラグメントをカスタマイズする方法について説明します](../content-management/customizable-fragments.md)

フィールドをカスタマイズするには、次の手順に従います。

1. 「**[!UICONTROL フラグメント]**」メニューからコードにフラグメントを挿入します。

1. 構文の最後にある`<fieldId>="<value>"` コードを使用して、変数のデフォルト値を上書きします。

   以下の例では、IDが「sports」の変数の値を「yoga」の値で上書きしています。 これにより、「スポーツ」変数が参照されるあらゆる場所で、フラグメントコンテンツに「ヨガ」が表示されます。

   ![](../content-management/assets/fragment-expression-use.png)

式フラグメントに編集可能なフィールドを追加し、メール作成時にその値を上書きする方法を示す例は、[このセクション ](../content-management/customizable-fragments.md#example)で利用できます。

## 継承を解除 {#break-inheritance}

パーソナライゼーションエディターにフラグメント IDを追加すると、元のエクスプレッションフラグメントに加えられた変更が同期されます。

ただし、エクスプレッションフラグメントのコンテンツをエディターにペーストすることもできます。 コンテキストメニューから、「**[!UICONTROL フラグメントを貼り付け]**」を選択して、そのコンテンツを挿入します。

![](assets/expression-fragment-paste.png)

その場合、元のフラグメントからの継承は壊れています。 フラグメントのコンテンツがエディターにコピーされ、変更が同期されなくなります。

これは、元のフラグメントにリンクされなくなったスタンドアロン要素になります。コード内の他の要素として編集できます。


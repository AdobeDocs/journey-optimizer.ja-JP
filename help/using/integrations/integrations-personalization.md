---
solution: Journey Optimizer
product: journey optimizer
title: 外部統合の使用
description: 外部統合をチャネルオーサリングプロセスに統合し、Adobe Target Delivery APIのレスポンスなど、パーソナライズされた動的な情報でコンテンツを強化できます
feature: Integrations
topic: Content Management
role: User
level: Beginner
keywords: 統合
feature_v2:
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
subfeature_v2:
  - id: d16f7424-4847-4b90-a37c-4b52cbdabee5
source-git-commit: bfb28a935dffca7c381fe72339abc840d2ab297b
workflow-type: tm+mt
source-wordcount: 842
ht-degree: 19%

---


# パーソナライゼーションに対する外部統合の使用 {#integrations-personalization}

>[!BEGINSHADEBOX]

**このページでは、** マーケターが設定された統合を適用して、メール、SMS、プッシュコンテンツをパーソナライズし、API呼び出しを別のAPIにチェーン付けして、より充実した動的なメッセージを作成する方法について説明します。

>[!ENDSHADEBOX]

コンテンツで外部統合を使用する前に、[統合の操作](integrations.md)で説明されているように、管理者が各統合（エンドポイント、認証、ポリシー、応答ペイロード、アクティベーション）を&#x200B;**設定およびアクティベート**&#x200B;していることを確認してください。

**[!UICONTROL フラグメント]**&#x200B;ごとに&#x200B;**3**&#x200B;件まで、メッセージに&#x200B;**5**&#x200B;件まで統合を追加できます。 フラグメントのみから取得された統合は、**5**&#x200B;にはカウントされません。

## コンテンツへの統合パーソナライゼーションの適用 {#apply-integration-personalization}

マーケターは、設定済みの統合を使用してコンテンツをパーソナライズできます。 次の手順に従います。

1. キャンペーンコンテンツにアクセスし、テキストまたは HTML **[!UICONTROL コンポーネント]**&#x200B;から「**[!UICONTROL パーソナライゼーションを追加]**」をクリックします。

   [コンポーネントの詳細情報](../email/content-components.md)

   ![](assets/external-integration-content-1.png)

1. 「**[!UICONTROL 統合]**」セクションに移動し、「**[!UICONTROL 統合を開く]**」をクリックして、アクティブな統合をすべて表示します。

   **Journey Optimizer フラグメント**&#x200B;は統合機能で利用できますが、アウトバウンドチャネルのみをサポートすることに注意してください。 フラグメントが公開されると、既存のジャーニーやキャンペーンへの影響を避けるために、新しい統合の追加と保存が無効になります。

   ![](assets/external-integration-content-2.png)

1. 統合を選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/external-integration-content-3.png)

1. **[!UICONTROL ピル]**&#x200B;モードを有効にして、高度な統合メニューをロック解除します。

   ![](assets/external-integration-content-4.png)

1. 統合パーソナライゼーションを作成する場合、統合ヘルパーには、エラーまたは不足しているデータがデフォルトコンテンツとどのように相互作用するかを定義する&#x200B;**`required`** フィールドが含まれます。

   * **`required=true`** （既定値）：そのメッセージのレンダリングが停止します。 送信は&#x200B;**`ExternalDataLookupExclusion`**&#x200B;で除外され、その除外は&#x200B;**メッセージフィードバックデータセット**&#x200B;に記録されます。
   * **`required=false`**：結果変数が&#x200B;**`null`**&#x200B;に設定され、レンダリングが続行されます。 テンプレートでデフォルトのテキスト、フォールバック、条件ロジックを使用することで、統合がデータを返さない場合にプロファイルが空のコンテンツを受け取らないようにします。

     ![](assets/external-integration-content-8.png)

1. 統合設定を完了するには、[設定](integrations.md#configure)時に以前指定した統合属性を定義します。

   これらの属性には、一定のままの静的値や、ユーザープロファイルから情報を動的に取り込むプロファイル属性のいずれかを使用して値を割り当てることができます。

   ![](assets/external-integration-content-5.png)

1. 統合属性を定義したら、![追加](assets/do-not-localize/Smock_Add_18_N.svg) アイコンをクリックして、パーソナライズされたメッセージに対してコンテンツの統合フィールドを使用できるようになります。

   ![](assets/external-integration-content-6.png)

   >[!NOTE]
   >
   >テンプレート内のトークンは、統合設定で公開された管理者のフィールドのみを使用する必要があります。 例えば、`{{weatherResponse.temperature}}`は`temperature`が公開されたときに有効です。`humidity`が公開されなかった場合、`{{weatherResponse.humidity}}`はエディターで拒否されます。

1. 「**[!UICONTROL 保存]**」をクリックします。

これで、統合パーソナライゼーションがコンテンツに正常に適用され、設定した属性に基づいて各受信者がカスタマイズされた関連性の高いエクスペリエンスを受信できるようになりました。

![](assets/external-integration-content-7.png)

## あるAPI呼び出しを別のAPI呼び出しにマッピングする {#map-integration-chain}

統合をチェーン化して、1つの呼び出しの結果を次の呼び出し（パスセグメント、ヘッダー、クエリパラメーターなど）にフィードできます。 呼び出しは同じメッセージ内で順番に実行され、カスタムコードなしでより豊かなパーソナライゼーションがサポートされます。

まず、次のことを確認してください。

* 管理者は、必要なすべての統合を設定してアクティブ化しました。 [統合の設定](integrations.md)を参照してください。
* バリアブルパスのプレースホルダー、ヘッダー、クエリパラメーターは、マーケター向けのラベルを使用した統合設定で設定されます。
* 管理者は、各統合の&#x200B;**[!UICONTROL 応答ペイロード]**&#x200B;で必要な応答フィールドを公開して、オーサリング時に表示できるようにしました。

次の例では、プロファイルの予約からフライト番号を返す予約統合を使用し、その番号をライブステータス（遅延、宛先）に使用するフライト情報統合を使用します。 2番目の統合の入力を1番目の呼び出しの応答にマッピングします。

1. メッセージまたはフラグメントを開き、パーソナライゼーションエディターを開きます。

   ![](assets/uc-integrations-1.png)

1. **[!UICONTROL 統合]**&#x200B;で、**[!UICONTROL 統合を開く]**&#x200B;をクリックします。

   ![](assets/uc-integrations-2.png)

1. フライト識別子を含む予約または予約データなど、応答が次の呼び出しをフィードする統合を追加します。

   ![](assets/uc-integrations-3.png)

1. （オプション） **[!UICONTROL ヘルパー関数]** メニューを開き、予約応答に名前付き変数をバインドする場合は、`Let`関数などのヘルパーを追加します。

   >[!NOTE]
   >
   > 管理者が定義した&#x200B;**[!UICONTROL 応答ペイロード]**&#x200B;で公開されたフィールドのみが使用できます。 設定で公開されていないプロパティを参照することはできません。

1. ヘルパー変数を使用する場合は、その変数を、旅客または予約ペイロードのフライト番号など、予約統合が下流使用のために返すフィールドにマッピングします。

   ![](assets/uc-integrations-4.png)

1. **[!UICONTROL 統合機能を開く]** メニューから、2番目の統合機能（フライトステータスなど）を追加します。

   ![](assets/uc-integrations-5.png)

1. 2つ目の統合で、**[!UICONTROL 統合属性]**&#x200B;を開きます。 パス変数、ヘッダー、クエリパラメーターなど、最初の呼び出しのデータを再利用する必要がある各入力について、最初の統合応答からマッピングソースを選択します。

   **[!UICONTROL ピル]** エクスペリエンスでは、`Let` ステートメントを使用せずに、ファーストコール出力をセカンドコール入力に直接マッピングできます。 `Let`を使用した場合は、代わりにその変数をマッピングできます。

   ![](assets/uc-integrations-6.png)

1. 2つ目の統合のトークンを、![add](assets/do-not-localize/Smock_Add_18_N.svg) コントロールを使用してコンテンツに挿入します。例えば、フライト情報の応答の宛先です。

   ![](assets/uc-integrations-8.png)

1. コンテンツを保存します。

**[!UICONTROL シミュレーション]**&#x200B;または送信時に、Journey Optimizerは次の順序で統合を実行します。最初の呼び出しは設定されたプロファイルコンテキストを使用し、その結果は2番目のリクエストをビルドします。 特定の統合がシミュレーションで実行されるか、送信時間が設定とチャネルによって異なります。

![](assets/uc-integrations-7.png)

<!--
## Use Adobe Target data in templates {#use-adobe-target-in-templates}

This section explains how to use **Integrations** in Adobe Journey Optimizer to fetch personalization data from **[!DNL Adobe Target]** at send time and use it in message templates. It assumes the Target Delivery API has already been configured as an integration.

For configuration steps, see [Work with Integrations](integrations.md) and the [Adobe Target Recommendations](vendor-integration.md#adobe-target-recommendations) sample.

The Target Delivery API returns a `prefetch.mboxes` array. Each mbox includes an `options` object with `content` and `type` fields. The `type` value determines how you use `content` in your template. Open the tab that matches your mbox response, then follow the steps to use that data in your message.

>[!BEGINTABS]

>[!TAB JSON content]

When `type` is `json`, the `content` field is a **JSON string**. Parse it before you access nested fields. The example below shows a typical Delivery API response for a JSON mbox.

```json
{
  "status": 200,
  "prefetch": {
    "mboxes": [
      {
        "index": 0,
        "name": "SummerOffer",
        "options": {
          "content": "{\"recommendations\":[{\"productId\":\"p101\",\"name\":\"Noise Smartwatch\",\"price\":2999},{\"productId\":\"p205\",\"name\":\"Boat Earbuds\",\"price\":1499}],\"strategy\":\"collaborative-filtering\"}",
          "type": "json"
        }
      }
    ]
  }
}
```

Use three helpers in sequence to fetch, extract, and parse the Target response.

1. **Fetch the Target response.** Call your configured Target integration with `externalDataLookup`. Set `integrationName` to the **[!UICONTROL Name]** of that integration (replace the example placeholder `target_recommendations`). Use the `result` parameter to name the template variable that holds the full Delivery API payload—for example, `targetResponse`.

    ```handlebars
    {{externalDataLookup integrationName="target_recommendations" result="targetResponse"}}
    ```

1. **Extract a specific mbox using valueAtPath.** `valueAtPath` extracts an element from an array by its 0-based index and assigns it to a template variable. Use the `idx` parameter to specify which element to access.

    ```handlebars
    {{valueAtPath targetResponse.prefetch.mboxes idx=0 result="summerOffer"}}
    ```

    | Parameter | Description |
    | --- | --- |
    | `path` | Path to the array (positional, no keyword) |
    | `idx` | 0-based index for array access (optional) |
    | `result` | Variable name to store the extracted value |

    >[!NOTE]
    >
    > If `idx` is out of bounds, rendering throws an exception. Guard invalid indexes with `{%#if idx >= 0 and idx < count(targetResponse.prefetch.mboxes)%}` when the index may be invalid. PQL expressions cannot be used as the path. **Available since release 2025.9.0.**

1. **Parse the JSON string using parseJson.** The mbox `options.content` field is a raw JSON string. `parseJson` converts it into a structured object whose fields can then be accessed directly in the template.

    ```handlebars
    {{parseJson jsonStr=summerOffer.options.content result="summerOfferContent"}}
    ```

    | Parameter | Description |
    | --- | --- |
    | `jsonStr` | Path to the string field containing valid JSON |
    | `result` | Variable name to store the parsed object |

    >[!NOTE]
    >
    > If the JSON string is invalid or the reference is null, `result` is set to `null` — no rendering error is thrown. Test with your actual Target response to confirm the content is valid JSON. **Available since: 2026.6.0**

1. **Access the data.** Once parsed, use dot notation to access fields from `summerOfferContent`. To render a list of recommendations:

    ```handlebars
    {{externalDataLookup integrationName="target_recommendations" result="targetResponse"}}
    {{valueAtPath targetResponse.prefetch.mboxes idx=0 result="summerOffer"}}
    {{parseJson jsonStr=summerOffer.options.content result="summerOfferContent"}}

    Strategy: {{summerOfferContent.strategy}}
    {{#each summerOfferContent.recommendations as |rec|}}
      {{rec.name}} — {{rec.price}}
    {{/each}}
    ```

>[!TAB HTML content]

When `type` is `html`, the `content` field is a ready-to-render HTML string. You do not need to parse it. The example below shows a typical Delivery API response for an HTML mbox.

```json
{
  "status": 200,
  "prefetch": {
    "mboxes": [
      {
        "index": 0,
        "name": "SummerOffer",
        "options": {
          "content": "<div class=\"offer\"><h2>Summer Sale</h2><p>50% off Smartwatch</p></div>",
          "type": "html"
        }
      }
    ]
  }
}
```

Fetch and extract the mbox, then render `content` directly. Skip `parseJson`.

```handlebars
{{externalDataLookup integrationName="target_recommendations" result="targetResponse"}}
{{valueAtPath targetResponse.prefetch.mboxes idx=0 result="summerOffer"}}
{{{summerOffer.options.content}}}
```

>[!NOTE]
>
> Use **triple braces** `{{{...}}}` to render HTML content as-is. Double braces `{{...}}` will escape HTML entities and render raw tag strings instead of the HTML.

>[!ENDTABS]

-->

## チュートリアルビデオ {#video}

このビデオでは、**統合**&#x200B;がAdobe Journey Optimizerを外部APIに接続して、ライブデータとコンテンツを&#x200B;**アウトバウンド**&#x200B;のチャネル、電子メール、SMS、プッシュ通知に取り込み、より適切なパーソナライゼーションを実現する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3484118/?learn=on)

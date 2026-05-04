---
solution: Journey Optimizer
product: journey optimizer
title: 外部統合を有効にする
description: 外部統合をチャネルオーサリングプロセスに統合し、パーソナライズされた動的な情報でコンテンツを強化します。
feature: Integrations
topic: Content Management
role: User
level: Beginner
keywords: 統合
source-git-commit: 4cc3c959fe08c1d574a5d041bf7721441bc96f97
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 43%

---


# パーソナライゼーションに対する外部統合の使用 {#integrations-personalization}

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

<!--

## Map one API call to another {#map-integration-chain}

You can **chain** integrations so that values returned by one active integration drive the inputs (path, headers, or query parameters) of another. That lets you build a real-time data flow in a single message without custom code.

Before you start, make sure that:

* An administrator has configured and activated every integration you need. See [Configure your Integration](integrations.md).
* Variable path placeholders, headers, and query parameters are set up in the integration configuration with marketer-facing labels.
* The administrator exposed the response fields you need in each integration's **[!UICONTROL Response payload]** so they appear when authoring.

In the below example, a reservation system integration returns a flight booking reference from the profile context. A separate flight-information integration expects that reference as a **path variable**. In the personalization editor, you map the second integration's variable to a field from the first integration's response, instead of a static value or profile attribute alone.

1. Open your message or fragment and place the cursor where you want personalized content (for example, a **[!UICONTROL Text]** field).

1. Open the personalization editor and go to **[!UICONTROL Integrations]** → **[!UICONTROL Open integrations]**.

1. Select the integration whose output will supply the downstream input (in the example, the reservation or profile API that returns the flight identifier).

1. Define that integration's inputs as usual—static values, profile attributes, or other allowed mappings—then save so its response is available for chaining.

    >[!NOTE]
    >
    > Fields must appear in the administrator-defined response payload for each integration. You cannot reference response properties that were not exposed in configuration.

1. Select the **second** integration (for example, the API that needs the flight number or booking reference on the URL path).

1. For each input that must come from the first call—often a **path variable** or **variable** header/query parameter—choose the mapping source that references the **first integration's response** (for example, the flight booking reference field from the reservation payload). Do not use a static test value if you need live, profile-specific data.

1. Insert the response tokens you need in the content (for example, destination name from the flight API, loyalty balance from a loyalty integration) using the ![add](assets/do-not-localize/Smock_Add_18_N.svg) control.

1. Save the personalization.

When you **simulate** or send, Journey Optimizer resolves integrations in order: the first call runs with the profile context you configured; its output is used to build the second request. Different integrations may run at simulation time and at send time according to your setup and channel behavior.

-->

## チュートリアルビデオ {#video}

このビデオでは、**統合**&#x200B;がAdobe Journey Optimizerを外部APIに接続して、ライブデータとコンテンツを&#x200B;**アウトバウンド**&#x200B;のチャネル、電子メール、SMS、プッシュ通知に取り込み、より適切なパーソナライゼーションを実現する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3484118/?learn=on)

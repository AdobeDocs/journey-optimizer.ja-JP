---
title: メール設定
description: チャネルの表面レベルで電子メールを設定する方法を説明します
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 13536962-7541-4eb6-9ccb-4f97e167734a
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 68%

---

# メール設定 {#email-settings}

チャネルサーフェスの専用セクション（メッセージプリセット）設定で E メール設定を定義します。 でサーフェスを作成する方法を学ぶ [この節](message-presets.md).

![](assets/preset-email-settings.png)

## メールのタイプ {#email-type}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_emailtype"
>title="電子メールカテゴリの定義"
>abstract="このチャネルサーフェスを使用する際に送信される E メールのタイプを選択します。ユーザーの同意を必要とするプロモーション E メールのマーケティング、または非商用 E メールのトランザクション。特定のコンテキストで購読解除されたプロファイルに送信することもできます。"

内 **電子メールのタイプ** 「 」セクションで、チャネルサーフェスと共に送信されるメッセージのタイプを選択します。 **マーケティング** または **トランザクション**.

* 選択 **マーケティング** プロモーション E メールの場合：これらのメッセージにはユーザーの同意が必要です。

* 選択 **トランザクション** （注文の確認、パスワードリセット通知、配信情報など、非商用の E メールの場合）。

>[!CAUTION]
>
>**トランザクション** マーケティングコミュニケーションから購読解除したプロファイルに電子メールを送信できます。 これらのメッセージは、特定のコンテキストでのみ送信できます。

条件 [メッセージの作成](../messages/get-started-content.md#create-new-message)を選択した場合は、電子メールに対して選択したカテゴリに一致する有効なチャネルサーフェスを選択する必要があります。

## サブドメインおよび IP プール {#subdomains-and-ip-pools}

「**サブドメインおよび IP プールの詳細**」セクションでは、以下を実行する必要があります。

1. メールの送信に使用するサブドメインを選択します。[詳細情報](about-subdomain-delegation.md)

1. サーフェスに関連付ける IP プールを選択します。 [詳細情報](ip-pools.md)

![](assets/preset-subdomain-ip-pool.png)

選択した IP プールが下にある間は、サーフェスの作成を続行できません [版](ip-pools.md#edit-ip-pool) (**[!UICONTROL 処理中]** ステータス ) との間に存在し、選択したサブドメインに関連付けられていない。 それ以外の場合は、IP プール／サブドメインの関連付けの最も古いバージョンが引き続き使用されます。この場合は、サーフェスをドラフトとして保存し、IP プールに **[!UICONTROL 成功]** ステータス。

>[!NOTE]
>
>非実稼動環境の場合、アドビは、標準のテストサブドメインの作成や、共有送信 IP プールへのアクセスを許可しません。[独自のサブドメインをデリゲート](delegate-subdomain.md)して、組織に割り当てられたプールの IP を使用する必要があります。

## List-Unsubscribe {#list-unsubscribe}

リストの[サブドメインの選択](#subdomains-and-ip-pools)から、「**[!UICONTROL List-Unsubscribe を有効にする]**」オプションが表示されます。

![](assets/preset-list-unsubscribe.png)

このオプションは、デフォルトでは有効になっています。

有効にしたままにすると、次のような登録解除リンクが電子メールヘッダーに自動的に含まれます。

![](assets/preset-list-unsubscribe-header.png)

このオプションを無効にした場合、電子メールヘッダーに登録解除リンクは表示されません。

登録解除リンクは、次の 2 つの要素で構成されます。

* すべての登録解除リクエストの送信先となる&#x200B;**登録解除メールアドレス**。

   In [!DNL Journey Optimizer]の場合、配信停止の E メールアドレスがデフォルトです **[!UICONTROL 宛先（配信停止）]** チャネルサーフェスに表示されるアドレス ( [選択したサブドメイン](#subdomains-and-ip-pools).

   ![](assets/preset-list-unsubscribe-mailto.png)

* 購読解除後にユーザーがリダイレクトされるランディングページの URL である&#x200B;**登録解除 URL**。

   次の場合、 [ワンクリックオプトアウトリンク](../messages/consent.md#one-click-opt-out) この表面を使用して作成されたメッセージに対する配信停止 URL は、ワンクリックオプトアウトリンク用に定義された URL になります。

   ![](assets/preset-list-unsubscribe-opt-out-url.png)

   >[!NOTE]
   >
   >メッセージコンテンツにワンクリックオプトアウトリンクを追加しない場合、ユーザーにランディングページは表示されません。

メッセージにヘッダー登録解除リンクを追加する方法について詳しくは、[この節](../messages/consent.md#unsubscribe-header)を参照してください。

<!--Select the **[!UICONTROL Custom List-Unsubscribe]** option to enter your own Unsubscribe URL and/or your own Unsubscribe email address.(to add later)-->

## ヘッダーパラメーター{#email-header}

内 **[!UICONTROL ヘッダーパラメーター]** 「 」セクションで、送信者の名前と、その表面を使用して送信される E メールのタイプに関連する E メールアドレスを入力します。

>[!CAUTION]
>
>これらのメールアドレスでは、現在選択されている[デリゲートされたサブドメイン](about-subdomain-delegation.md)を使用する必要があります。

* **[!UICONTROL 送信者名]**：送信者の名前（会社のブランド名など）。

* **[!UICONTROL 送信者のメール]**：コミュニケーションに使用するメールアドレス。例えば、デリゲートされたサブドメインが *marketing.luma.com* の場合は、*contact@marketing.luma.com* を使用できます。

* **[!UICONTROL 返信先（名前）]**：受信者がメールクライアントソフトウェアの「**返信**」ボタンをクリックしたときに使用する名前。

* **[!UICONTROL 返信先（メール）]**：受信者がメールクライアントソフトウェアの「**返信**」ボタンをクリックしたときに使用するメールアドレス。デリゲートされたサブドメインに定義されたアドレス（例：*reply@marketing.luma.com*）を使用する必要があります。このアドレスを使用していないメールは破棄されます。

* **[!UICONTROL エラーメール]**：メールを配信してから数日後に ISP で発生したすべてのエラー（非同期バウンス）は、このアドレスで受信されます。

![](assets/preset-header.png)

>[!NOTE]
>
>アドレスは、文字（A ～ Z）で始まる必要があり、英数字のみを使用できます。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

### メールの転送 {#forward-email}

デリゲートされたサブドメインの [!DNL Journey Optimizer] で受信したすべてのメールを特定のメールアドレスに転送する場合は、アドビカスタマーケアにお問い合わせください。以下を指定する必要があります。

* 選択した転送メールアドレス。転送メールアドレスドメインは、アドビにデリゲートされたサブドメインと同じにはできないことに注意してください。
* サンドボックス名。
* 転送 E メールアドレスを使用する表面名。
* 現在の **[!UICONTROL 返信先（E メール）]** チャネルサーフェスレベルで設定されたアドレス。

>[!NOTE]
>
>サブドメインごとに 1 つの転送メールアドレスのみ指定できます。その結果、複数のサーフェスが同じサブドメインを使用する場合は、すべてのサーフェスで同じ転送用 E メールアドレスを使用する必要があります。

転送メールアドレスはアドビが設定します。これには 3～4 日かかる場合があります。

## BCC メール {#bcc-email}

[!DNL Journey Optimizer] から送信された電子メールの同一のコピー（またはブラインドカーボンコピー）を BCC インボックスに送信できます。BCC インボックスは、コンプライアンスやアーカイブの目的で保存されます。

これをおこなうには、 **[!UICONTROL BCC 電子メール]** チャンネルサーフェスレベルでのオプション機能。 [詳細情報](bcc-email.md)

![](assets/preset-bcc.png)

## メールの再試行パラメーター {#email-retry}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_retryperiod"
>title="再試行期間の調整"
>abstract="一時的なソフトバウンスエラーが原因で E メール配信が失敗した場合は、3.5 日（84 時間）再試行が実行されます。 このデフォルトの再試行期間は、ニーズに合わせて調整できます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configuration-message/email-configuration/monitor-reputation/retries.html?lang=ja" text="再試行について"

次の項目を設定できます。 **E メール再試行パラメーター**.

![](assets/preset-retry-parameters.png)

デフォルトでは、[再試行期間](retries.md#retry-duration)は 84 時間に設定されていますが、必要に応じてこの設定を調整できます。

次の範囲内の整数値（時間または分）を入力する必要があります。

* マーケティングメールの場合、再試行期間の下限は 6 時間です。
* トランザクションメールの場合、再試行期間の下限は 10 分です。
* どちらのメールタイプでも、再試行期間の上限は 84 時間（5040 分）です。

再試行の詳細については、[この節](retries.md)を参照してください。

## URL トラッキング {#url-tracking}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_utm"
>title="URL トラッキングパラメーターの定義"
>abstract="このセクションを使用すると、メールコンテンツに存在する URL にトラッキングパラメーターを自動的に追加できます。この機能はオプションです。"

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_url_preview"
>title="URL トラッキングパラメーターのプレビュー"
>abstract="メールコンテンツに存在する URL にトラッキングパラメーターを追加する方法を確認します。"

以下を使用できます。 **[!UICONTROL URL トラッキングパラメーター]** チャネルをまたいでマーケティング活動の効果を測定する。 この機能はオプションです。

このセクションで定義されたパラメーターは、メールメッセージコンテンツに含まれる URL の末尾に追加されます。その後、これらのパラメーターを Adobe Analytics や Google Analytics などの web 分析ツールで取得し、様々なパフォーマンスレポートを作成できます。

![](assets/preset-url-tracking.png)

3 つの URL トラッキングパラメータが、チャネルサーフェスを作成する際の例として自動入力されます。 これらを編集し、「**[!UICONTROL 新しいパラメーターを追加]**」ボタンを使用して最大 10 個のトラッキングパラメーターを追加できます。

URL トラッキングパラメーターを設定するには、目的の値を&#x200B;**[!UICONTROL 名前]**&#x200B;および&#x200B;**[!UICONTROL 値]**&#x200B;フィールドで直接入力することができます。

次のオブジェクトに移動して、事前定義済みの値のリストから選択することもできます。
* ジャーニー属性：**ソース ID**、**ソース名**、**ソースバージョン ID**
* アクション属性：**アクション ID**、**アクション名**
* Offer Decisioning 属性：**オファー ID**、**オファー名**

![](assets/preset-url-tracking-source.png)

>[!CAUTION]
>
>フォルダーは選択しないでください。必要なフォルダーを参照し、トラッキングパラメーター値として使用するプロファイル属性を選択します。

<!--or edit it using the Expression editor. Learn more on [personalization](../../personalization/personalize.md#use-expression-editor). Select the contextual attribute of your choice.

You can drag and drop the parameters to reorder them.-->

以下に、Adobe Analytics および Google Analytics 互換 URL の例を示します。

* Adobe Analytics 互換 URL：`www.YourLandingURL.com?cid=email_AJO_{{context.system.source.id}}_image_{{context.system.source.name}}`

* Google Analytics 互換 URL：`www.YourLandingURL.com?utm_medium=email&utm_source=AJO&utm_campaign={{context.system.source.id}}&utm_content=image`

>[!NOTE]
>
>テキスト値の入力と、事前定義された値の選択を組み合わせることができます。各&#x200B;**[!UICONTROL 値]**&#x200B;フィールドには、合計 255 文字まで入力できます。

結果のトラッキング URL を動的にプレビューできます。パラメーターを追加、編集、または削除するたびに、プレビューが自動的に更新されます。

![](assets/preset-url-tracking-preview.png)
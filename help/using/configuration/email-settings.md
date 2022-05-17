---
title: メール設定
description: メッセージプリセットレベルで電子メールを設定する方法を説明します
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
source-git-commit: a036f53b88425d64281d2ac530016d638e2d13c9
workflow-type: tm+mt
source-wordcount: '1013'
ht-degree: 68%

---

# メール設定 {#email-settings}

メッセージプリセット設定の専用のセクションで電子メール設定を定義します。 メッセージプリセットを [この節](message-presets.md).

![](assets/preset-email.png)

## メールのタイプ {#email-type}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_emailtype"
>title="電子メールカテゴリの定義"
>abstract="このプリセットを使用する際に送信されるメッセージのタイプを選択します。ユーザーの同意が必要なプロモーションメッセージ用の「マーケティング」または、特定のコンテキストで購読解除済みのプロファイルにも送信できる非商用メッセージ用の「トランザクション」です。"

「**メールのタイプ**」セクションで、プリセットと共に送信されるメッセージのタイプ（「**マーケティング**」または「**トランザクション**」）を選択します。

* プロモーションメッセージの場合は、「**マーケティング**」を選択します。これらのメッセージにはユーザーの同意が必要です。

* 注文確認、パスワードリセット通知、配信情報など、非商用メッセージの場合は、「**トランザクション**」を選択します。

>[!CAUTION]
>
>**トランザクション**&#x200B;メッセージは、アドビからのお知らせで購読を解除したプロファイルに送信できます。これらのメッセージは、特定のコンテキストでのみ送信できます。

[メッセージの作成](../messages/get-started-content.md#create-new-message)時に、メッセージに対して選択したカテゴリに一致する有効なメッセージプリセットを選択する必要があります。

## サブドメインおよび IP プール {#subdomains-and-ip-pools}

「**サブドメインおよび IP プールの詳細**」セクションでは、以下を実行する必要があります。

1. メールの送信に使用するサブドメインを選択します。[詳細](about-subdomain-delegation.md)

1. プリセットに関連付ける IP プールを選択します。[詳細](ip-pools.md)

![](assets/preset-subdomain-ip-pool.png)

選択した IP プールが以下の場合は、プリセットの作成を続行できません [版](ip-pools.md#edit-ip-pool) (**[!UICONTROL 処理中]** ステータス ) との間に存在し、選択したサブドメインに関連付けられていない。 それ以外の場合は、IP プール/サブドメインの関連付けの最も古いバージョンが引き続き使用されます。 その場合は、プリセットをドラフトとして保存し、IP プールに **[!UICONTROL 成功]** ステータス。

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

   [!DNL Journey Optimizer] の場合、登録解除の電子メールアドレスは、[選択したサブドメイン](#subdomains-and-ip-pools)に基づいてメッセージプリセットに表示されるデフォルトの&#x200B;**[!UICONTROL 宛先（登録解除）]**&#x200B;アドレスです。

   ![](assets/preset-list-unsubscribe-mailto.png)

* 購読解除後にユーザーがリダイレクトされるランディングページの URL である&#x200B;**登録解除 URL**。

   [ワンクリックオプトアウトリンク](../messages/consent.md#one-click-opt-out)をこのプリセットを使用して作成されたメッセージに加える場合、登録解除 URL は、ワンクリックオプトアウトリンク用に定義された URL になります。

   ![](assets/preset-list-unsubscribe-opt-out-url.png)

   >[!NOTE]
   >
   >メッセージコンテンツにワンクリックオプトアウトリンクを追加しない場合、ユーザーにランディングページは表示されません。

メッセージにヘッダー登録解除リンクを追加する方法について詳しくは、[この節](../messages/consent.md#unsubscribe-header)を参照してください。

<!--Select the **[!UICONTROL Custom List-Unsubscribe]** option to enter your own Unsubscribe URL and/or your own Unsubscribe email address.(to add later)-->

## ヘッダーパラメーター{#email-header}

「**[!UICONTROL ヘッダーパラメーター]**」セクションでは、そのプリセットを使用して送信されるメッセージのタイプに関連付けられた送信者の名前とメールアドレスを入力します。

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

## メールの再試行パラメーター {#email-retry}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_retryperiod"
>title="再試行期間の調整"
>abstract="一時的なソフトバウンスエラーが原因で電子メールメッセージが失敗した場合は、3.5 日間（84 時間）再試行が実行されます。このデフォルトの再試行期間は、ニーズに合わせて調整できます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configuration-message/email-configuration/monitor-reputation/retries.html?lang=ja" text="再試行について"

**メールの再試行パラメーター**&#x200B;を設定できます。

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
>title="URL トラッキングパラメーター"
>abstract="このセクションを使用して、E メールコンテンツに存在するキャンペーン URL にトラッキングパラメーターを自動的に追加します。"

以下を使用できます。 **[!UICONTROL URL トラッキングパラメーター]** チャネルをまたいでマーケティング活動の効果を測定する。 この機能は のオプションです。


このセクションで定義されたパラメーターは、E メールメッセージコンテンツに含まれる URL の末尾に追加されます。 その後、これらのパラメーターをAdobe AnalyticsやGoogle Analyticsなどの Web 分析ツールで取得し、様々なパフォーマンスレポートを作成できます。

![](assets/preset-url-tracking.png)

例として、3 つの URL トラッキングパラメーターがメッセージプリセットの作成時に自動入力されます。 これらを編集し、を使用して最大 10 個のトラッキングパラメーターを追加できます。 **[!UICONTROL 新しいパラメーターを追加]** 」ボタンをクリックします。

URL トラッキングパラメーターを設定するには、目的の値を **[!UICONTROL 名前]** および **[!UICONTROL 値]** フィールドを選択するか、次のオブジェクトに移動して、事前定義済みの値のリストから選択します。

* ジャーニー属性： **ソース ID**, **ソース名**, **ソースバージョン ID**
* メッセージ属性： **アクション ID**, **アクション名**
* Offer decisioning属性： **オファー ID**, **オファー名**

![](assets/preset-url-tracking-source.png)

>[!CAUTION]
>
>フォルダーは選択しないでください：必要なフォルダーを参照し、トラッキングパラメーター値として使用するプロファイル属性を選択します。

以下に、Adobe AnalyticsとGoogle Analytics互換 URL の例を示します。

* Adobe Analytics互換 URL: `www.YourLandingURL.com?cid=email_AJO_{{context.system.source.id}}_image_{{context.system.source.name}}`

* Google Analytics互換 URL: `www.YourLandingURL.com?utm_medium=email&utm_source=AJO&utm_campaign={{context.system.source.id}}&utm_content=image`

>[!NOTE]
>
>テキスト値の入力と、事前定義された値の選択を組み合わせることができます。 各 **[!UICONTROL 値]** フィールドには、合計 255 文字まで入力できます。

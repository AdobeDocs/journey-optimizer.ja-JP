---
title: メッセージプリセットの作成
description: メッセージプリセットを設定および監視する方法について学ぶ
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 9038528f-3da0-4e0e-9b82-b72c67b42391
source-git-commit: 7039c816c459ba8cb5dbb52daf3c8265e1e1a511
workflow-type: tm+mt
source-wordcount: '1751'
ht-degree: 56%

---

# メッセージプリセットの作成

[!DNL Journey Optimizer] では、メッセージプリセットを設定して、メールとプッシュ通知メッセージに必要な技術的パラメーター（メールのタイプ、送信者のメールと名前、モバイルアプリなど）を定義しておくことができます。

>[!CAUTION]
>
> * メッセージプリセットは、ジャーニー管理者のみが設定できます。 [詳細](../administration/ootb-product-profiles.md#journey-administrator)
>
> * 電子メール設定を実行し、 [プッシュ設定](../push-configuration.md) メッセージプリセットを作成する前の手順です。


メッセージプリセットを設定すると、メッセージを作成する際に「**[!UICONTROL プリセット]**」リストからメッセージプリセットを選択できるようになります。

➡️ [メールプリセットの作成および使用方法については、このビデオを参照](#video-presets)

## メッセージプリセットの作成 {#create-message-preset}

メッセージプリセットを作成するには、次の手順に従います。

1. 次にアクセス： **[!UICONTROL チャネル]** > **[!UICONTROL ブランディング]** > **[!UICONTROL メッセージプリセット]** メニュー、次に「 **[!UICONTROL メッセージプリセットを作成]**.

   ![](../assets/preset-create.png)

1. プリセットの名前と説明（オプション）を入力し、設定するチャネルを選択します。

   ![](../assets/preset-general.png)

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。 アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. **メール**&#x200B;の設定を行います。

   ![](../assets/preset-email.png)

   * プリセットを使用して送信するメッセージのタイプ（**トランザクション**&#x200B;または&#x200B;**マーケティング**）を選択します。

      >[!CAUTION]
      >
      > **トランザクション**&#x200B;メッセージは、アドビからのお知らせで購読を解除したプロファイルに送信できます。トランザクションメッセージは、パスワードのリセット、注文のステータス、配信の通知など、特定のコンテキストでのみ送信できます。

   * メールの送信に使用するサブドメインを選択します。 [詳細](about-subdomain-delegation.md)
   * プリセットに関連付ける IP プールを選択します。 [詳細](ip-pools.md)
   * そのプリセットを使用して送信するメールのヘッダーパラメーターを入力します。

      >[!CAUTION]
      >
      >電子メールアドレスは、現在選択されている [委任サブドメイン](about-subdomain-delegation.md).

      <!--CAUTION: Except for the **Reply to (forward email)** field-->

      * **[!UICONTROL 送信者名]**:送信者の名前（ブランド名など）。

      * **[!UICONTROL 送信者のメール]**：コミュニケーションに使用するメールアドレス。例えば、デリゲートされたサブドメインが *marketing.luma.com* の場合は、*contact@marketing.luma.com* を使用できます。

      * **[!UICONTROL 返信先（名前）]**：受信者がメールクライアントソフトウェアの「**返信**」ボタンをクリックしたときに使用する名前。

      * **[!UICONTROL 返信先（メール）]**：受信者がメールクライアントソフトウェアの「**返信**」ボタンをクリックしたときに使用するメールアドレス。<!--The emails sent to this address will be forwarded to the **[!UICONTROL Reply to (forward email)]** address provided below. -->デリゲートされたサブドメインに定義されたアドレス（例：*reply@marketing.luma.com*）を使用する必要があります。使用しないと、メールは破棄されます。

      * **[!UICONTROL エラーメール]**：メールを配信してから数日後に ISP が生成したすべてのエラー（非同期バウンス）は、このアドレスで受信します。

      <!--**[!UICONTROL Reply to (forward email)]**: All emails received by [!DNL Journey Optimizer] for the delegated subdomain will be forwarded to this email address. You can specify any address, except an email address defined on the delegated subdomain. For example, if the delegated subdomain is *marketing.luma.com*, any address like *abc@marketing.luma.com* is prohibited.-->

      >[!NOTE]
      >
      >2021 年 10 月リリース以降は、 [!DNL Journey Optimizer] ユーザーインターフェイス。 すべてのメールを [!DNL Journey Optimizer] 特定の電子メールアドレスに転送されるデリゲートされたサブドメインについては、 [Adobeカスタマーケアサポートチーム](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。 <!--move to Deprecated features section when created?-->

      ![](../assets/preset-header.png)

      >[!NOTE]
      >
      >名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。 アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

   * **メール再試行パラメーター**&#x200B;を設定します。デフォルトでは、[再試行期間](retries.md#retry-duration)は 84 時間に設定されていますが、必要に応じてこの設定を調整できます。

      ![](../assets/preset-retry-paramaters.png)

      次の範囲内の整数値（時間または分）を入力する必要があります。
      * マーケティングメールタイプの場合、再試行期間の下限は 6 時間です。
      * トランザクションメールタイプの場合、再試行期間の下限は 10 分です。
      * どちらのメールタイプでも、再試行期間の上限は 84 時間（5040 分）です。


1. **プッシュ通知**&#x200B;の設定を行います。

   ![](../assets/preset-push.png)

   * 少なくとも 1 つのプラットフォーム（**iOS** または／および **Android**）を選択します。

   * 各プラットフォームで使用するモバイルアプリケーションを選択します。

      プッシュ通知を送信する環境の設定方法については、[この節](../push-gs.md)を参照してください。

<!--
1. Configure the **SMS** settings.

     ![](../assets/preset-sms.png)

    * Select the **[!UICONTROL SMS Type]** that will be sent with the preset: **[!UICONTROL Transactional]** or **[!UICONTROL Marketing]**
    
    * Select the **[!UICONTROL SMS configuration]** to associate with the preset.
        
      For more on how to configure your environment to send SMS messages, refer to [this section](sms-configuration.md).

    * Enter the **[!UICONTROL Sender number]** ​you want to use for your communications.
-->

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。 なお、メッセージプリセットをドラフトとして保存し、後で設定を再開することもできます。

   ![](../assets/preset-submit.png)

1. メッセージプリセットが作成されると、リストに「**[!UICONTROL 処理中]**」のステータスで表示されます。

   この段階では、メッセージプリセットが適切に設定されていることを確かめるために、いくつかのチェックが実行されています。 処理時間は約 **48h-72h**、および **7 ～ 10 営業日**.

   これらのチェックには、Adobeチームが実行する設定および技術テストが含まれます。

   * SPF 検証
   * DKIM 検証
   * MX レコードの検証
   * 拒否リストへの IP 登録の検証
   * Helo ホストの検証
   * IP プールの検証
   * A/PTR レコード、t/m/res サブドメインの検証

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](#monitor-message-presets)を参照してください。

1. チェックが正常に完了すると、メッセージプリセットのステータスが「**[!UICONTROL アクティブ]**」になります。メッセージの配信に使用する準備が整いました。

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/preset-active.png)

## メッセージプリセットの監視 {#monitor-message-presets}

すべてのメッセージプリセットが **[!UICONTROL チャネル]** > **[!UICONTROL メッセージプリセット]** メニュー フィルターを使用すると、チャネルタイプ、ユーザー、ステータスに応じてリストを参照できます。

![](../assets/preset-filters.png)

メッセージプリセットには、次のステータスがあります。

* **[!UICONTROL ドラフト]**：メッセージプリセットは下書きとして保存されており、まだ送信されていません。設定を再開するには、これを開きます。
* **[!UICONTROL 処理中]**：メッセージプリセットが送信され、いくつかの検証手順を実行中です。
* **[!UICONTROL アクティブ]**：メッセージプリセットは検証済みであり、選択してメッセージを作成できます。
* **[!UICONTROL 失敗]**：メッセージプリセットの検証中に、1 つ以上のチェックが失敗しました。
* **[!UICONTROL 非アクティブ]**:メッセージプリセットが非アクティブ化されます。 新しいメッセージの作成には使用できません。

メッセージプリセットの作成に失敗した場合、考えられる各エラー理由の詳細は次のとおりです。

これらのエラーのいずれかが発生した場合は、[アドビカスタマーケアサポートチーム](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}にご連絡ください。

* **SPF 検証に失敗しました**：SPF（Sender Policy Framework）はメール認証プロトコルで、特定のサブドメインからメールを送信できる承認済み IP を指定できます。SPF 検証エラーは、SPF レコードの IP アドレスが、メールボックスプロバイダーへのメール送信に使用される IP アドレスと一致しないことを意味します。

* **DKIM 検証に失敗しました** : DKIM（DomainKeys Identified Mail）を使用すると、受信したメッセージが関連ドメインの正規の送信者によって送信されたこと、および元のメッセージの内容が途中で改変されていないことを受信サーバーが検証できます。DKIM 検証の失敗は、メッセージコンテンツの信頼性とメッセージコンテンツの送信ドメインとの関連付けを受信メールサーバーが検証できないことを意味します。

* **MX レコードの検証に失敗しました** : MX（Mail eXchange）レコードの検証の失敗は、特定のサブドメインに代わって受信メールを受け取るべきメールサーバーが正しく設定されていないことを意味します。

* **配信品質の設定に失敗しました**：配信品質の設定の失敗は、次のいずれかの理由で起こる可能性があります。
   * 割り当てられた IP がブロックリストに登録されている
   * `helo` 名が無効
   * 対応するプリセットの IP プールで指定された IP 以外の IP からメールが送信される
   * Gmail や Yahoo などの主要な ISP の受信ボックスにメールを配信できない

## メッセージプリセットの編集 {#edit-message-preset}

メッセージプリセットを編集するには、次の手順に従います。

>[!NOTE]
>
>次の項目は編集できません： **[!UICONTROL プッシュ通知設定]**. メッセージプリセットがプッシュ通知チャネル用にのみ設定されている場合、編集できません。

1. リストで、メッセージプリセット名をクリックして開きます。

   ![](../assets/preset-name.png)

1. その IP プールのプロパティを必要に応じて編集します。 

   >[!NOTE]
   >
   >メッセージプリセットに **[!UICONTROL アクティブ]** ステータス、 **[!UICONTROL 名前]**, **[!UICONTROL チャネルを選択]** および **[!UICONTROL サブドメイン]** フィールドは灰色表示になっており、編集できません。

1. クリック **[!UICONTROL 送信]** 変更を確定します。

   ![](../assets/preset-confirm-update.png)

   >[!NOTE]
   >
   >また、メッセージプリセットをドラフトとして保存し、後で更新を再開することもできます。

変更が送信されると、メッセージプリセットは、次の場合と同じような検証サイクルを繰り返します。 [プリセットの作成](#create-message-preset).

>[!NOTE]
>
>次の項目だけを編集する場合、 **[!UICONTROL 説明]**, **[!UICONTROL E メールのタイプ]** および/または **[!UICONTROL E メールの再試行パラメーター]** フィールドを指定すると、更新が即時に実行されます。

メッセージプリセットの場合、 **[!UICONTROL アクティブ]** のステータスを確認すると、更新の詳細を確認できます。 この作業を行うには、以下の手順を実行します。

* 次をクリック： **[!UICONTROL 最近の更新]** アクティブなプリセット名の横に表示されるアイコン。

   ![](../assets/preset-recent-update-icon.png)

* 更新の処理中に、アクティブなメッセージプリセットから更新の詳細にアクセスすることもできます。

   ![](../assets/preset-view-update-details.png)

の **[!UICONTROL 最近の更新]** 画面には、更新ステータス、<!--the approximate remaining time before completion (if validation is in progress)--> 要求された変更のリスト

![](../assets/preset-recent-update-screen.png)

### ステータスを更新 {#update-statuses}

メッセージプリセットの更新には、次のステータスがあります。

* **[!UICONTROL 処理中]**:メッセージプリセットの更新が送信され、いくつかの検証手順を実行しています。
* **[!UICONTROL 成功]**:更新されたメッセージプリセットが検証され、メッセージを作成するために選択できます。
* **[!UICONTROL 失敗]**:メッセージプリセットの更新の検証中に、1 つ以上のチェックが失敗しました。

各ステータスについては、以下で詳しく説明します。

### Processing

プリセットが正しく更新されたことを確認するために、いくつかの配信品質チェックが実行されます。

>[!NOTE]
>
>次の項目だけを編集する場合、 **[!UICONTROL 説明]**, **[!UICONTROL E メールのタイプ]** および/または **[!UICONTROL E メールの再試行パラメーター]** フィールドを指定すると、更新が即時に実行されます。

処理時間は約 **48h-72h**、および **7 ～ 10 営業日**. 検証サイクルで実行されたチェックの詳細については、 [この節](#create-message-preset).

既にアクティブなプリセットを編集する場合：

* ステータスは変わりません **[!UICONTROL アクティブ]** 検証プロセスが進行中の間に

* この **[!UICONTROL 最近の更新]** メッセージプリセットリストのプリセット名の横にアイコンが表示されます。

* 検証プロセス中、このプリセットを使用して設定されたメッセージは、古いバージョンのプリセットを引き続き使用します。

>[!NOTE]
>
>更新中は、メッセージプリセットを変更できません。 名前はクリックできますが、すべてのフィールドが灰色表示になっています。 変更は、更新が正常に完了するまで反映されません。

### 成功

検証プロセスが正常に完了すると、このプリセットを使用するすべてのメッセージで、新しいバージョンのプリセットが自動的に使用されます。 ただし、次の場合は待つ必要があります。
* 単一メッセージで消費されるまで数分間
* バッチメッセージでプリセットが有効になる次のバッチまで。

<!--Changes made to a message preset with the **[!UICONTROL Active]** status will automatically be applied to all messages currently using this preset.-->

### Failed

検証プロセスが失敗した場合でも、古いバージョンのプリセットが引き続き使用されます。

<!--The possible update error types are as follows:
* **Authorization error**: the bearer token is invalid or not authorized.
* **Illegal modification**: an edit was performed on one or more non-allowed fields.
* **Precondition failed**: some fields can only have specific values and this has not been honored.-->

考えられる失敗理由について詳しくは、 [この節](#monitor-message-presets).

更新が失敗すると、プリセットが再び編集可能になります。 名前をクリックし、修正する必要のある設定を更新できます。

## メッセージプリセットの非アクティブ化 {#deactivate-preset}

を作成するには、以下を実行します。 **[!UICONTROL アクティブ]** 新しいメッセージを作成するには、メッセージプリセットを使用できません。非アクティブにすることができます。 ただし、このプリセットを使用して公開したメッセージは影響を受けず、引き続き機能します。

>[!NOTE]
>
>更新の処理中にメッセージプリセットを非アクティブ化することはできません。 更新が正常に完了するか、失敗するまで待つ必要があります。 詳細情報： [メッセージプリセットの編集](#edit-message-preset) そして [ステータスを更新](#update-statuses).

1. メッセージプリセットリストにアクセスします。

1. 任意のアクティブなプリセットの場合は、 **[!UICONTROL その他のアクション]** 」ボタンをクリックします。

1. 選択 **[!UICONTROL 無効化]**.

   ![](../assets/preset-deactivate.png)

>[!NOTE]
>
>非アクティブのメッセージプリセットは削除できません。メッセージの送信にそのプリセットを使用しているジャーニーへの影響を避けるためです。

非アクティブ化されたメッセージプリセットは直接編集できません。 ただし、コピーを作成してコピーを編集し、新しいバージョンを作成して新しいメッセージを作成することはできます。 また、再度アクティブ化し、更新が正常に完了するまで待って編集することもできます。

![](../assets/preset-activate.png)

<!--1. Access the message presets list.

1. Deactivate the message preset that you want to edit.

1. Duplicate the deactivated message preset. A copy with the **[!UICONTROL Draft]** status is automatically added to the list.

    ![](../assets/preset-duplicated.png)

1. Open the duplicated message preset, modify it according to your needs, then submit your changes. The message preset will go through the same validation cycle as during the [creation step](#create-message-preset).

1. Once validated, it gets the **[!UICONTROL Active]** status and is ready to be used to create new messages.-->

## ハウツービデオ{#video-presets}

メッセージプリセットの作成方法と使用方法、サブドメインのデリゲート方法および IP プールの作成方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334343?quality=12)

---
solution: Journey Optimizer
product: journey optimizer
title: SMS チャネルの設定
description: Journey Optimizer で SMS を送信するように環境を設定する方法を学ぶ
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: 442e3213ad512b62332cd08d6639dfc52bdc766a
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 86%

---

# SMS チャネルの設定 {#sms-configuration}

[!DNL Journey Optimizer] では、ジャーニーを作成し、ターゲットとなるオーディエンスにメッセージを送信できます。

SMS を送信する前に、インスタンスを設定します。Journey Optimizer と[プロバイダー設定を統合](#create-api)し、[SMS サーフェスを作成](#message-preset-sms)する必要があります（SMS プリセットなど）。これらの手順は、[Adobe Journey Optimizer システム管理者](../start/path/administrator.md)が実行する必要があります。

## 前提条件{#sms-prerequisites}

Adobe Journey Optimizer は現在、Sinch や Twilio などのサードパーティプロバイダーと統合されており、そうしたプロバイダーは Adobe Journey Optimizer とは独立に SMS サービスを提供しています。

SMS を設定する前に、こうしたいずれかの SMS プロバイダーのアカウントを作成して、Adobe Journey Optimizer と該当する SMS プロバイダー間の接続を確立するための API トークンとサービス ID を受信できるようにする必要があります。

SMS サービスを使用した場合、該当する SMS プロバイダーが定める追加の利用条件に同意したとみなされます。Sinch と Twilio は、Adobe Journey Optimizer と統合することでユーザーが利用できるサードパーティ製品であるため、SMS サービスに関する問題や問い合わせについてサポートを受ける際は、Sinch または Twilio のユーザーが対象の SMS プロバイダーに問い合わせる必要があります。サードパーティ製品について、アドビは一切関係せず、責任も負いません。

>[!CAUTION]
>
>SMS サブドメインにアクセスして編集するには、実稼動サンドボックスにおける **[!UICONTROL SMS サブドメインの管理]**&#x200B;権限が必要です。

## 新しい API 認証情報の作成 {#create-api}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_header"
>title="Journey Optimizer で SMS ベンダーを設定する"
>abstract="ベンダーを選択し、SMS API の認証情報を入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api"
>title="Journey Optimizer で SMS ベンダーを設定する"
>abstract="SMS を送信する前に、プロバイダー設定を Journey Optimizer と統合する必要があります。 完了したら、SMS サーフェスを作成する必要があります。 これらの手順は、Adobe Journey Optimizer システム管理者が実行する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/sms/sms-configuration.html?lang=ja#message-preset-sms" text="SMS チャネルサーフェスの作成"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_configuration"
>title="SMS ベンダー設定の選択"
>abstract="SMS ベンダーに設定する API 認証情報を選択します。"

お使いの SMS ベンダーを Journey Optimizer に設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報の作成]**」ボタンをクリックします。

   ![](assets/sms_6.png)

1. SMS API の資格情報を設定します。

   * の場合 **[!DNL Sinch]**:

      * **[!UICONTROL 名前]**:API 資格情報の名前を選択します。

      * **[!UICONTROL サービス ID]** および **[!UICONTROL API トークン]**:API ページにアクセスするには、「 SMS 」タブで資格情報を確認します。  [詳細情報](https://developers.sinch.com/docs/sms/getting-started/)
   * の場合 **[!DNL Twilio]**:

      * **[!UICONTROL 名前]**:API 資格情報の名前を選択します。

      * **[!UICONTROL アカウント SID]** および **[!UICONTROL 認証トークン]**:Twilio コンソールダッシュボードページの「アカウント情報」ペインにアクセスして、資格情報を検索します。

      * **[!UICONTROL メッセージ SID]**:Twilio の API で作成されるすべてのメッセージに割り当てられる一意の識別子を入力します。 [詳細情報](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-)
   * の場合 **[!DNL Infobip]**:

      * **[!UICONTROL 名前]**:API 資格情報の名前を選択します。

      * **[!UICONTROL API ベース URL]** および **[!UICONTROL API トークン]**:web インターフェイスのホームページまたは API キー管理ページにアクセスして、資格情報を見つけます。 [詳細情報](https://www.infobip.com/docs/api)

   ![](assets/sms_7.png)

1. API 認証情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 認証情報を作成して設定した後、SMS メッセージ用のチャネルサーフェス（メッセージプリセットなど）を作成する必要があります。

## SMS サーフェスの作成 {#message-preset-sms}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_sms_type"
>title="SMS カテゴリの定義"
>abstract="このサーフェスを使用する SMS メッセージのタイプを選択します（ユーザーの同意が必要なプロモーション SMS メッセージの場合は「マーケティング」、パスワードリセットなどの非商用 SMS メッセージの場合は「トランザクション」）。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html?lang=ja#sms-opt-out-management" text="マーケティング SMS メッセージのオプトアウト"

SMS チャネルを設定したら、**[!DNL Journey Optimizer]** から SMS メッセージを送信できるように、チャネルサーフェスを作成する必要があります。

チャネルサーフェスを作成するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL ブランディング]**／**[!UICONTROL チャネルサーフェス]**&#x200B;を選択します。「**[!UICONTROL チャネルサーフェスを作成]**」ボタンをクリックします。

   ![](assets/preset-create.png)

1. サーフェスの名前と説明（オプション）を入力し、SMS チャネルを選択します。

   ![](assets/sms_preset.png)

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. **SMS 設定**&#x200B;を定義します。

   ![](assets/preset-sms.png)

   * サーフェスを使用して送信される **[!UICONTROL SMS タイプ]**&#x200B;を選択します（**[!UICONTROL トランザクション]**&#x200B;または&#x200B;**[!UICONTROL マーケティング]**）。

      * プロモーション SMS の場合は、「**マーケティング**」を選択します。これらのメッセージにはユーザーの同意が必要です。
      * 注文確認、パスワードリセット通知、配信情報などの非商用メッセージの場合は、「**トランザクション**」を選択します。

      >[!CAUTION]
      >
      >**トランザクション** SMS メッセージは、アドビからのお知らせを登録解除したプロファイルに送信できます。これらのメッセージは、特定のコンテキストでのみ送信できます。

      メッセージの作成時に、選択したメッセージカテゴリに一致する有効なチャネルサーフェスを選択する必要があります。

   * **[!UICONTROL SMS 設定]**&#x200B;を選択し、サーフェスと関連付けます。

      SMS メッセージを送信する環境の設定方法については、[この節](#create-api)を参照してください。

   * コミュニケーションに使用する「**[!UICONTROL 送信者番号]**」を入力します。

   * 「**[!UICONTROL SMS 実行フィールド]**」を選択して、プロファイルの電話番号に関連付けられた「**[!UICONTROL プロファイル属性]**」を選択します。


1. SMS メッセージで URL 短縮機能を使用する場合は、**[!UICONTROL サブドメイン]**&#x200B;リストから項目を選択します。

   >[!NOTE]
   >
   >サブドメインを選択するには、1 つ以上の SMS サブドメインを事前に設定していることを確認してください。[方法についてはこちらを参照](sms-subdomains.md)

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。なお、チャネルサーフェスをドラフトとして保存し、後で設定を再開することもできます。

   ![](assets/sms_preset_2.png)

1. チャネルサーフェスが作成されると、リストに「**[!UICONTROL 処理中]**」のステータスで表示されます。

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](#monitor-channel-surfaces)を参照してください。

1. チェックが正常に完了すると、チャネルサーフェスのステータスが「**[!UICONTROL アクティブ]**」になります。メッセージの配信に使用する準備が整いました。

   ![](assets/preset-active.png)

これで、Journey Optimizer で SMS メッセージを送信する準備が整いました。

**関連トピック**

* [SMS メッセージの作成](create-sms.md)
* [ジャーニーへのメッセージの追加](../building-journeys/journeys-message.md)
* [キャンペーンへのメッセージの追加](../campaigns/create-campaign.md)


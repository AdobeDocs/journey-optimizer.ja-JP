---
title: SMS 設定
description: Journey Optimizer で SMS メッセージを送信するように環境を設定する方法を学ぶ
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: b31eb2bcf52bb57aec8e145ad8e94790a1fb44bf
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 47%

---

# SMS チャネルの設定 {#sms-configuration}

[!DNL Journey Optimizer] では、ジャーニーを作成し、ターゲットとなるオーディエンスにメッセージを送信できます。

SMS を送信する前に、インスタンスを設定します。 以下が必要です。 [プロバイダー設定の統合](#create-api) Journey Optimizerと [SMS サーフェスの作成](#message-preset-sms) （例：SMS プリセット）。 これらの手順は、 [Adobe Journey Optimizerシステム管理者](../start/path/administrator.md).

>[!AVAILABILITY]
>
>SMS チャネルは現在、一連の組織でのみ使用できます（使用制限があります）。 詳しくは、アドビ担当者にお問い合わせください。

## 新しい API 認証情報の作成 {#create-api}

Journey Optimizer で SMS ベンダーを設定するには、次の手順に従います。

1. 「**[!UICONTROL 管理]**」／「**[!UICONTROL チャネル]**」／「**[!UICONTROL API 認証情報]**」メニューにアクセスし、「 **[!UICONTROL API 認証情報の作成]**」をクリックします。

   ![](assets/sms_4.png)

1. を選択します。 **[!UICONTROL SMS ベンダー]**:

   * [!DNL Sinch]。次を検索： **[!UICONTROL サービス ID]** および **[!UICONTROL API トークン]** Sinch アカウントから SMS / API メニューにアクセスします。
   * [!DNL Twilio]。次を検索： **[!UICONTROL サービス ID]** および **[!UICONTROL API トークン]**&#x200B;をクリックし、コンソールダッシュボードページの「アカウント情報」ペインにアクセスします。

1. API 認証情報の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

1. **[!UICONTROL サービス ID]** と **[!UICONTROL API トークン]**&#x200B;を入力します。

   ![](assets/sms_5.png)

1. API 認証情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 資格情報を作成して設定した後、SMS メッセージのチャネル面（メッセージプリセット）を作成する必要があります。

## SMS メッセージのチャネルサーフェスを作成する {#message-preset-sms}

SMS チャネルを設定したら、SMS メッセージを送信するチャネルサーフェスを作成する必要があります。 **[!DNL Journey Optimizer]**.

チャネルサーフェスを作成するには、次の手順に従います。

1. 次にアクセス： **[!UICONTROL チャネル]** > **[!UICONTROL ブランディング]** > **[!UICONTROL チャンネルサーフェス]** メニュー、次に「 **[!UICONTROL チャンネルサーフェスを作成]**.

   ![](assets/preset-create.png)

1. サーフェスの名前と説明（オプション）を入力し、SMS チャネルを選択します。

   ![](assets/sms_preset.png)

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. **SMS** の設定を行います。

   ![](assets/preset-sms.png)

   * を選択します。 **[!UICONTROL SMS の種類]** それは表面と共に送られる **[!UICONTROL トランザクション]** または **[!UICONTROL マーケティング]**.

   * を選択します。 **[!UICONTROL SMS 設定]** サーフェスに関連付ける

      SMS メッセージを送信する環境の設定方法については、[この節](#create-api)を参照してください。

   * コミュニケーションに使用する「**[!UICONTROL 送信者番号]**」を入力します。

   * を選択します。 **[!UICONTROL SMS 実行フィールド]** をクリックし、 **[!UICONTROL プロファイル属性]** プロファイルの電話番号に関連付けられています。

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。また、チャンネルサーフェスをドラフトとして保存し、後で設定を再開することもできます。

   ![](assets/sms_preset_2.png)

1. チャネルサーフェスが作成されると、リストには次の情報が表示されます。 **[!UICONTROL 処理中]** ステータス。

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](#monitor-channel-surfaces)を参照してください。

1. チェックが正常に完了すると、チャネルサーフェスは **[!UICONTROL アクティブ]** ステータス。 メッセージの配信に使用する準備が整いました。

   ![](assets/preset-active.png)

これで、Journey Optimizer で SMS メッセージを送信する準備が整いました。

**関連トピック**

* [SMS メッセージの作成](../messages/create-sms.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)

---
title: SMS 設定
description: Journey Optimizer で SMS メッセージを送信するように環境を設定する方法を学ぶ
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: c86c9121e601f0c208626f578e923e7d30adc9c4
workflow-type: ht
source-wordcount: '414'
ht-degree: 100%

---

# SMS チャネルの設定 {#sms-configuration}

>[!CAUTION]
>
> SMS チャネルは、現在、一部のユーザーのみが早期アクセスで利用できます。この機能を利用する場合は、アドビアカウント担当者にお問い合わせください。

[!DNL Journey Optimizer] では、ジャーニーを作成し、ターゲットとなるオーディエンスにメッセージを送信できます。

## 新しい API 認証情報の作成 {#create-api}

Journey Optimizer で SMS ベンダーを設定するには、次の手順に従います。

1. 「**[!UICONTROL 管理]**」／「**[!UICONTROL チャネル]**」／「**[!UICONTROL API 認証情報]**」メニューにアクセスし、「 **[!UICONTROL API 認証情報の作成]**」をクリックします。

   ![](../assets/sms_4.png)

1. **[!UICONTROL SMS ベンダー]**&#x200B;として Sinch を選択します。

1. API 認証情報の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

1. **[!UICONTROL サービス ID]** と **[!UICONTROL API トークン]**&#x200B;を入力します。

   >[!NOTE]
   >
   > Sinch には特別な API 認証情報が必要です。次を検索： **[!UICONTROL サービス ID]** と **[!UICONTROL API トークン]**&#x200B;を検索するには、Sinch アカウントから SMS／API メニューにアクセスします。

   ![](../assets/sms_5.png)

1. API 認証情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 認証情報を作成して設定した後、SMS メッセージ用のメッセージプリセットを作成する必要があります。

## SMS メッセージ用メッセージプリセットの作成 {#message-preset-sms}

SMS チャネルを設定したら、**[!DNL Journey Optimizer]** から SMS メッセージを送信できるように、メッセージプリセットを作成する必要があります。

メッセージプリセットを作成するには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL ブランディング]**／**[!UICONTROL メッセージプリセット]**&#x200B;メニューにアクセスし、「**[!UICONTROL メッセージプリセットを作成]**」をクリックします。

   ![](../assets/preset-create.png)

1. プリセットの名前と説明（オプション）を入力し、SMS チャネルを選択します。

   ![](../assets/sms_preset.png)

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。 アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. **SMS** の設定を行います。

   ![](../assets/preset-sms.png)

   * プリセットを使用して送信する **[!UICONTROL SMS タイプ]**（**[!UICONTROL トランザクション]**&#x200B;または&#x200B;**[!UICONTROL マーケティング]**）を選択します。

   * **[!UICONTROL SMS 設定]**&#x200B;を選択し、プリセットと関連付けます。

      SMS メッセージを送信する環境の設定方法については、[この節](sms-configuration.md)を参照してください。

   * コミュニケーションに使用する「**[!UICONTROL 送信者番号]**」を入力します。

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。 なお、メッセージプリセットをドラフトとして保存し、後で設定を再開することもできます。

   ![](../assets/sms_preset_2.png)

1. メッセージプリセットが作成されると、リストに「**[!UICONTROL 処理中]**」のステータスで表示されます。

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](#monitor-message-presets)を参照してください。

1. チェックが正常に完了すると、メッセージプリセットのステータスが「**[!UICONTROL アクティブ]**」になります。メッセージの配信に使用する準備が整いました。

   ![](../assets/preset-active.png)

プッシュ通知およびメールのメッセージプリセットを設定する方法については、[この節](message-presets.md)を参照してください。

これで、Journey Optimizer で SMS メッセージを送信する準備が整いました。

**関連トピック**

* [SMS メッセージの作成](../create-sms.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)

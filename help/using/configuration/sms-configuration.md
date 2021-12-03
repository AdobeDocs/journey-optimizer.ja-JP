---
title: SMS 設定
description: Journey Optimizerで SMS メッセージを送信するように環境を設定する方法を説明します
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: e4125d3e1f0c382c1f2ca13ad080aba830c5df46
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 31%

---

# SMS チャネルの設定 {#sms-configuration}

>[!CAUTION]
>
> 現在、SMS チャネルは、一部のユーザーに対してのみ早期にアクセスできます。 この機能を利用する場合は、担当のAdobeアカウント担当者にお問い合わせください。

[!DNL Journey Optimizer] では、ジャーニーを作成し、ターゲティングされたオーディエンスにメッセージを送信できます。

## 新しい API 資格情報を作成 {#create-api}

Journey Optimizerで SMS ベンダーを設定するには、次の手順に従います。

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL API 資格情報]** メニュー、次に「 **[!UICONTROL API 資格情報を作成]**.

   ![](../assets/sms_4.png)

1. としてシンチを選択します。 **[!UICONTROL SMS ベンダー]**.

1. を入力します。 **[!UICONTROL 名前]** API 資格情報用に保存されます。

1. を入力します。 **[!UICONTROL サービス ID]** および **[!UICONTROL API トークン]**.

   >[!NOTE]
   >
   > Sinch には特別な API 資格情報が必要です。 次を検索： **[!UICONTROL サービス ID]** および **[!UICONTROL API トークン]** Sinch アカウントから SMS / API メニューにアクセスします。

   ![](../assets/sms_5.png)

1. クリック **[!UICONTROL 送信]** API 資格情報の設定が完了したとき。

API 資格情報を作成して設定した後、SMS メッセージ用のメッセージプリセットを作成する必要があります。

## SMS メッセージのメッセージプリセットの作成 {#message-preset-sms}

SMS チャネルを設定したら、SMS メッセージを送信できるように、メッセージプリセットを作成する必要があります。 **[!DNL Journey Optimizer]**.

メッセージプリセットを作成するには、次の手順に従います。

1. 次にアクセス： **[!UICONTROL チャネル]** > **[!UICONTROL ブランディング]** > **[!UICONTROL メッセージプリセット]** メニュー、次に「 **[!UICONTROL メッセージプリセットを作成]**.

   ![](../assets/preset-create.png)

1. プリセットの名前と説明（オプション）を入力し、SMS チャネルを選択します。

   ![](../assets/sms_preset.png)

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。 アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. の設定 **SMS** 設定。

   ![](../assets/preset-sms.png)

   * を選択します。 **[!UICONTROL SMS の種類]** プリセットと共に送信される **[!UICONTROL トランザクション]** または **[!UICONTROL マーケティング]**.

   * を選択します。 **[!UICONTROL SMS 設定]** プリセットに関連付けます。

      SMS メッセージを送信するように環境を設定する方法について詳しくは、 [この節](sms-configuration.md).

   * 次を入力します。 **[!UICONTROL 送信者番号]** 通信に&#x200B;使用する

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。 なお、メッセージプリセットをドラフトとして保存し、後で設定を再開することもできます。

   ![](../assets/sms_preset_2.png)

1. メッセージプリセットが作成されると、リストに「**[!UICONTROL 処理中]**」のステータスで表示されます。

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](#monitor-message-presets)を参照してください。

1. チェックが正常に完了すると、メッセージプリセットのステータスが「**[!UICONTROL アクティブ]**」になります。メッセージの配信に使用する準備が整いました。

   ![](../assets/preset-active.png)

プッシュ通知および E メールのメッセージプリセットを設定する方法については、 [この節](message-presets.md).

これで、Journey Optimizerで SMS メッセージを送信する準備が整いました。

**関連トピック**

* [SMS メッセージの作成](../create-sms.md)
* [ジャーニーへのメッセージの追加](../building-journeys/journeys-message.md)

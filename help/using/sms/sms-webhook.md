---
solution: Journey Optimizer
product: journey optimizer
title: SMS Webhook の設定
description: オプトインとオプトアウトの同意を管理するために、インバウンド応答を取り込むための Webhook を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: a0f3e385-934d-44d6-a487-6035161aef0e
source-git-commit: 2bd0048c356c668ce2611b923f126e2a4e2c8630
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 71%

---

# Webhook の作成 {#webhook}

>[!BEGINSHADEBOX]

オプトインキーワードやオプトアウトキーワードを指定していない場合は、ユーザーのプライバシーを遵守するために標準の同意メッセージが使用されます。カスタムキーワードを追加すると、デフォルト設定が自動的に上書きされます。

**デフォルトのキーワード：**

* **オプトイン**：SUBSCRIBE、YES、UNSTOP、START、CONTINUE、RESUME、BEGIN
* **オプトアウト**：STOP、QUIT、CANCEL、END、UNSUBSCRIBE、NO
* **ヘルプ**：HELP

>[!ENDSHADEBOX]

API 資格情報が正常に作成されたら、Webhook を設定して、オプトインとオプトアウトの同意を管理するインバウンド応答をキャプチャし、利用可能な場合は開封確認などの配信レポートを受信できるようになりました。

Webhook を設定する際に、取得するデータの種類に基づいて目的を定義できます。

* **[!UICONTROL インバウンド]**：オプトインやオプトアウトなどの同意応答を取得し、ユーザーの環境設定を収集する場合は、このオプションを使用します。

* **[!UICONTROL フィードバック]**：このオプションを選択すると、レシートの読み取りやユーザーのインタラクションなど、配信およびエンゲージメントイベントをトラッキングし、レポートや分析をサポートすることができます。

SMS プロバイダーに応じて、以下のタブを参照します。

>[!BEGINTABS]

>[!TAB カスタム]

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;に移動し、**[!UICONTROL SMS 設定]**&#x200B;の下にある **[!UICONTROL SMS Webhook]** メニューを選択して、「**[!UICONTROL Webhook を作成]**」ボタンをクリックします。

   ![](assets/sms_byo_5.png){zoomable="yes"}

1. 以下で説明するように、Webhook 設定を指定します。

   * **[!UICONTROL 名前]**：Webhook の名前を入力します。

   * **[!UICONTROL SMS ベンダーを選択]**：カスタム。

   * **[!UICONTROL タイプ]**：インバウンド。

   * **[!UICONTROL API 資格情報]**：[以前に設定した API 資格情報](sms-configuration-custom.md#api-credential)をドロップダウンから選択します。

   * **[!UICONTROL 送信者電話番号]**：コミュニケーションに使用する送信者の電話番号を入力します。

     ![](assets/webhook-inbound.png){zoomable="yes"}

1. 「![](assets/do-not-localize/Smock_Add_18_N.svg)」をクリックしてキーワードカテゴリを追加し、SMS プロバイダーに応じて設定します。

   * **[!UICONTROL 受信キーワードカテゴリ]**：キーワードカテゴリを「**[!UICONTROL オプトイン]**」、「**[!UICONTROL オプトアウト]**」、「**[!UICONTROL ダブルオプトイン]**」、「**[!UICONTROL ヘルプ]**」または「**[!UICONTROL カスタム]**」から選択します。

   * **[!UICONTROL キーワードを入力]**：メッセージを自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。「![](assets/do-not-localize/Smock_Add_18_N.svg)」をクリックして複数のキーワードを追加します。

     **[!UICONTROL カスタムキーワード]**&#x200B;の場合は、ジャーニー内のバッチベースのアクションに同意以外の関連キーワードを使用します。

   * **[!UICONTROL 返信メッセージ]**：自動的に送信されるカスタム応答をドロップダウンから選択します。

   * **[!UICONTROL ファジーオプトアウト]**：このオプションを有効にすると、ニアマッチオプトアウトキーワードが検出された場合に自動返信が送信されます。

   ![](assets/sms_byo_6.png){zoomable="yes"}

1. 受信メッセージが設定されたキーワードまたはカテゴリに一致しない場合に自動的に送信される **[!UICONTROL デフォルトの返信メッセージ]** を入力します。

1. 「**[!UICONTROL ペイロードエディターを表示]**」をクリックして、リクエストペイロードを検証およびカスタマイズします。

   プロファイル属性を使用してペイロードを動的にパーソナライズし、ビルトインのヘルパー関数を使用して、処理と応答の生成のために正確なデータを確実に送信できます。

1. Webhook の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL フィードバック]** Webhook を作成するには、上記と同じ手順に従い、Webhook **[!UICONTROL タイプ]** として **[!UICONTROL フィードバック]** を選択します。

1. **[!UICONTROL Webhook]** メニューから、既存の Webhook を編集または削除したり、**[!UICONTROL Webhook URL]** にアクセスしてコピーして SMS プロバイダーと統合したりできます。

   ![](assets/sms_byo_7.png){zoomable="yes"}

Webhook の設定を作成および設定した後、SMS メッセージ用に [&#x200B; チャネル設定 &#x200B;](sms-configuration-surface.md) を作成する必要があります。

設定が完了すると、メッセージオーサリング、パーソナライゼーション、リンクトラッキング、レポートなど、すべての標準のチャネル機能を活用できます。

>[!TAB Infobip]

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;に移動し、**[!UICONTROL SMS 設定]**&#x200B;の下にある **[!UICONTROL SMS Webhook]** メニューを選択して、「**[!UICONTROL Webhook を作成]**」ボタンをクリックします。

   ![](assets/sms_byo_5.png){zoomable="yes"}

1. 以下で説明するように、Webhook 設定を指定します。

   * **[!UICONTROL 名前]**：Webhook の名前を入力します。

   * **[!UICONTROL SMS ベンダーを選択]**:Infobip。

   * **[!UICONTROL タイプ]**：インバウンド。

   * **[!UICONTROL API 資格情報]**：[以前に設定した API 資格情報](sms-configuration-infobip.md#api-credential)をドロップダウンから選択します。

   * **[!UICONTROL 送信者電話番号]**：コミュニケーションに使用する送信者の電話番号を入力します。

     ![](assets/webhook-infobip-1.png){zoomable="yes"}

1. 「![](assets/do-not-localize/Smock_Add_18_N.svg)」をクリックしてキーワードカテゴリを追加し、SMS プロバイダーに応じて設定します。

   * **[!UICONTROL 受信キーワードカテゴリ]**：キーワードカテゴリを「**[!UICONTROL オプトイン]**」、「**[!UICONTROL オプトアウト]**」、「**[!UICONTROL ダブルオプトイン]**」、「**[!UICONTROL ヘルプ]**」または「**[!UICONTROL カスタム]**」から選択します。

   * **[!UICONTROL キーワードを入力]**：メッセージを自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。「![](assets/do-not-localize/Smock_Add_18_N.svg)」をクリックして複数のキーワードを追加します。

     **[!UICONTROL カスタムキーワード]**&#x200B;の場合は、ジャーニー内のバッチベースのアクションに同意以外の関連キーワードを使用します。

   * **[!UICONTROL 返信メッセージ]**：自動的に送信されるカスタム応答をドロップダウンから選択します。

   * **[!UICONTROL ファジーオプトアウト]**：このオプションを有効にすると、ニアマッチオプトアウトキーワードが検出された場合に自動返信が送信されます。

   ![](assets/webhook-infobip-2.png){zoomable="yes"}

1. 受信メッセージが設定されたキーワードまたはカテゴリに一致しない場合に自動的に送信される **[!UICONTROL デフォルトの返信メッセージ]** を入力します。

1. Webhook の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL フィードバック]** Webhook を作成するには、上記と同じ手順に従い、Webhook **[!UICONTROL タイプ]** として **[!UICONTROL フィードバック]** を選択します。

1. **[!UICONTROL Webhook]** メニューから、既存の Webhook を編集または削除したり、**[!UICONTROL Webhook URL]** にアクセスしてコピーして SMS プロバイダーと統合したりできます。

   ![](assets/sms_byo_7.png){zoomable="yes"}

Webhook のインバウンド設定を作成し指定したら、SMS メッセージ用の[チャネル設定](sms-configuration-surface.md)を作成する必要があります。

設定が完了すると、メッセージオーサリング、パーソナライゼーション、リンクトラッキング、レポートなど、すべての標準のチャネル機能を活用できます。

>[!TAB  シンチ ]

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;に移動し、**[!UICONTROL SMS 設定]**&#x200B;の下にある **[!UICONTROL SMS Webhook]** メニューを選択して、「**[!UICONTROL Webhook を作成]**」ボタンをクリックします。

   ![](assets/sms_byo_5.png){zoomable="yes"}

1. 以下で説明するように、Webhook 設定を指定します。

   * **[!UICONTROL 名前]**：Webhook の名前を入力します。

   * **[!UICONTROL SMS ベンダーを選択]**:Sinch。

   * **[!UICONTROL タイプ]**：インバウンド。

   * **[!UICONTROL API 資格情報]**：[以前に設定した API 資格情報](sms-configuration-sinch.md#create-api)をドロップダウンから選択します。

   * **[!UICONTROL 送信者電話番号]**：コミュニケーションに使用する送信者の電話番号を入力します。

     ![](assets/webhook-sinch-1.png){zoomable="yes"}

1. 「![](assets/do-not-localize/Smock_Add_18_N.svg)」をクリックしてキーワードカテゴリを追加し、SMS プロバイダーに応じて設定します。

   * **[!UICONTROL 受信キーワードカテゴリ]**：キーワードカテゴリを「**[!UICONTROL オプトイン]**」、「**[!UICONTROL オプトアウト]**」、「**[!UICONTROL ダブルオプトイン]**」、「**[!UICONTROL ヘルプ]**」または「**[!UICONTROL カスタム]**」から選択します。

   * **[!UICONTROL キーワードを入力]**：メッセージを自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。「![](assets/do-not-localize/Smock_Add_18_N.svg)」をクリックして複数のキーワードを追加します。

     **[!UICONTROL カスタムキーワード]**&#x200B;の場合は、ジャーニー内のバッチベースのアクションに同意以外の関連キーワードを使用します。

   * **[!UICONTROL 返信メッセージ]**：自動的に送信されるカスタム応答をドロップダウンから選択します。

   * **[!UICONTROL ファジーオプトアウト]**：このオプションを有効にすると、ニアマッチオプトアウトキーワードが検出された場合に自動返信が送信されます。

   ![](assets/webhook-sinch-2.png){zoomable="yes"}

1. 受信メッセージが設定されたキーワードまたはカテゴリに一致しない場合に自動的に送信される **[!UICONTROL デフォルトの返信メッセージ]** を入力します。

1. Webhook の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL Webhook]** メニューで、![ごみ箱アイコン](assets/do-not-localize/Smock_Delete_18_N.svg)をクリックして、Webhook を削除します。

1. 既存の設定を変更するには、目的の Webhook を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

1. 以前に送信した **[!UICONTROL Webhook]** から新しい **[!UICONTROL Webhook URL]** にアクセスしてコピーします。

   ![](assets/sms_byo_7.png){zoomable="yes"}

Webhook のインバウンド設定を作成し指定したら、SMS メッセージ用の[チャネル設定](sms-configuration-surface.md)を作成する必要があります。

設定が完了すると、メッセージオーサリング、パーソナライゼーション、リンクトラッキング、レポートなど、すべての標準のチャネル機能を活用できます。

<!--
>[!TAB Twilio]

1. In the left rail, navigate to **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]**, select the **[!UICONTROL SMS Webhooks]** menu under **[!UICONTROL SMS settings]**, and click the **[!UICONTROL Create Webhook]** button.

    ![](assets/sms_byo_5.png){zoomable="yes"}

1. Configure your Webhook Settings, as detailed below:

    * **[!UICONTROL Name]**: Enter a name for your Webhook.

    * **[!UICONTROL Select SMS vendor]**: Twilio.

    * **[!UICONTROL Type]**: Inbound.

    * **[!UICONTROL API credentials]**: Choose from the drop-down you [previously configured API credentials](sms-configuration-twilio.md#create-api).

    * **[!UICONTROL Sender Phone Number ​]**: Enter the Sender phone number ​you want to use for your communications.
        
1. Click ![](assets/do-not-localize/Smock_Add_18_N.svg) to add your keywords categories, then, configure them depending on your SMS provider:

    * **[!UICONTROL Inbound Keyword Category]**: Choose your keyword categories either **[!UICONTROL Opt-In]**, **[!UICONTROL Opt-Out]**, **[!UICONTROL Double Opt-In]**, **[!UICONTROL Help]** or **[!UICONTROL Custom]**. 

    * **[!UICONTROL Enter a keyword]**: Enter the default or custom keywords that will automatically trigger your message. Click ![](assets/do-not-localize/Smock_Add_18_N.svg) to add multiple keywords.

        For **[!UICONTROL Custom keyword]**, use non-consent–related keywords for batch-based actions within a journey.

    * **[!UICONTROL Reply Message]**: Select from the drop-down the custom response that is automatically sent.

    * **[!UICONTROL Fuzzy Opt-out]**: Enable this option to send an automatic reply when a near-match opt-out keyword is detected.

1. Enter a **[!UICONTROL Default Reply Message]** automatically sent when an inbound message does not match any configured keyword or category.

1. Click **[!UICONTROL Submit]** when you finished the configuration of your Webhook.

1. In the **[!UICONTROL Webhooks]** menu, click the ![bin icon](assets/do-not-localize/Smock_Delete_18_N.svg) to delete your Webhook.

1. To modify existing configuration, locate the desired Webhook and click the **[!UICONTROL Edit]** option to make the necessary changes.

1. Access and copy your new **[!UICONTROL Webhook URL]** from your previously submitted **[!UICONTROL Webhook]**.

After creating and configuring the inbound settings for the Webhook, you now need to create a [channel configuration](sms-configuration-surface.md) for SMS messages. 

Once configured, you can leverage all out-of-the-box channel capabilities such as message authoring, personalization, link tracking, and reporting.
-->

>[!ENDTABS]


## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3459089?captions=jpn)

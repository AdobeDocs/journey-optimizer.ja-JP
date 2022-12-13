---
solution: Journey Optimizer
product: journey optimizer
title: 旅オプティマイザーのアーカイブサポート
description: メッセージをアーカイブする方法について説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 186a5044-80d5-4633-a7a7-133e155c5e9f
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 0%

---

# アーカイブのサポート {#archiving-support}

## メッセージをアーカイブする方法 {#about-archiving}

HIPAA のような規制については、個人に送信される [!DNL Journey Optimizer] メッセージをアーカイブする方法を提供する必要があります。 実際に、お客様が苦情を提起した場合は、送信されたメッセージのコピーを取得して確認することができます。

* 電子メールチャンネルには、 [!DNL Journey Optimizer] BCC 電子メール機能が組み込まれています。 [詳細情報](#bcc-email)

* Additionnaly では、すべてのチャネルについて、パーソナライズされていないメッセージテンプレートの詳細を含む、エンティティデータセット **の「Template」フィールド** を使用できます。このフィールドを使用してデータセットを書き出し、メタデータを保存します。メッセージの送信者、宛先、タイミング パーソナライズされたデータは書き出されません。テンプレート (メッセージのフォーマットと構造) が考慮されます。 [詳細情報](../data/datasets-query-examples.md#entity-dataset)

>[!NOTE]
>
>[!DNL Journey Optimizer] は、SMS アーカイブ要件についてはサポートしていません。 専用のアーカイブサポートについては、SMS ベンダー (Synch または Twilio) を使用して作業してください。

## 電子メールに BCC を使用する方法 {#bcc-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_bcc"
>title="BCC 電子メールアドレスの定義"
>abstract="送信された電子メールを BCC 受信ボックスに送信するには、そのコピーを保存しておくことができます。 送信されたすべての電子メールが BCC アドレスにブラインドコピーされるように、任意の電子メールアドレスを入力します。 BCC アドレスドメインは、Adobe に委任されているサブドメインと同じであってはなりません。 この機能はオプションです。"

によって [!DNL Journey Optimizer] 送信された電子メールを BCC 受信ボックスに送信することもできます。 このオプション機能により、コンプライアンスやアーカイブの目的でユーザーに送信する電子メール通信のコピーを保存しておくことができます。 このような場合は、宛先には表示されません。

### BCC 電子メールの有効化 {#enable-bcc}

このオプションを有効 **[!UICONTROL BCC email]** にするには、チャネルサーフェス [&#128279;](channel-surfaces.md) の  専用フィールド (メッセージプリセット) に、選択した電子メールアドレスを入力します。Adobe に委任されたサブドメインで定義されている電子メールアドレスを除き、どの外部アドレスも正しい形式で指定できます。 例えば、marketing.luma.com *サブドメインを Adobe に委任* した場合、abc@marketing.luma.com *のような* アドレスは禁止されます。

>[!CAUTION]
>
>1つの BCC 電子メールアドレスのみを定義することができます。 BCC アドレスに、現在のチャンネルサーフェスを使用して送信されたすべての電子メールを格納するのに十分な受信容量があることを確認してください。
>
>この節で [ は、その他の推奨事項について説明 ](#bcc-recommendations-limitations) します。

>[!NOTE]
>
>ヘルスケアシールドアドオンオファリングを購入した場合は、BCC addresse の ISP が TLS 1.2 プロトコルをサポートすることを確認する必要があります。

![](assets/preset-bcc.png)

このサーフェスを使用しているすべての電子メールメッセージは、入力した BCC 電子メールアドレスにブラインドコピーされます。 その後、外部システムを使用して処理およびアーカイブすることができます。

>[!CAUTION]
>
>BCC 機能の使用については、ライセンス供与されているメッセージ数に基づいて計算されます。 そのため、アーカイブする重要な通信に使用されているサーフェスでのみこの機能を有効にする必要があります。 ライセンスされるボリュームについては、契約を確認してください。

BCC 電子メールアドレスの設定は、ただちにサーフェスレベルで保存および処理されます。 このサーフェスを使用して新しいメッセージを作成すると、BCC 電子メールアドレスが自動的に表示されます。

![](assets/preset-bcc-in-msg.png)

ただし、ここで [&#128279;](../email/email-settings.md) 説明している  ような情報を送信するために BCC アドレスが選択されます。

### 推奨事項と制限事項 {#bcc-recommendations-limitations}

* プライバシーに関するコンプライアンスを確保するために、BCC 電子メールは、セキュリティで保護された個人情報 (PII) を保管できるアーカイブシステムによって処理する必要があります。

* メッセージには、個人を特定できる情報 (PII) などの重要な機密データが含まれている場合があるので、BCC アドレスが正しいことを確認し、メッセージへのアクセスを保護する必要があります。

* BCC に使用されている受信ボックスは、スペースや配信に適した適切な管理を行う必要があります。 受信ボックスがバウンスを返した場合は、受信されなかったり、アーカイブされなかったりすることがあります。

* メッセージは、宛先の受信者より先に BCC 電子メールアドレスに配信される場合があります。 BCC メッセージは、元のメッセージがバウンス [&#128279;](../reports/suppression-list.md#delivery-failures) された  としても送信される場合もあります。

   <!--OR: Only successfully sent emails are taken in account. [Bounces](../reports/suppression-list.md#delivery-failures) are not. TO CHECK -->

* BCC アドレスに送信された電子メールを開いたりクリックしたりすることはありません。これは、送信解析から開いてクリックした総数によって異なります。これにより、レポート [&#128279;](../reports/global-report.md) の  計算が失敗する可能性があります。

* BCC 受信ボックスでは、メッセージにスパムというマークを付けないでください。これは、このアドレスに送信される他の電子メールすべてに影響します。


>[!CAUTION]
>
>BCC アドレスに送信される電子メールの購読解除リンクをクリックしないと、対応する受信者の購読はただちに解除されます。

### GDPR コンプライアンス {#gdpr-compliance}

GDPR のような規制により、データの主題によっては、いつでも同意を修正できるようにすることができます。 転送オプティマイザーによって送信される BCC 電子メールには、個人を特定できる情報 (PII) が含まれているため、を編集して、 **[!UICONTROL CJM Email BCC Feedback Event Schema]** これらの pii を GDPR や同様の規制に適合させることができます。

これを行うには、次の手順を実行します。

1. &#x200B;> **[!UICONTROL Schemas]** > **[!UICONTROL Browse]** に **[!UICONTROL Data management]** 移動し、「」を選択 **[!UICONTROL CJM Email BCC Feedback Event Schema]** します。

   ![](assets/preset-bcc-schema.png)

1. クリックすると展開 **[!UICONTROL _experience]** 、 **[!UICONTROL customerJourneyManagment]** 次 **[!UICONTROL secondaryRecipientDetail]** のようになります。

1. を選択 **[!UICONTROL originalRecipientAddress]** します。

1. **[!UICONTROL Field properties]**&#x200B;右側ので、チェックボックスを下に **[!UICONTROL Identity]** スクロールします。

1. このオプションを選択し、さらに「」を選択 **[!UICONTROL Primary identity]** します。

1. ドロップダウンリストから名前空間を選択します。

   ![](assets/preset-bcc-schema-identity.png)

1. をクリック **[!UICONTROL Apply]** します。

>[!NOTE]
>
>プライバシーの管理について詳しくは、『経験プラットフォームマニュアル [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"} の「プライバシーの管理」を参照してください。

### BCC レポートデータ {#bcc-reporting}

「BCC」に同様のレポートは、メッセージレポートには表示されません。 ただし、インフォメーションはという **[!UICONTROL AJO BCC Feedback Event Dataset]** システムデータセットに保存されます。 このデータセットに対してクエリーを実行すると、デバッグ目的で使用する有益な情報を取得することができます。

このデータセットには、ユーザーインターフェイスを使用してアクセスできます。 > **[!UICONTROL Datasets]** > **[!UICONTROL Browse]** を選択 **[!UICONTROL Data management]** し、フィルターを使用して、 **[!UICONTROL Show system datasets]** システムによって生成されたデータセットを表示します。このセクション [&#128279;](../data/get-started-datasets.md#access-datasets) のデータセットにアクセスする方法について詳しくは  、こちらを参照してください。

![](assets/preset-bcc-dataset.png)

このデータセットに対してクエリーを実行するには、Adobe Experience Platform Query サービス [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target="_blank"}  によっ  て提供されるクエリーエディターを使用できます。このファイルにアクセスするには、「> **[!UICONTROL Queries]** 」を選択 **[!UICONTROL Data management]** し、をクリック **[!UICONTROL Create query]** します。[詳細情報](../data/get-started-queries.md)

![](assets/preset-bcc-queries.png)

検索する情報の種類に応じて、次のクエリーを実行することができます。

1. 以下の他のすべてのクエリについては、旅のアクション ID が必要になります。 このクエリーを実行すると、過去2日間の特定の旅バージョン ID に関連付けられたすべてのアクション Id が取得されます。

    ```
    SELECT
    DISTINCT
    CAST(TIMESTAMP AS DATE) AS EventTime,
    _experience.journeyOrchestration.stepEvents.journeyVersionID,
    _experience.journeyOrchestration.stepEvents.actionName, 
    _experience.journeyOrchestration.stepEvents.actionID 
    FROM journey_step_events 
    WHERE 
    _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND 
    _experience.journeyOrchestration.stepEvents.actionID is not NULL AND 
    TIMESTAMP > NOW() - INTERVAL '2' DAY 
    ORDER BY EventTime DESC;
    ```

   >[!NOTE]
   >
   >パラメーターを取得 `<journey version id>` するには、対応 [ ](../building-journeys/journey.md#journey-versions) **[!UICONTROL Journey management]** する > **[!UICONTROL Journeys]** メニューを選択します。 旅のバージョン ID は、web ブラウザーに表示される URL の末尾に表示されます。
   >
   >![](assets/preset-bcc-action-id.png)

1. このクエリーを実行すると、特定のユーザーを対象とする特定のメッセージに対して生成されたすべてのメッセージフィードバックイベント (特にフィードバックステータス) を、次の2日に取得できます。

    ```
    SELECT  
    _experience.customerJourneyManagement.messageExecution.journeyVersionID AS JourneyVersionID, 
    _experience.customerJourneyManagement.messageExecution.journeyActionID AS JourneyActionID, 
    timestamp AS EventTime, 
    _experience.customerJourneyManagement.emailChannelContext.address AS RecipientAddress, 
    _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus AS FeedbackStatus,
    CASE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus
        WHEN 'sent' THEN 'Sent'
        WHEN 'delay' THEN 'Retry'
        WHEN 'out_of_band' THEN 'Bounce' 
        WHEN 'bounce' THEN 'Bounce'
    END AS FeedbackStatusCategory
    FROM cjm_message_feedback_event_dataset 
    WHERE  
        timestamp > now() - INTERVAL '2' day  AND
        _experience.customerJourneyManagement.messageExecution.journeyVersionID = '<journey version id>' AND 
        _experience.customerJourneyManagement.messageExecution.journeyActionID = '<journey action id>' AND  
        _experience.customerJourneyManagement.emailChannelContext.address = '<recipient email address>'
        ORDER BY EventTime DESC;
    ```
                                            
   >[!NOTE]
   >
   >パラメーターを取得 `<journey action id>` するには、旅のバージョン id を使用して、上で説明した最初のクエリーを実行します。 `<recipient email address>`このパラメーターには、対象となる受信者の電子メールアドレスを指定します。

1. このクエリーを実行すると、特定のユーザーを対象としていた特定のメッセージについて、最後の2日間に、すべての BCC メッセージについてのフィードバックイベントを取得することができます。

   ```
   SELECT   
   _experience.customerJourneyManagement.messageExecution.journeyVersionID AS JourneyVersionID, 
   _experience.customerJourneyManagement.messageExecution.journeyActionID AS JourneyActionID, 
   _experience.customerJourneyManagement.emailChannelContext.address AS BccEmailAddress,
   timestamp AS EventTime, 
   _experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress AS RecipientAddress, 
   _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus AS FeedbackStatus,
   CASE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus
               WHEN 'sent' THEN 'Sent'
               WHEN 'delay' THEN 'Retry'
               WHEN 'out_of_band' THEN 'Bounce' 
               WHEN 'bounce' THEN 'Bounce'
           END AS FeedbackStatusCategory 
   FROM ajo_bcc_feedback_event_dataset  
   WHERE  
   timestamp > now() - INTERVAL '2' day  AND
   _experience.customerJourneyManagement.messageExecution.journeyVersionID = '<journey version id>' AND 
   _experience.customerJourneyManagement.messageExecution.journeyActionID = '<journeyaction id>' AND 
   _experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress = '<recipient email address>'
   ORDER BY EventTime DESC;
   ```

1. このクエリーを実行すると、メッセージが受信されていない受信者のアドレスがすべて取得されます。 BCC 項目は、最後の30日以内に存在します。

   ```
    SELECT
        DISTINCT 
    bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress AS RecipientAddressesNotRecievedMessage
    FROM ajo_bcc_feedback_event_dataset bcc
    LEFT JOIN cjm_message_feedback_event_dataset mfe
    ON 
   bcc._experience.customerJourneyManagement.messageExecution.journeyVersionID =
            mfe._experience.customerJourneyManagement.messageExecution.journeyVersionID AND    bcc._experience.customerJourneyManagement.messageExecution.journeyActionID = mfe._experience.customerJourneyManagement.messageExecution.journeyActionID AND 
   bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress = mfe._experience.customerJourneyManagement.emailChannelContext.address AND
   mfe._experience.customerJourneyManagement.messageExecution.journeyVersionID = '<journey version id>' AND 
   mfe._experience.customerJourneyManagement.messageExecution.journeyActionID = '<journey action id>' AND
   mfe.timestamp > now() - INTERVAL '30' DAY AND
   mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus IN ('bounce', 'out_of_band') 
    WHERE bcc.timestamp > now() - INTERVAL '30' DAY;
   ```

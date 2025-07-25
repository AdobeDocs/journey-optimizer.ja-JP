---
solution: Journey Optimizer
product: journey optimizer
title: WhatsApp チャネルの設定
description: Journey Optimizer で WhatsApp メッセージを送信するように環境を設定する方法について説明します
feature: Whatsapp, Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: d1f40cd8-f311-4df6-b401-8858095cef3e
source-git-commit: 2d80f72d672f0a8ecb345dbd12ee8864785dca14
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 65%

---

# WhatsApp 設定の基本を学ぶ {#whatsapp-config}

>[!BEGINSHADEBOX]

**目次**

* [WhatsApp メッセージの基本を学ぶ](get-started-whatsapp.md)
* **[WhatsApp 設定の基本を学ぶ](whatsapp-configuration.md)**
* [WhatsApp メッセージの作成](create-whatsapp.md)
* [WhatsApp メッセージの確認および送信](send-whatsapp.md)

>[!ENDSHADEBOX]

WhatsApp メッセージを送信する前に、Adobe Journey Optimizer 環境を設定し、WhatsApp アカウントに関連付ける必要があります。これを実行するには、次の手順を実行します。

1. [WhatsApp API 資格情報を作成します](#WhatsApp-credentials)
1. [WhatsApp Webhook の作成](#WhatsApp-webhook)
1. [WhatsApp 設定を作成します](#WhatsApp-configuration)

これらの手順は、Adobe Journey Optimizer [システム管理者](../start/path/administrator.md)が実行する必要があります。

## WhatsApp API 資格情報の作成 {#whatsapp-credentials}

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、API 資格情報を設定します。

   * **API トークン**：API トークンを入力します。詳しくは、[Meta ドキュメント](https://developers.facebook.com/docs/facebook-login/guides/access-tokens/)を参照してください。
   * **ビジネスアカウント ID**：ビジネスポートフォリオに関連する一意の番号を入力します。詳しくは、[Meta ドキュメント](https://www.facebook.com/business/help/1181250022022158?id=180505742745347)を参照してください。

   ![](assets/whatsapp-api.png)

1. 「**[!UICONTROL 続行]**」をクリックします。

1. WhatsApp API 資格情報に接続する&#x200B;**ビジネスアカウント**&#x200B;を選択します。

   ![](assets/whatsapp-api-2.png)

1. Whatsapp メッセージの送信に使用する **送信者名** を選択します。

1. 電話番号の設定は自動的に入力されます。

   * **品質評価**：過去 24 時間に送信されたメッセージに関する顧客のフィードバックを反映します。
      * 緑色：高品質
      * 黄色：中品質
      * 赤色：低品質

     詳しくは、[品質評価](https://www.facebook.com/business/help/766346674749731#)を参照してください。

   * **スループット**：電話番号がメッセージを送信できる速度を示します。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 資格情報を作成および設定したら、WhatsApp メッセージ用のチャネル設定を作成する必要があります。[詳細情報](#whatsapp-configuration)

## Webhook の作成 {#WhatsApp-webhook}

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_inbound_keyword_category"
>title="受信キーワードカテゴリ"
>abstract="<b> オプトイン </b>：ユーザーが購読すると、定義した自動応答を送信します。 <br/><b> オプトアウト </b>：ユーザーが登録解除すると、定義した自動応答を送信します。 <br/><b> ヘルプ </b>：ユーザーがヘルプまたはサポートをリクエストしたときに、定義済みの自動応答を送信します。 <br/><b> デフォルト </b>：一致するキーワードがない場合にフォールバック自動応答を送信します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_inbound_keyword"
>title="キーワードを入力"
>abstract= "You can define keywords to trigger specific auto-responses, such as for Opt-In, Opt-Out, Help, or Default, based on what users text. Keywords are not case-sensitive, e.g., stop and STOP are treated the same."

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_webhook_url"
>title=" コールバック URL"
>abstract="このオブジェクトの検証リクエストと Webhook 通知は、指定した URL に送信されます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_whatsapp_webhook_verify_token"
>title="トークンの検証"
>abstract="Meta がエコーバックするトークンは、検証プロセス中にコールバック URL を確認して検証するために使用されます。"

>[!NOTE]
>
>オプトインまたはオプトアウトのキーワードが指定されていない場合、標準の同意メッセージは有効になりません。

WhatsApp API 認証情報と [Meta Webhook](https://developers.facebook.com/docs/whatsapp/webhooks/) が正常に作成されたら、次の手順は Webhook を作成してインバウンド設定を設定することです。

1. 左側のレールで、**[!UICONTROL 管理]**`>`**[!UICONTROL チャネル]** に移動し、**[!UICONTROL WhatsApp 設定]** の下にある **[!UICONTROL WhatsApp Webhook]** メニューを選択して、**[!UICONTROL Webhook を作成]** ボタンをクリックします。

1. Webhook の [!UICONTROL &#x200B; 名前 &#x200B;] を入力します。

1. ドロップダウンから、以前に作成した [API 資格情報 ](#whatsapp-credentials) を選択します。

1. 「![ 追加 ](assets/do-not-localize/Smock_AddCircle_18_N.svg)」をクリックして、次のような **[!UICONTROL 受信キーワードカテゴリ]** の設定を開始します。

   * **[!UICONTROL オプトインキーワード]**
   * **[!UICONTROL オプトアウトキーワード]**
   * **[!UICONTROL ヘルプキーワード]**

1. **[!UICONTROL キーワード]** を入力します。

   複数のキーワードを追加するには、「![ 追加 ](assets/do-not-localize/Smock_AddCircle_18_N.svg)」をクリックします。

1. 設定したキーワードを受信したときに送信される **[!UICONTROL 返信メッセージ]** を指定します。

<!--
1. Click **[!UICONTROL View payload editor]** to validate and customize your request payloads. 
    
    You can dynamically personalize your payload using profile attributes, and ensure accurate data is sent for processing and response generation with the help of built-in helper functions.
-->

1. WhatsApp Webhook の設定が完了したら、**[!UICONTROL 送信]** をクリックします。

1. **[!UICONTROL Webhook]** メニューで ![bin アイコン ](assets/do-not-localize/Smock_Delete_18_N.svg) をクリックして WhatsApp Webhook を削除します。

1. 既存の設定を変更するには、目的の Webhook を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

1. 以前に送信した **[!UICONTROL WhatsApp Webhook]** から新しい **[!UICONTROL Webhook URL]** にアクセスしてコピーします。

Webhook が設定されたので、WhatsApp 設定を作成できます。

## WhatsApp 設定の作成 {#whatsapp-configuration}

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL 一般設定]**／**[!UICONTROL チャネル設定]**&#x200B;を選択します。「**[!UICONTROL チャネル設定を作成]**」ボタンをクリックします。

   ![](assets/whatsapp-config-1.png)

1. 設定の名前と説明（オプション）を入力し、WhatsApp チャネルを選択します。

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. チャネルとして **[!DNL WhatsApp]** を選択します。

   ![](assets/whatsapp-config-2.png)

1. この設定を使用してメッセージに同意ポリシーを関連付けるには、**[!UICONTROL マーケティングアクション]**&#x200B;を選択します。顧客の意向に従うために、そのマーケティングアクションに関連付けられているすべての同意ポリシーが活用されます。詳細情報

1. 以前に作成した **[!UICONTROL WhatsApp API 設定]**&#x200B;を選択します。

   ![](assets/whatsapp-config-3.png)

1. コミュニケーションに使用する「**[!UICONTROL 送信者番号]**」を入力します。

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。なお、チャネル設定をドラフトとして保存し、後で設定を再開することもできます。

1. チャネル設定が作成されると、リストに「**[!UICONTROL 処理中]**」のステータスで表示されます。

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](../configuration/channel-surfaces.md)を参照してください。

1. チェックが正常に完了すると、チャネル設定のステータスが「**[!UICONTROL アクティブ]**」になります。メッセージの配信に使用する準備が整いました。

設定が完了すると、メッセージオーサリング、パーソナライゼーション、リンクトラッキング、レポートなど、すべての標準のチャネル機能を活用できます。

これで、Journey Optimizer で WhatsApp メッセージを送信する準備が整いました。
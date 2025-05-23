---
solution: Journey Optimizer
product: journey optimizer
title: カスタムプロバイダーの設定
description: カスタムプロバイダーを使用して Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: fd713864-96b9-4687-91bd-84e3533273ff
source-git-commit: 37313ca8a9527c934d8aeaf265e9674219726636
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 21%

---

# カスタム SMS プロバイダーの設定 {#sms-configuration-custom}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_provider_url"
>title="プロバイダー URL"
>abstract="接続する予定の外部 API の URL を指定します。この URL は、API の機能にアクセスするためのエンドポイントとして機能します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_header_parameters"
>title="ヘッダーパラメーター"
>abstract="適切な認証、コンテンツの書式設定、効果的な API 通信を有効にするために、追加ヘッダーのラベル、タイプ、値を指定します。 "

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_provider_payload"
>title="プロバイダーペイロード"
>abstract="処理と応答の生成用に正しいデータの送信を確保するために、リクエストペイロードを指定します。"

この機能を使用すると、独自の SMS プロバイダーを統合および設定でき、デフォルトのプロバイダー（Sinch、Twilio、Infobip）を超える柔軟性を提供できます。 これにより、シームレスな SMS オーサリング、配信、レポートおよび同意管理が可能になります。

SMS のカスタムプロバイダー設定を使用すると、Journey Optimizer内で直接カスタム SMS プロバイダーを設定し、動的メッセージ用の高度なペイロードカスタマイズを使用し、同意の環境設定（オプトイン/オプトアウト）を管理してコンプライアンスを確保できます。

カスタム SMS プロバイダーを設定するには、次の手順に従います。

1. [API 認証情報の作成](#api-credential)
1. [Webhook の作成](#webhook)
1. [チャネル設定の作成](sms-configuration-surface.md)
1. [SMS チャネルアクションを使用したジャーニーまたはキャンペーンの作成](create-sms.md)

## API 認証情報の作成 {#api-credential}

アドビで標準で使用できないカスタムプロバイダー（Sinch、Infobip、Twilio など）を使用して Journey Optimizer でメッセージを送信するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**`>`**[!UICONTROL チャネル]** に移動し、**[!UICONTROL SMS 設定]** の下の **[!UICONTROL API 資格情報]** メニューを選択して、「**[!UICONTROL 新しい API 資格情報の作成]**」ボタンをクリックします。

   ![](assets/sms_byo_1.png)

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：カスタム。

   * **[!UICONTROL 名前]**:API 資格情報の名前を入力します。

   * **[!UICONTROL プロバイダーの AppId]**:SMS プロバイダーから提供されたアプリケーション ID を入力します。

   * **[!UICONTROL プロバイダー名]**:SMS プロバイダーの名前を入力します。

   * **[!UICONTROL プロバイダー URL]**:SMS プロバイダーの URL を入力します。

   * **[!UICONTROL 認証タイプ&#x200B;]**：認証タイプを選択し、選択した認証方法に基づいて [ 対応するフィールドに入力 ](#auth-options) します。

     ![](assets/sms-byop.png)

1. 「**[!UICONTROL ヘッダー]**」セクションで「**[!UICONTROL 新しいパラメーターを追加]**」をクリックし、外部サービスに送信されるリクエストメッセージの HTTP ヘッダーを指定します。

   **Content-Type** および **Charset** ヘッダーフィールドはデフォルトで設定され、削除できません。

   ![](assets/sms_byo_2.png)

1. **[!UICONTROL プロバイダーペイロード]** を追加して、リクエストペイロードを検証およびカスタマイズします。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]** メニューで ![bin アイコン ](assets/do-not-localize/Smock_Delete_18_N.svg) をクリックして、API 資格情報を削除します。

   ![](assets/sms_byo_3.png)

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

   ![](assets/sms_byo_4.png)

API 認証情報を作成して設定した後、SMS メッセージの [Webhook の受信設定 ](#webhook) を設定する必要があります。

### カスタム SMS プロバイダーの認証オプション {#auth-options}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_auth_type"
>title="認証タイプ"
>abstract="API へのアクセスに必要な認証方法を指定します。これにより、外部サービスとの安全で承認済みの通信が確保されます。"

>[!BEGINTABS]

>[!TAB API キー ]

API 認証情報が作成されたら、API キー認証に必要な次のフィールドに入力します。

* **[!UICONTROL &#x200B; 名前 &#x200B;]**&#x200B;:API キー設定の名前を入力します。
* **[!UICONTROL API トークン &#x200B;]**&#x200B;:SMS プロバイダーから提供された API トークンを入力します。

![](assets/sms-byop-api-key.png)

>[!TAB MAC認証 ]

API 認証情報を作成したら、MAC認証に必要な次のフィールドに入力します。

* **[!UICONTROL &#x200B; 名前 &#x200B;]**&#x200B;:MAC認証設定の名前を入力します。
* **[!UICONTROL API トークン &#x200B;]**&#x200B;:SMS プロバイダーから提供された API トークンを入力します。
* **[!UICONTROL API 秘密鍵]**:SMS プロバイダーから提供された API 秘密鍵を入力します。 このキーは、安全な通信のためのMAC（Message Authentication Code）を生成するために使用されます。
* **[!UICONTROL Mac Authorization Hash Format]**: MAC認証のハッシュ形式を選択します。

![](assets/sms-byop-mac.png)

>[!TAB OAuth 認証 ]

API 認証情報が作成されたら、OAuth 認証に必要な次のフィールドに入力します。

* **[!UICONTROL &#x200B; 名前 &#x200B;]**&#x200B;:OAuth 認証設定の名前を入力します。

* **[!UICONTROL API トークン &#x200B;]**&#x200B;:SMS プロバイダーから提供された API トークンを入力します。

* **[!UICONTROL OAuth URL]**&#x200B;:OAuth トークンを取得する URL を入力します。

* **[!UICONTROL OAuth Body]**&#x200B;:`grant_type`、`client_id`、`client_secret` などのパラメーターを含む、JSON 形式の OAuth リクエスト本文を指定します。

![](assets/sms-byop-oauth.png)

>[!TAB JWT 認証 ]

API 資格情報を作成したら、JWT 認証に必要な次のフィールドに入力します。

* **[!UICONTROL &#x200B; 名前 &#x200B;]**&#x200B;:JWT 認証設定の名前を入力します。

* **[!UICONTROL API トークン &#x200B;]**&#x200B;:SMS プロバイダーから提供された API トークンを入力します。

* **[!UICONTROL JWT ペイロード &#x200B;]**&#x200B;：発行者、件名、オーディエンス、有効期限など、JWT に必要なクレームを含む JSON ペイロードを入力します。

![](assets/sms-byop-jwt.png)

>[!ENDTABS]

## Webhook の作成 {#webhook}

>[!BEGINSHADEBOX]

オプトインまたはオプトアウトのキーワードが指定されない場合、ユーザーのプライバシーを尊重するために、標準の同意メッセージが使用されます。 カスタムキーワードを追加すると、デフォルトが自動的に上書きされます。

**デフォルトのキーワード：**

* **オプトイン**：購読、はい、停止解除、開始、続行、再開、開始
* **オプトアウト**：停止、終了、キャンセル、終了、登録解除、いいえ
* **ヘルプ**: ヘルプ

>[!ENDSHADEBOX]

API 資格情報が正常に作成されたら、次の手順では Webhook を作成してインバウンド設定を指定します。 この設定により、システムが受信データまたはメッセージを適切に受信および処理できるようになります。

1. 左側のレールで、**[!UICONTROL 管理]**`>`**[!UICONTROL チャネル]** に移動し、**[!UICONTROL SMS 設定]** の下の **[!UICONTROL SMS Webhook]** メニューを選択し、**[!UICONTROL Webhook を作成]** ボタンをクリックします。

   ![](assets/sms_byo_5.png)

1. 以下に説明するように、Webhook を設定します。

   * **[!UICONTROL 名前]**:Webhook の名前を入力します。

   * **[!UICONTROL SMS ベンダーを選択]**：カスタム。

   * **[!UICONTROL API 資格情報を選択]**:（以前に設定した API 資格情報 [ ドロップダウンから選択 ](#api-credential) ます。

   * **[!UICONTROL オプトインキーワード]**：オプトインメッセージを自動的にトリガーにするデフォルトまたはカスタムのキーワードを入力します。 複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL オプトインメッセージ]**：オプトインメッセージとして自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL オプトアウトキーワード]**：オプトアウトメッセージを自動的にトリガーにするデフォルトまたはカスタムのキーワードを入力します。 複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL オプトアウトメッセージ]**：オプトアウトメッセージとして自動的に送信されるカスタム応答を入力します。

   ![](assets/sms_byo_6.png)

1. **[!UICONTROL ペイロードエディターを表示]** をクリックして、リクエストペイロードを検証しカスタマイズします。

   プロファイル属性を使用してペイロードを動的にパーソナライズし、組み込みのヘルパー関数を使用して、処理と応答の生成のために正確なデータを確実に送信できます。

1. Webhook の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL Webhook]** メニューで ![bin アイコン ](assets/do-not-localize/Smock_Delete_18_N.svg) をクリックして、Webhook を削除します。

1. 既存の設定を変更するには、目的の Webhook を見つけ、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

1. 以前に送信した **[!UICONTROL Webhook]** から新しい **[!UICONTROL Webhook URL]** にアクセスしてコピーします。

   ![](assets/sms_byo_7.png)

Webhook の受信設定を作成して設定した後、SMS メッセージ用に [ チャネル設定 ](sms-configuration-surface.md) を作成する必要があります。

設定が完了すると、メッセージオーサリング、パーソナライゼーション、リンクトラッキング、レポートなど、すべての標準のチャネル機能を活用できます。

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3431625)


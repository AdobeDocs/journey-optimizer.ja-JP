---
solution: Journey Optimizer
product: journey optimizer
title: カスタムプロバイダーの設定
description: カスタムプロバイダーを使用して Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
badge: label="ベータ版" type="Informative"
role: Admin
level: Intermediate
exl-id: fd713864-96b9-4687-91bd-84e3533273ff
source-git-commit: fc78fcfb0f2ce3616cb8b1df44dda2cfd66262fe
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 34%

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

>[!AVAILABILITY]
>
>カスタムプロバイダーは現在、一部のユーザーのみを対象としたベータ版として提供されています。ベータ版に参加するには、アドビの担当者にお問い合わせください。
>このベータ版では、オプトイン／オプトアウトの同意管理と配信レポートのインバウンドメッセージはサポートされていません。


この機能を使用すると、独自の SMS プロバイダーを統合および設定でき、デフォルトのプロバイダー（Sinch、Twilio、Infobip）を超える柔軟性を提供できます。 これにより、シームレスな SMS オーサリング、配信、レポートおよび同意管理が可能になります。

SMS 用のカスタムプロバイダー設定を使用すると、次のことができます。

* Journey Optimizer内で直接カスタム SMS プロバイダーを設定します。
* 動的メッセージには、高度なペイロードのカスタマイズを使用します。
* 同意環境設定（オプトイン/オプトアウト）を管理して、コンプライアンスを確保します。

## API 認証情報の作成 {#api-credential}

アドビで標準で使用できないカスタムプロバイダー（Sinch、Infobip、Twilio など）を使用して Journey Optimizer でメッセージを送信するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**`>`**[!UICONTROL チャネル]** に移動し、**[!UICONTROL API 資格情報]** メニューを選択して、「**[!UICONTROL 新しい API 資格情報の作成]**」ボタンをクリックします。

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

   プロファイル属性を使用してペイロードを動的にパーソナライズし、組み込みのヘルパー関数を使用して、処理と応答の生成のために正確なデータを確実に送信できます。
<!--
1. Add your **Inbound settings** to determine how your system handles incoming messages and subscriber preferences: 

    * **[!UICONTROL Inbound Webhook URL]**: Specify the endpoint URL where inbound messages (e.g. replies or new messages from users) are sent.
    * **[!UICONTROL Opt-in Keywords]**: Enter the default or custom keywords that will automatically trigger your Opt-In Message. For multiple keywords, use comma-separated values.
    * **[!UICONTROL Opt-in Message]**: Enter the custom response that is automatically sent as your Opt-In Message.
    * **[!UICONTROL Opt-out Keywords]**: Enter the default or custom keywords that will automatically trigger your Opt-Out Message. For multiple keywords, use comma-separated values.
    * **[!UICONTROL Opt-out Message]**: Enter the custom response that is automatically sent as your Opt-Out Message.
-->

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

   ![](assets/sms_byo_3.png)

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

   ![](assets/sms_byo_4.png)

API 資格情報を作成し設定したら、SMS メッセージ用のチャネルサーフェスを作成する必要があります。[詳細情報](sms-configuration-surface.md)

設定が完了すると、メッセージオーサリング、パーソナライゼーション、リンクトラッキング、レポートなど、すべての標準のチャネル機能を活用できます。

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

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3443607?captions=jpn)

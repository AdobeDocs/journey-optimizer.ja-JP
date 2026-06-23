---
solution: Journey Optimizer
product: journey optimizer
title: カスタムプロバイダーの設定
description: Journey Optimizerでカスタムプロバイダーを使用してモバイルメッセージを送信する環境を設定する方法について説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: fd713864-96b9-4687-91bd-84e3533273ff
TQID: https://experienceleague.adobe.com/v5gRCHjcQjn0kXPdtakSZRNlRIA-PVyGpctdn7zwXSI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
subfeature_v2: id: b3b09fe1-10f1-4793-9f6b-1ca0269eebe7id: cf64c7f6-7428-4ae5-b158-8df9771f38f4
source-git-commit: 46131a2626da2c03fc31092cf685cbc73b38bd35
workflow-type: tm+mt
source-wordcount: 1198
ht-degree: 68%

---

# カスタムプロバイダーの設定 {#sms-configuration-custom}

>[!BEGINSHADEBOX]

**このページでは：** API資格情報を作成し、認証方法を選択し、SMSおよびRCS メッセージを送信するためのヘッダー、ペイロード、インバウンド設定を設定することで、Adobe Journey Optimizerでカスタムメッセージプロバイダーを統合する方法について説明します。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_provider_url"
>title="プロバイダー URL"
>abstract="接続する予定の外部 API の URL を指定します。 この URL は、API の機能にアクセスするためのエンドポイントとして機能します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_header_parameters"
>title="ヘッダーパラメーター"
>abstract="適切な認証、コンテンツの書式設定、効果的な API 通信を有効にするために、追加ヘッダーのラベル、タイプ、値を指定します。 "

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_provider_payload"
>title="プロバイダーペイロード"
>abstract="処理と応答の生成用の正しいデータの送信を確保するために、リクエストペイロードを指定します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_response_msg_id_extractor"
>title="プロバイダーペイロード"
>abstract="Journey Optimizer がプロバイダーの送信応答から一意のメッセージ ID を抽出する方法を指定します。 </br>フィールド一致：フィールド名（例：messageId）を入力します。 AJO は、応答をスキャンし、最初に一致する値を返します。 </br>ドット表記法：フィールドへのパス（例：messages.0.id）を入力します。 配列に数値セグメントを使用します。 $ 接頭辞はありません。</br> プロバイダーがコールバックデータフィールドの渡しをサポートしている場合は、空白のままにします。"

この機能により、独自のメッセージプロバイダーを統合および設定できるようになり、デフォルトのオプション（Sinch、Twilio、Infobip）を超える柔軟性が得られます。 これにより、モバイルメッセージのオーサリング、配信、レポート、同意管理をシームレスに行うことができます。

カスタムプロバイダー設定を使用すると、Journey Optimizer 内でサードパーティのメッセージサービスを直接接続し、動的コンテンツのメッセージペイロードをカスタマイズし、オプトイン／オプトアウトの環境設定を管理して、SMS チャネルと RCS チャネルの両方でコンプライアンスを確保できます。

カスタムプロバイダーを設定するには、次の手順に従います。

1. [API 資格情報の作成](#api-credential)
1. [Webhook の作成](mobile-webhook.md)
1. [チャネル設定の作成](mobile-configuration-surface.md)
1. [SMS チャネルアクションを使用したジャーニーまたはキャンペーンの作成](create-mobile-message.md)

## API 資格情報の作成 {#api-credential}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_channel_type"
>title="チャネルタイプ"
>abstract="オプション。 このカスタム SMS プロバイダー資格情報を使用して送信されたメッセージ（SMSまたはRCSなど）を分類します。 Journey Optimizerは、XDM エクスペリエンスイベントに値を書き込むため、チャネル別の配信をレポートおよび追跡できます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_webhook_require_auth"
>title="認証"
>abstract="有効にすると、Adobe IMSで認証されたリクエストのみが受け入れられます。 このエンドポイントにデータを送信する場合、発信者は有効なOAuth トークンを含める必要があります。"

Adobeでは標準で使用できないカスタムプロバイダー（Sinch、Infobip、Twilioなど）を使用してJourney Optimizerでモバイルメッセージを送信するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;に移動し、**[!UICONTROL SMS 設定]**&#x200B;の下にある **[!UICONTROL API 資格情報]**&#x200B;メニューを選択して、「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

   ![](assets/sms_byo_1.png)

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：カスタム。

   * **[!UICONTROL 名前]**：API 資格情報の名前を入力します。

   * **[!UICONTROL プロバイダーのアプリ ID]**：SMS プロバイダーから提供されたアプリケーション ID を入力します。

   * **[!UICONTROL プロバイダー名]**：SMS プロバイダーの名前を入力します。

   * **[!UICONTROL プロバイダーの URL]**：SMS プロバイダーの URL を入力します。

   * **[!UICONTROL チャネルタイプ]**：オプション。 この資格情報がどのモバイルチャネルを表しているかを示します（SMS、RCS、MMSなど）。

   * **[!UICONTROL 認証タイプ]**：認証タイプを選択し、選択した認証方法に基づいて[対応するフィールドに入力](#auth-options)します。

     ![](assets/sms-byop.png)

1. 「**[!UICONTROL mTLS サポート]**」オプションを有効にすると、安全な接続を確立する前にクライアントとサーバーの両方が相互に認証するようになります。

   mTLS のみを使用するには、**[!UICONTROL 認証タイプ]**&#x200B;ドロップダウンから「**[!UICONTROL 認証なし]**」を選択し、**[!UICONTROL mTLS サポート]**&#x200B;を有効にします。

   mTLSは、SMS プロバイダー（メッセージ送信）エンドポイントにのみ適用されます。 OAuth トークンエンドポイントではmTLSを使用できません。 テストする前に、トークンエンドポイントでmTLSが無効になっていることを確認します。

   >[!IMPORTANT]
   >
   >[MTLS公開証明書API](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/mtls-api/public-certificate-endpoint)から公開証明書をダウンロードし、サーバーのトラストストアに追加して、SMS送信エンドポイントをAdobe Experience Platform認証局チェーンを信頼するように設定します（想定されるクライアント CN: `ajo-sms.aep-mtls.adobe.com`）。そうしないと、Journey Optimizerでクライアント証明書が省略され、SMS配信が失敗します。

1. 「**[!UICONTROL ヘッダー]**」セクションで、「**[!UICONTROL 新しいパラメーターを追加]**」をクリックし、外部サービスに送信されるリクエストメッセージの HTTP ヘッダーを指定します。

   **Content-Type** および **Charset** ヘッダーフィールドはデフォルトで設定され、削除できません。

   ![](assets/sms_byo_2.png)

1. **[!UICONTROL プロバイダーペイロード]**&#x200B;を追加して、リクエストペイロードを検証およびカスタマイズします。

   RCS メッセージの場合、このペイロードは後で[コンテンツデザイン](create-mobile-message.md#sms-content)中に使用されます。

   >[!NOTE]
   >
   >基本認証またはベアラー認証を使用してカスタム SMS プロバイダーを設定する際は、JSON ペイロードに `authOption` パラメーターを含める必要があります。 さらに、**プロバイダーペイロード**&#x200B;は、テンプレート変数 `{{fromNumber}}`、`{{toNumber}}`、`{{message}}` を参照する必要があります。

1. 「**[!UICONTROL インバウンドのカスタムデータセットを使用]**」を選択して、この資格情報のインバウンド SMSを、ドロップダウンから選択した事前作成データセットにルーティングします。 [ インバウンドキーワードのカスタムデータセットの使用について詳しく見る](custom-dataset-inbound-keywords.md)

   >[!NOTE]
   >
   >データセットスキーマは&#x200B;**[!UICONTROL XDM ExperienceEvent]**&#x200B;である必要があり、少なくとも次のフィールドグループを含める必要があります。
   >* Adobe CJM ExperienceEvent - メッセージインタラクションの詳細
   >* Adobe CJM ExperienceEvent - Message Execution Details
   >* Adobe CJM ExperienceEvent - メッセージプロファイル詳細
   >
   >プロファイルに対してスキーマとデータセットを有効にする必要があります。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、![ごみ箱アイコン](assets/do-not-localize/Smock_Delete_18_N.svg)をクリックして、API 資格情報を削除します。

   ![](assets/sms_byo_3.png)

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

   ![](assets/sms_byo_4.png)

1. 既存の API 資格情報から「**[!UICONTROL SMS 接続を検証]**」をクリックし、指定されたデバイスにサンプルメッセージを送信して、SMS API 資格情報をテストおよび検証します。

1. 「**番号**」フィールドと「**メッセージ**」フィールドに入力し、「**[!UICONTROL 接続を確認]**」をクリックします。

   >[!IMPORTANT]
   >
   >メッセージは、プロバイダーのペイロード形式に合わせて構造化する必要があります。

   ![](assets/verify-connection.png)

API 資格情報を作成して設定した後、SMS メッセージの [Webhook のインバウンド設定](#webhook)を指定する必要があります。

>[!TIP]
>
>サンドボックスごとに個別のエージェント設定（実稼動、開発など）を常に作成して管理します。 環境横断的なWebhook応答の問題を防ぐことができます。 サンドボックス間で同じAPI資格情報、Webhook、プロバイダーコールバック URL （RCS エージェントを含む）を再利用しないでください。

### カスタム SMS プロバイダーの認証オプション {#auth-options}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_auth_type"
>title="認証タイプ"
>abstract="API へのアクセスに必要な認証方法を指定します。これにより、外部サービスとの安全で承認済みの通信が確保されます。"

>[!BEGINTABS]

>[!TAB API キー]

API 資格情報を作成したら、API キー認証に必要なフィールドに入力します。

* **[!UICONTROL 名前]**：API キー設定の名前を入力します。
* **[!UICONTROL API トークン]**：SMS プロバイダーから提供された API トークンを入力します。

![](assets/sms-byop-api-key.png)

>[!TAB MAC 認証]

API 資格情報を作成したら、MAC 認証に必要なフィールドに入力します。

* **[!UICONTROL 名前]**：MAC 認証設定の名前を入力します。
* **[!UICONTROL API トークン]**：SMS プロバイダーから提供された API トークンを入力します。
* **[!UICONTROL API 秘密鍵]**：SMS プロバイダーから提供された API 秘密鍵を入力します。 このは、安全な通信のための MAC（メッセージ認証コード）を生成するために使用されます。
* **[!UICONTROL MAC 認証ハッシュ形式]**：MAC 認証のハッシュ形式を選択します。

![](assets/sms-byop-mac.png)

>[!TAB OAuth 認証]

API 資格情報を作成したら、OAuth 認証に必要なフィールドに入力します。

* **[!UICONTROL 名前]**：OAuth 認証設定の名前を入力します。

* **[!UICONTROL API トークン]**：SMS プロバイダーから提供された API トークンを入力します。

* **[!UICONTROL OAuth URL]**：OAuth トークンを取得する URL を入力します。

* **[!UICONTROL OAuth 本文]**：`grant_type`、`client_id`、`client_secret` などのパラメーターを含む、JSON 形式の OAuth リクエスト本文を指定します。

Journey Optimizerは、カスタム SMS コネクタの有効期限が切れると、OAuth トークンを動的に更新します。

![](assets/sms-byop-oauth.png)

>[!TAB JWT 認証]

API 資格情報を作成したら、JWT 認証に必要なフィールドに入力します。

* **[!UICONTROL 名前]**：JWT 認証設定の名前を入力します。

* **[!UICONTROL API トークン]**：SMS プロバイダーから提供された API トークンを入力します。

* **[!UICONTROL JWT ペイロード]**：発行者、件名、オーディエンス、有効期限など、JWT に必要なクレームを含む JSON ペイロードを入力します。

![](assets/sms-byop-jwt.png)

>[!ENDTABS]

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3431625)


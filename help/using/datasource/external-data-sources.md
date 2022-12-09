---
solution: Journey Optimizer
product: journey optimizer
title: 外部データソース
description: 外部データソースの設定方法について説明します。
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
exl-id: f3cdc01a-9f1c-498b-b330-1feb1ba358af
source-git-commit: f6db4f7cbb1951c009fa7915f340da96eea74120
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 0%

---

# 外部データソース {#external-data-sources}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_custom"
>title="外部データソース"
>abstract="外部データソースを使用すると、例えばホテル予約システムを使用して人が登録済みかどうかを確認する必要がある場合などに、サードパーティシステムとの接続を定義することができます。 Adobe エクスペリエンスプラットフォームデータソースとは異なり、外部データソースは必要な数だけ作成することができます。"

外部データソースを使用すると、例えばホテル予約システムを使用して人が登録済みかどうかを確認する必要がある場合などに、サードパーティシステムとの接続を定義することができます。 Adobe エクスペリエンスプラットフォームデータソースとは異なり、外部データソースは必要な数だけ作成することができます。

>[!NOTE]
>
>このページ ](../configuration/external-systems.md) に [ は、外部システムの操作時に guardrails が表示されています。

JSON を使用した REST Api はサポートされています。 API キー、basic およびカスタム認証モードがサポートされています。

では、実際の気象データに応じて、旅のビヘイビアーをカスタマイズするために使用する weather API サービスの例を見てみましょう。

ここでは、次の2つの API 呼び出しの例を示します。

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

この呼び出しは、メイン URL ( _https://api.adobeweather.org/weather_ )、2つのパラメーターセット (市区町村は &quot;市区町村&quot;、緯度と経度の場合は &quot;lat/long&quot;)、api キー (appid) で構成されています。

ここでは、新しい外部データソースの作成と設定を行う主な手順について説明します。

1. データソースのリストからをクリック **[!UICONTROL Create Data Source]** して、新しい外部データソースを作成します。

   ![](assets/journey25.png)

   これにより、画面の右側にデータソースの構成ペインが表示されます。

   ![](assets/journey26.png)

1. データソースの名前を入力します。

   >[!NOTE]
   >
   >スペースまたは特殊文字は使用しないでください。 30文字を超えないようにしてください。

1. データソースに説明を追加します。 この手順はオプションです。
1. 外部サービスの URL を追加します。 Https://api.adobeweather.org/weather _の例を次_ に示します。

   >[!CAUTION]
   >
   >セキュリティ上の理由から、HTTPS を使用することを強くお勧めします。 また、一般に公開されていない Adobe アドレスを使用したり、IP アドレスを使用することができないことに注意してください。

   ![](assets/journey27.png)

1. 外部サービスの設定 **[!UICONTROL No authentication]** に応じて、、 **[!UICONTROL Basic]** **[!UICONTROL Custom]** 、または **[!UICONTROL API key]** によって認証を設定します。 カスタム認証モードについて詳しくは、次の項 ](../datasource/external-data-sources.md#custom-authentication-mode) を参照してください [ 。この例では、以下のように選択します。

   * **[!UICONTROL Type]**: &quot;API key&quot;
   * **[!UICONTROL Name]**: &quot;appid&quot; (API key パラメーターの名前)
   * **[!UICONTROL Value]**: &quot;1234&quot; (これは、当社の API キーの値です)
   * **[!UICONTROL Location]**: &quot;Query parameter&quot; (API キーが URL に配置されています)

   ![](assets/journey28.png)

1. ボタンをクリック **[!UICONTROL Add a New Field Group]** して、設定されている各 API パラメーターに対して新しいフィールドグループを追加します。 フィールドグループ名には、スペースや特殊文字は使用できません。 上の例では、2つのフィールドグループを作成する必要があります。これは、各パラメーターセットに1つずつ、市および長い/lat を作成することです。

「Long ¥ lat」パラメーターセットについては、次の情報を使用してフィールドグループを作成します。

* **[!UICONTROL Used in]**: フィールドグループを使用する journeys の数が表示されます。 このフィールドグループを使用して journeys のリストを表示するには、 **[!UICONTROL View journeys]** このアイコンをクリックします。
* **[!UICONTROL Method]**: 「POST」または「GET」メソッドを選択します。 ここでは、GET メソッドを選択します。
* **[!UICONTROL Dynamic Values]**&#x200B;次の例では、「coma」、「long、lat」で区切られたさまざまなパラメーターを入力します。 パラメーターの値は実行コンテキストに依存するため、journeys で定義されます。 [詳細情報](../building-journeys/expression/expressionadvanced.md)
* **[!UICONTROL Response Payload]**: フィールド内 **[!UICONTROL Payload]** をクリックして、コールによって返されたペイロードの例をペーストします。 この例では、weather API web サイトで使用されるペイロードを使用しました。 フィールドタイプが正しいかどうかを確認します。 この API が呼び出されるたびに、システムはペイロードの例に含まれるすべてのフィールドを取得します。 現在パスしているペイロードを変更する場合は、「on **[!UICONTROL Paste a new payload]** 」をクリックします。
* **[!UICONTROL Sent Payload]**&#x200B;次の例では、このフィールドは表示されていません。 このオプションは、「POST」メソッドを選択した場合にのみ使用できます。 サードパーティシステムに送信されるペイロードをペーストします。

GET 呼び出しでパラメーターを使用する必要がある場合は、フィールドに **[!UICONTROL Dynamic Values]** パラメーターを入力して、呼び出しの最後に自動的に追加されます。 POST 呼び出しの場合は、次の操作を実行する必要があります。

* 次の例のように、フィールドで **[!UICONTROL Dynamic Values]** の呼び出し時に渡されるパラメーターを一覧表示します。
* 送信されたペイロードの本文でもまったく同じシンタックスを指定します。 そのためには、次のように「param」を追加する必要があります。「パラメーターの名前」 (次の例では &quot;identifier&quot;) を追加します。 以下のシンタックスに従います。

   ```
   {"id":{"param":"identifier"}}
   ```

![](assets/journey29.png)

をクリック **[!UICONTROL Save]** します。

これで、データソースが設定され、journeys として使用できるようになりました。例えば、状況に応じて、電子メールをカスタマイズすることができます。 気温が30°C を超えている場合は、特定の通信を行うことができます。

## カスタム認証モード{#custom-authentication-mode}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="カスタム認証について"
>abstract="カスタム認証モードは、OAuth2 などの API 折り返しプロトコルを呼び出すために複雑な認証に使用されます。 アクションの実行は、2段階の手順で行います。 最初に、エンドポイントへの呼び出しが実行され、アクセストークンが生成されます。 その後、アクセストークンがアクションの HTTP 要求に挿入されます。"

この認証モードは複雑な認証のために使用されます。 OAuth2 などの API 折り返しプロトコルを呼び出して、アクションの実際の HTTP 要求に注入されるアクセストークンを取得します。

カスタム認証を設定する際には、以下のボタンをクリックして、カスタム認証ペイロードが正しく設定されているかどうかを確認できます。

![](assets/journey29-bis.png)

テストが成功した場合、ボタンは緑色になります。

![](assets/journey29-ter.png)

この認証では、2つの手順を実行してアクションを実行します。

1. エンドポイントを呼び出して、アクセストークンを生成します。
1. アクセストークンの適切な方法で挿入することによって、REST API を呼び出します。

この認証は、2つの部分で構成されます。

アクセストークンを生成するために呼び出されるエンドポイントの定義。

* エンドポイント: エンドポイントの生成に使用する URL
* エンドポイント (GET または POST) 上の HTTP 要求のメソッド
* headers: 必要に応じて、この呼び出しにヘッダーとして挿入されるキーと値のペア
* body: メソッドが POST の場合は、呼び出しの本体について記述します。 BodyParams (キーと値のペア) で定義されている、限られた body 構造をサポートします。 BodyType は、呼び出しの本体のフォーマットとエンコードを示します。
   * &#39; form &#39;: コンテンツタイプが application/x-www-x-www-form-urlencoded (charset UTF-8) になり、キーと値のペアが次のようにシリアル化されるとしてされることを意味します。
   * &#39; json &#39;: コンテンツタイプが application/json (charset UTF-8) になり、キーと値のペアが json オブジェクトとして直列化されます。次のようになります: _{&quot;key1&quot;、&quot;value1&quot;、&quot;key2&quot;: &quot;value2&quot;、...}_

アクションの HTTP 要求に、アクセストークンが注入される方法の定義。

* authorizationType: 生成されたアクセストークンをそのアクションの HTTP 呼び出しに注入する方法を定義します。 指定できる値は次のとおりです。

   * bearer: 認証ヘッダー _にアクセストークンが注入されるようにする必要があることを示します。 authorization: Bearer &lt;access token=&quot;&quot;>_&lt;/access>
   * header: アクセストークンを、プロパティ tokenTarget によって定義されたヘッダー名として、ヘッダーとして挿入する必要があることを示します。 例えば、tokenTarget が myHeader の場合、アクセストークンは見出しとして次のように挿入されます。 _myheader: &lt;access token=&quot;&quot;>_&lt;/access>
   * queryParam: アクセストークンを queryParam として挿入する必要があることを示します。これは、プロパティ tokenTarget によって定義されるクエリパラメーター名です。 例えば、tokenTarget が myQueryParam の場合、アクション呼び出しの URL は次のようになり&lt;url>ます。 &lt;access token=&quot;&quot;>_&lt;/access> &lt;/url>_

* tokenInResponse: 認証呼び出しからアクセストークンを抽出する方法を指定します。 このプロパティは次のように指定できます。
   * 「response」: HTTP 応答がアクセストークンであることを示します。
   * json のセレクター (応答が json の場合、XML などの他の形式はサポートされていません)。 このセレクターの形式は _json://&lt;path to=&quot;&quot; the=&quot;&quot; access=&quot;&quot; token=&quot;&quot; property=&quot;&quot;>_ です。&lt;/path>例えば、次のよう _な呼び出しの応答が表示されている場合、{&quot;access_token&quot;: &quot;theToken&quot;、&quot;timestamp&quot;: 12323445656}_ 、tokenInResponse は以下 _のようになります: json://access_token_

この認証の形式は以下のとおりです。

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```

カスタム認証データソースのトークンのキャッシュ期間を変更することができます。 以下に、カスタム認証ペイロードの例を示します。 キャッシュ期間は、「cacheDuration」パラメーターで定義されています。 これにより、生成されるトークンをキャッシュに保存する期間を指定します。 単位には、ミリ秒、秒、分、時間、日、月、年を使用できます。

```
"authentication": {
    "type":"customAuthorization",
    "authorizationType":"Bearer",
    "endpoint":"http://localhost:${port}/epsilon/oauth2/access_token",
    "method":"POST",
    "headers": {
        "Authorization":"Basic EncodeBase64(${epsilonClientId}:${epsilonClientSecret})"
        },
    "body": {
        "bodyType":"form",
        "bodyParams": {
             "scope":"cn mail givenname uid employeeNumber",
             "grant_type":"password",
             "username":"${epsilonUserName}",
             "password":"${epsilonUserPassword}"
             }
        },
    "tokenInResponse":"json://access_token",
    "cacheDuration":
             { "duration":5, "timeUnit":"seconds" }
    }
```

>[!NOTE]
>
>キャッシュ期間を使用すると、認証エンドポイントの呼び出しが多すぎるということを防ぐことができます。 認証トークンの保存は、サービスにキャッシュされますが、持続性はありません。 サービスが再起動した場合は、クリーンキャッシュによって開始されます。 デフォルトでは、キャッシュ期間は1時間です。 カスタム認証ペイロードでは、別の保存期間を指定することによって、この設定を調整できます。

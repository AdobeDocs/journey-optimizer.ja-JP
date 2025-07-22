---
solution: Journey Optimizer
product: journey optimizer
title: 外部エンドポイントからのデータを使用したコンテンツのパーソナライズ
description: 外部エンドポイントからデータを動的に取得して、インバウンドコンテンツをパーソナライズする方法を説明します。
badge: label="限定提供" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター
source-git-commit: f5d1bc27afadbf875fe4dd3149ce090a8773e0f9
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 1%

---


# 外部エンドポイントからのデータを使用したコンテンツのパーソナライズ {#data-endpoint}

>[!AVAILABILITY]
>
>この機能は、一連の組織でのみ使用できます（使用制限あり）。

Journey Optimizerでは、外部エンドポイントからのデータを活用して、コードベースのエクスペリエンス、web、アプリ内メッセージチャネルなどのインバウンドチャネルでコンテンツをパーソナライズできます。

それには、パーソナライゼーションエディターで専用のヘルパー関数 `externalDataLookup` を使用できます。 ヘルパーを使用するには、まず [!DNL Journey Optimizer] **アクション** を定義し、外部エンドポイントに関する詳細を設定する必要があります。

## 必読

### ランタイム実行

インバウンドアクションに externalDataLookup ヘルパーが含まれる場合、[!DNL Adobe Experience Platform] Edge Networkがパーソナライゼーションリクエストを受信して処理する際に、エンドポイントが動的に呼び出されます。 つまり、外部エンドポイントは、クライアントが特定のサーフェスのためにAEP Edge Networkに送信するのと少なくとも同じ量の同時読み込みとスループットを処理できる必要があります。

### 認証

アクション設定の認証オプションは、現在、externalDataLookup ヘルパーではサポートされていません。
それまでの間、API キーベースの認証またはその他のプレーンテキストの認証キーの場合は、アクション設定のヘッダーフィールドとして指定できます。
Adobeの内部エンドポイントのみ：エンドポイントのサービストークンベースの認証を有効にするには、AJO エンジニアリングにお問い合わせください。

### ガードレールと制限

詳しくは、AJO インバウンドチャネルキャンペーンおよびジャーニーのカスタムアクション#GuardrailsandGuidelines 参照してください。

デフォルトでは、AJOは、外部エンドポイントの呼び出し時にタイムアウトの 300 ミリ秒を使用します。 エンドポイントのタイムアウトを増やすには、AJO エンジニアリングにお問い合わせください。
Personalization エディターで、AJOは、式を挿入する際にエンドポイント応答のスキーマを参照できず、式で使用される応答からの JSON 属性への参照を検証しません。
externalDataLookup ヘルパーを使用して置き換えるペイロード変数パラメーターでサポートされているデータタイプは、String、Integer、Decimal、Boolean、listString、listInt、listInteger、listDecimal です
アクション設定に対する変更は、ライブキャンペーンおよびジャーニーの対応する externalDataLookup 呼び出しには反映されません。 変更を反映するには、externalDataLookup ヘルパーのアクションを使用しているライブキャンペーンまたはジャーニーをコピーまたは変更する必要があります。
変数の使用は、まだ外部データ参照ヘルパーパラメーター内ではサポートされていません。
動的 URL パスは現在サポートされていません。  - インバウンドカスタムアクションの機能強化#DynamicPathSegments

## アクションの作成

アクションを作成して、ルックアップのエンドポイントを設定します。 これは、各エンドポイントに対して 1 回だけ行う必要があり、技術ユーザーが行う必要があります。 このページを参照してください。

ジャーニーのコンテンツを取得する **[!UICONTROL カスタムアクション]** アクティビティと、ジャーニーまたはキャンペーンのインバウンドアクションのデータを取得する `externalDataLookup` ヘルパー関数の両方で同じアクションを使用できます。

**[!UICONTROL 管理]**/**[!UICONTROL 設定]** メニューを参照します。

アクション ID をメモして、手順 6 で使用するためにコピーします。


## 取得したデータを使用してコンテンツをパーソナライズする

### ヘルパー関数をコンテンツに追加します

1. インバウンドキャンペーンまたはジャーニーアクションを作成し、そのコンテンツを編集します。

1. 外部エンドポイントから取得したデータを使用するコンテンツを見つけ、パーソナライゼーションエディターにアクセスします。

1. ヘルパー関数メニューを選択し、`externalDataLookup` ヘルパー関数を探します。

1. を選択すると、コードに関連する構文を挿入し、`actionId` と `result` のパラメーター値を次のように置き換えます。

   * `actionId`：アクションの作成時にコピーしたアクション nID を貼り付けます。
   * `result`：このパラメーターを任意の名前に設定します。 この結果変数を使用して、取得したコンテンツにアクセスします。

1. エンドポイント呼び出しの一部として渡される変数パラメーター値を追加します。 例えば、言語パラメーターと最大 items パラメーターを渡す方法を次に示します。

### 取得したデータを使用したパーソナライズ

外部エンドポイント参照呼び出しから取得したデータにアクセスするには、パーソナライゼーション式とヘルパー関数を使用して、アクション定義の応答ペイロードで定義されたフィールドを参照します。

`result` 変数を使用して、取得したデータにアクセスし、インバウンドアクションのコンテンツに挿入します。 例えば、エンドポイントから取得した項目の JSON 配列を返す方法を次に示します。

次の例で見てみましょう。アクションの応答ペイロードは、次のように設定されています。

```
{
    "videos": [
        {
            "id": "integer",
            "title": "string",
            "description": "string",
            "thumbnail_url": "string",
            "video_page_url": "string",
            "url": "string",
            "video_type": "string",
            "start_timestamp": "dateOnly",
            "created_on": "dateOnly",
            ...
        }
    ]
}
```

Personalizationの例 1 - コードベースの Experience HTML アクションで最初のビデオの説明を表示する：

```
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}
 
First video description: <b>result.videos[0].description</b>
```

Personalizationの例 2 - コードベースのエクスペリエンス JSON アクションで項目配列を返す

```
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}
 
[
{{#each result.videos as |item|}}
    {                                                  
        "title": "{{item.title}}",
        "url": "{{item.video_page_url}}",
        "thumbnail_url": "{{item.thumbnail_url}}",
        "start_timestamp": "{{item.start_timestamp}}"
    },
{{/each}}
]
```

## タイムアウトとエラー処理

AJOでは、AEP Edge Networkの低遅延および高スループットのパフォーマンス特性を維持するために、外部エンドポイントを呼び出す際に厳密なタイムアウトを使用します。

エンドポイントがタイムアウトした場合、またはエンドポイントに到達する他の種類のエラーがある場合、結果変数は空になります。 この場合、結果変数内の属性への参照も空になります。 コンテンツ内に属性を単に表示すると、空白で表示されます。 結果で配列属性をループ処理しようとすると、項目が返されません。

フォールバックコンテンツを表示してタイムアウトやエラーをより適切に処理する場合は、検索結果が空かどうかを確認し、その場合はフォールバックコンテンツを表示できます。

例えば、次のように、単一の属性に対するフォールバック値を表示できます。

最初のビデオの説明：{%=result.videos[0].description ?: &quot;none found&quot; %}


または、次のように、コンテンツブロック全体を条件付きでレンダリングできます。

{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}

{%#if result%}
結果を使用して何らかの処理を行う…
{%else%}
... フォールバックコンテンツを返す…
{%/if%}
デバッグ
外部データ検索のデバッグに役立つように、AEP AssuranceのEdge Delivery ビューには、タイムアウトとエラーの詳細が含まれています。 インバウンドアクションで externalDataLookup ヘルパーを使用した場合に期待される結果が得られない場合は、Assurance セッションを開始し、web またはモバイル実装からAJO呼び出しを開始し、Edge Delivery ビューを使用してタイムアウトやエラーの詳細を確認できます。

例：

実行詳細の一部としての Assurance トレースのEdge Delivery セクションに、新しい customActions ブロックが追加されました。

リクエストと応答の詳細は、以下に類似したものです。 「エラー」セクションは、カスタムアクションの実行中に問題が発生した場合のデバッグに役立ちます

## よくある質問

+++リクエストからコンテキスト属性をパラメーターとして外部データ参照に渡す方法を教えてください。

コンテキスト属性/ データストリーム / イベント メニューを使用して、使用しているエクスペリエンスイベントスキーマを参照し、関連する属性をパラメーター値として次のように挿入します。

`{{externalDataLookup actionId="..." result="result" query.myQueryParameter=context.datastream.event.<schemaId>.my.xdm.attribute}}`

+++

+++AJOは外部エンドポイント応答のキャッシュを行いますか？

現在はサポートされていません。 この機能は今後サポートされる予定です。

+++









構文
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result" optional-parameters...}}



パラメーターを渡す
外部エンドポイントが呼び出されると、アクションで定義されているすべての定数ヘッダー値、クエリパラメーター、リクエストペイロード値が、アクション設定で指定された値で送信されます。

任意の変数ヘッダー値、クエリ/パスパラメーターまたはリクエストペイロード値について、パラメーターを使用して externalDataLookup ヘルパーに値を動的に渡すことができます。

パラメーター名：

ヘッダーパラメーター：ヘッダー。&lt;parameter-name>
クエリパラメーター：クエリ。&lt;parameter-name>
ペイロードパラメーター：payload。&lt;parameter-name>
パスパラメーター：dynamic_path。&lt;parameter-name>
例：

{{externalDataLookup actionId="..." result="result" header.myHeaderParameter="value1" query.myQueryParameter="value2" payload.myPayloadParameter="value3"}}
パラメーター値は、固定値にすることも、プロファイルフィールドやその他のコンテキスト属性を参照してパーソナライズすることもできます。次に例を示します。

{{externalDataLookup actionId="..." result="result" query.myQueryParameter=profile.myProfileValue}}
ペイロードパラメーターは、ネストされた JSON 属性を参照するドット表記を使用して指定できます。例：

{{externalDataLookup actionId="..." result="result" payload.context.channel="web"}}
---
title: 外部データ参照ヘルパー
description: Adobe Journey Optimizerの動的パーソナライゼーションに外部 Data Lookup Helper を使用するための包括的なガイドです。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
hide: true
hidefromtoc: true
badge: label="限定提供" type="Informative"
source-git-commit: f5d1bc27afadbf875fe4dd3149ce090a8773e0f9
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 1%

---


# 外部データ参照ヘルパー

`externalDataLookup` パーソナライゼーションエディターの [!DNL Journey Optmizer] ヘルパーを使用して、外部エンドポイントから動的にデータを取得し、コードベースのエクスペリエンス、web、アプリ内メッセージチャネルなどのインバウンドチャネルのコンテンツを生成するために使用できます。

>[!AVAILABILITY]
>
>この機能は、一連の組織でのみ使用できます（使用制限あり）。

ヘルパーを使用するには、まず **[!UICONTROL 管理]**/**[!UICONTROL 設定]** メニューでアクションを定義する必要があります。 「アクション」では、URL、GETと POST メソッド、ヘッダーパラメーター、クエリパラメーター、POST body JSON スキーマ、レスポンス JSON スキーマなど、外部エンドポイントに関する詳細を設定します。

アクションを定義すると、次の場合に使用できます。

* ジャーニー内のカスタムアクションアクティビティでコンテンツを取得する。
* ジャーニーとインバウンドキャンペーンでは、externalDataLookup ヘルパーでインバウンドアクションのデータを取得します。

## ガードレールと制限

インバウンドチャネルキャンペーンとジャーニー[!DNL Journey Optimizer] カスタムアクションも参照#GuardrailsandGuidelines てください。

* デフォルトでは、[!DNL Journey Optimizer] は外部エンドポイントの呼び出し時に 300 ミリ秒のタイムアウトを使用します。 エンドポイントのタイムアウトを増やすには、[!DNL Journey Optimizer] Engineering にお問い合わせください。
* Personalization エディターでは、式を挿入 [!DNL Journey Optimizer] る際にエンドポイント応答のスキーマを参照したり、式で使用される応答から JSON 属性への参照を検証したりすることはできません。
* externalDataLookup ヘルパーを使用して置き換えるペイロード変数パラメーターでサポートされているデータタイプは、String、Integer、Decimal、Boolean、listString、listInt、listInteger、listDecimal です。
* アクション設定に対する変更は、ライブキャンペーンおよびジャーニーの対応する externalDataLookup 呼び出しには反映されません。 変更を反映するには、externalDataLookup ヘルパーのアクションを使用しているライブキャンペーンまたはジャーニーをコピーまたは変更する必要があります。
* 変数の使用は、まだ外部データ参照ヘルパーパラメーター内ではサポートされていません。
* 動的 URL パスは現在サポートされていません。  - インバウンドカスタムアクションの機能強化#DynamicPathSegments.
* マルチパスレンダリングがサポートされています。
* アクション設定の認証オプションは、現在、externalDataLookup ヘルパーではサポートされていません。 それまでの間、API キーベースの認証またはその他のプレーンテキストの認証キーの場合は、アクション設定のヘッダーフィールドとして指定できます。

## アクションの設定とヘルパーの使用

アクションを定義し、ヘルパーをパーソナライゼーションに使用するには、次の手順に従います。

1. アクションを作成して、ルックアップのエンドポイントを設定します。 これは、各エンドポイントに対して 1 回だけ行う必要があり、技術ユーザーが行う必要があります。 [ カスタムアクションの設定方法を学ぶ ](../action/about-custom-action-configuration.md)

   アクション ID をメモしてコピーします。

   ![](assets/external-data-action.png)

1. インバウンドキャンペーンまたはジャーニーアクションを作成します。 この例では、externalDataLookup ヘルパーをコードベースのエクスペリエンス JSON アクションで使用する方法を示していますが、任意のインバウンドチャネルのパーソナライゼーションフィールドで使用できます。

1. アクションの内容を編集し、パーソナライゼーションエディターのヘルパー関数に移動して、**[!UICONTROL ヘルパー関数]**/**[!UICONTROL ヘルパー]** に移動します。

1. `+` ボタンをクリックして、externalDataLookup ヘルパーを挿入します。 ヘルパー式が、`actionId` と `result` のプレースホルダー値と共にエディターに挿入されます。

   ![](assets/external-data-personalization.png)

   プレースホルダーの値を次のように置き換えます。

   * `actionId`：以前にコピーしたアクション ID を貼り付けます。
   * `result`：任意の名前を設定します。 この結果変数を使用して、取得したコンテンツにアクセスします。

1. エンドポイント呼び出しの一部として渡される変数パラメーター値を追加します。 例えば、言語パラメーターと最大 items パラメーターを渡す方法を次に示します。

   ![](assets/external-data-personalization-example.png)

1. 結果変数を使用して、取得したデータにアクセスし、インバウンドアクションのコンテンツに挿入します。 例えば、エンドポイントから取得した項目の JSON 配列を返す方法を次に示します。

   ![](assets/external-data-personalization-result.png)

## 仕組み

### ランタイム実行

インバウンドアクションに externalDataLookup ヘルパーが含まれる場合、[!DNL Journey Optimizer] のパーソナライゼーションリクエストがAEP Edge Networkによって受信および処理される際に、エンドポイントが動的に呼び出されます。

つまり、外部エンドポイントは、クライアントが特定のサーフェスのためにAEP Edge Networkに送信するのと少なくとも同じ量の同時読み込みとスループットを処理できる必要があります。

### 構文

`{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result" optional-parameters...}}`

### パラメーターを渡す

外部エンドポイントが呼び出されると、アクションで定義されているすべての定数ヘッダー値、クエリパラメーター、リクエストペイロード値が、アクション設定で指定された値で送信されます。

任意の変数ヘッダー値、クエリ/パスパラメーターまたはリクエストペイロード値について、パラメーターを使用して externalDataLookup ヘルパーに値を動的に渡すことができます。

パラメーター名：

* ヘッダーパラメーター：ヘッダー。&lt;parameter-name>
* クエリパラメーター：クエリ。&lt;parameter-name>
* ペイロードパラメーター：payload。&lt;parameter-name>
* パスパラメーター：dynamic_path。&lt;parameter-name>

例：

`{{externalDataLookup actionId="..." result="result" header.myHeaderParameter="value1" query.myQueryParameter="value2" payload.myPayloadParameter="value3"}}`

パラメーター値は、固定値にすることも、プロファイルフィールドやその他のコンテキスト属性を参照してパーソナライズすることもできます。次に例を示します。

`{{externalDataLookup actionId="..." result="result" query.myQueryParameter=profile.myProfileValue}}`

ペイロードパラメーターは、ネストされた JSON 属性を参照するドット表記を使用して指定できます。例：

`{{externalDataLookup actionId="..." result="result" payload.context.channel="web"}}`

### 結果へのアクセス

外部エンドポイント参照呼び出しから取得したデータにアクセスするには、パーソナライゼーション式とヘルパー関数を使用して、アクション定義の応答ペイロードで定義されたフィールドを参照します。

例えば、アクションの応答ペイロードが次のような場合：

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

その後、例えば次のように、コードベースの Experience HTML アクションの最初のビデオの説明を取得してアクセスできます。

```
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}
 
First video description: <b>result.videos[0].description</b>
```

例えば、項目を取得してループし、次のようなコードベースのエクスペリエンス JSON アクションで項目配列を返すことができます。

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

## トラブルシューティング

### タイムアウトとエラー処理

AEP Edge Networkの低遅延、高スループットのパフォーマンス特性を維持するために、外部エンドポイントを呼び出す際に [!DNL Journey Optimizer] では厳密なタイムアウトを使用します。

エンドポイントがタイムアウトした場合、またはエンドポイントに到達する他の種類のエラーがある場合、結果変数は空になります。 この場合、結果変数内の属性への参照も空になります。 コンテンツ内に属性を単に表示すると、空白で表示されます。 結果で配列属性をループ処理しようとすると、項目が返されません。

フォールバックコンテンツを表示してタイムアウトやエラーをより適切に処理する場合は、検索結果が空かどうかを確認し、その場合はフォールバックコンテンツを表示できます。

例えば、次のように、単一の属性に対するフォールバック値を表示できます。

`First video description: {%=result.videos[0].description ?: "none found" %}`

または、次のように、コンテンツブロック全体を条件付きでレンダリングできます。

```
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}
 
{%#if result%}
   ... do something with result ...
{%else%}
    ... return fallback content ...
{%/if%}
```

### デバッグ

外部データ検索のデバッグに役立つように、AEP AssuranceのEdge Delivery ビューには、タイムアウトとエラーの詳細が含まれています。 インバウンドアクションで externalDataLookup ヘルパーを使用した場合に期待される結果が得られない場合は、Assurance セッションを開始し、web またはモバイル実装から [!DNL Journey Optimizer] 呼び出しを開始し、Edge Delivery ビューを使用してタイムアウトやエラーの詳細を確認できます。

例：

実行詳細の一部としての Assurance Trace のEdge Delivery セクションに、以下に類似したリクエストと応答の詳細を含む新しい customActions ブロックが追加されました。 「エラー」セクションは、カスタムアクションの実行中に問題が発生した場合のデバッグに役立ちます

![](assets/external-data-troubleshoot.png)

## FAQ

* リクエストからコンテキスト属性をパラメーターとして外部データ参照に渡す方法を教えてください。

  コンテキスト属性/ データストリーム / イベント メニューを使用して、使用しているエクスペリエンスイベントスキーマを参照し、関連する属性をパラメーター値として次のように挿入します。

  `{{externalDataLookup actionId="..." result="result" query.myQueryParameter=context.datastream.event.<schemaId>.my.xdm.attribute}}`

* 外部エンドポイン [!DNL Journey Optimizer] 応答のキャッシュはありますか？

  現在はサポートされていません。 この機能は今後サポートされる予定です。

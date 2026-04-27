---
solution: Journey Optimizer
product: journey optimizer
title: ベンダーとの連携
description: 有効なAPIを公開する外部プラットフォームとAdobe Journey Optimizerの統合に加えて、エンジニアリングでテストされたベンダーパターンを使用して、設定の設計時に確実に機能します。
feature: Integrations
topic: Content Management
role: User
level: Intermediate
hide: true
keywords: 統合、ベンダー、サードパーティ
source-git-commit: eab38d6c5f07af0f2dc403abaf0deb3a09f0d392
workflow-type: tm+mt
source-wordcount: '9327'
ht-degree: 7%

---

# 利用可能なベンダー

>[!BEGINSHADEBOX]

目次：

* [統合の操作](integrations.md)
* [ベンダーとの連携を始める](vendor-integration-gs.md)
* **[使用可能なベンダー](vendor-integration.md)**
* [FAQ](vendor-integration-faq.md)

>[!ENDSHADEBOX]

## コンテンツとCMS {#content-and-cms}

### Contentful {#contentful}

>[!BEGINSHADEBOX]

Contentfulは、RESTまたはGraphQL経由の構造化されたエントリとアセット用のヘッドレス CMSです。これにより、Journey Optimizerは送信時または開封時にコンテンツを取得できます。

一般的なユースケースには、電子メールのローカライズされたヒーローブロック、代替テキスト、CTA、動的モジュールの製品またはプロモ – ションエントリなどがあります。 もうひとつの一般的なパターンは、パーソナライズされたメッセージを配信するために、IDごとに特定のエントリを取得することです。

>[!ENDSHADEBOX]

+++ Contentfulの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* 配信API アクセスと読み取り指向のAPI キーを備えたコンテンツフルスペース。
* コンテンツタイプとフィールド IDをクリアします。Journey Optimizerの管理者アクセス権により、統合を作成できます。


次の制限事項と除外事項が適用されます。

* ブロックリストまたはページ分割されたコンテンツ APIは、このパターンに適していません。特定のエントリまたはアセットをターゲットとする取得呼び出しを優先します。
* 書き戻しまたは双方向の同期は、この例の範囲外です。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 Content Delivery APIと配信トークンを使用して&#x200B;**GET**&#x200B;を設定し、サンプル JSONを貼り付け、フィールドをマッピングし、テストしてアクティブ化します。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Contentful Content Delivery API （CDA） URLを使用してエンドポイントを設定します：`https://cdn.contentful.com/spaces/{space_id}/environments/{environment_id}/entries/{entry_id}`

1. HTTP メソッドを選択：**GET**。

1. 認証を追加します。 以下の&#x200B;**サンプル統合フィールド**&#x200B;に示すように、**`access_token`** **クエリ** パラメーターをContent Delivery API トークンに設定します。 Contentfulは、`Authorization: Bearer` ヘッダーで同じトークンを受け入れます。統合フィールドでサポートされているフィールドを使用してください。

1. 必要に応じてパス変数（エントリ ID、ロケールなど）を追加します。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. パーソナライゼーションの必須フィールドを選択します。

1. 必要に応じて、タイムアウトとキャッシュを設定します。

1. 接続をテストしてアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

統合フィールドのサンプル（お使いのスペースと環境の[&#x200B; コンテンツ配信API](https://www.contentful.com/developers/docs/references/content-delivery-api/){target="_blank"}に合わせる）:

| フィールド | 値 |
| -- | -- |
| **URL** | `https://cdn.contentful.com/spaces/{{spaceID}}/environments/{{environment_id}}/entries/{{entry_id}}` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |
| **HTTP メソッド** | `GET` |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `spaceID` | `spaceID` | `<YOUR_SPACE_ID>` |
| `environment_id` | `environment_id` | `<YOUR_ENV_ID>` |
| `entry_id` | `entry_id` | `<YOUR_ENTRY_ID>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | `access_token` | `<YOUR_API_KEY>` | クエリパラメーター |

+++

### Sitecore {#sitecore}

>[!BEGINSHADEBOX]

Sitecore Content Hubと関連するCloud APIは、DAM形式のダウンロードとメタデータフローをサポートしています。以下のパターンの例では、ダウンロード順序をIDで示しています。

一般的なユースケースには、メールコンテンツのアセットやダウンロードのメタデータや、Sitecoreで管理されるDAM ワークフローとの連携が含まれます。

>[!ENDSHADEBOX]

+++ Sitecoreの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* テナント URLと資格情報（API サーフェスごとのベアラーまたはトークン）。
* Journey Optimizerの管理者アクセス権にアクセスして、統合を作成できます。

次の制限事項と除外事項が適用されます。

* ホスト名とパスはSitecore製品によって異なります。 テナントが公開するエンドポイントのみを使用します。
* OAuth アクセストークン、更新、および有効期間は、Sitecore セキュリティポリシーに従う必要があります。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 ダウンロード注文パスに&#x200B;**GET**&#x200B;を設定し、Sitecoreごとに認証ヘッダーを設定し、コンテキストから`id`をマッピングし、サンプル JSONを貼り付け、フィールドをマッピングし、アセットの遅延のタイムアウトを調整します。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Content Hub APIを使用してエンドポイントを設定します（例：IDによるダウンロード順序）。 URL パターンの例：

   `https://xmapps-api.sitecorecloud.io/api/v1/downloadorders/{id}`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

Journey Optimizerでこのサンプル呼び出しを設定する場合は、次のフィールドを使用します。 [Sitecore ドキュメント &#x200B;](https://doc.sitecore.com/){target="_blank"}で、製品（Content Hub、XM Cloudなど）のホスト名とAPI バージョンを確認します。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://xmapps-api.sitecorecloud.io/api/v1/downloadorders/{{id}}` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `id` | `id` | `<id_of_download_order>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |
| 認証 | 認証 | 定数 | ベアラー`<token>` | はい（オン） |
| If-Modified-Since | If-Modified-Since | 変数 | 2019-08-24T14:15:22Z | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | X-Auth-Token | `<token>` | ヘッダー |

+++

### Salsify {#salsify}

>[!BEGINSHADEBOX]

Salsifyは、商品、チャネル、デジタルアセット用のAPIを備えたPIMです。

一般的なユースケースには、電子メールやメッセージ内の製品属性やメディア URLが、同時配信されたカタログデータと連携して含まれます。

>[!ENDSHADEBOX]

+++ Salsifyの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API トークンと組織コンテキスト。プロファイルまたはコンテキストから解決可能な製品ID。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* 非常に大きなカタログ：統合でエンティティごとの取得が想定される場合は、一括リストエンドポイントを避けます。
* 属性の表示は、Salsifyの役割の権限によって制限できます。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 一括カタログ呼び出しよりも単一の製品取得を好み、ベアラー認証を設定し、サンプル JSONを貼り付け、フィールドをマップし、テストし、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Salsify製品APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://api.salsify.com/v1/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

古い参照の中には、Salsifyのダウンロード注文スタイルのパスを再利用したものもあります。代わりに、`https://app.salsify.com/api/v1/orgs/{org_id}/products/{salsify_id}`またはそれに類似したものをテナントが使用できます。 [Salsify開発者](https://developers.salsify.com/){target="_blank"}で確認します。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://app.salsify.com/api/v1/orgs/{{org_id}}/products/{{salsify_id}}` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `org_id` | `org_id` | `<org_id>` |
| `salsify_id` | `salsify_id` | `<salsify_id>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルトのパラメーター） | Content-Type | 定数 | application/json | はい（オン） |
| 認証 | 認証 | 定数 | `Bearer <YOUR_TOKEN_HERE>` | はい（オン） |
| If-Modified-Since | If-Modified-Since | 変数 | 2019-08-24T14:15:22Z | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | `apiKey` | `<your_api_key>` | ヘッダー |

+++

### Contentstack {#contentstack}

>[!BEGINSHADEBOX]

コンテンツスタックはヘッドレス CMSです。REST配信は、Journey OptimizerのJSON フィールドマッピングに典型的です。

典型的なユースケースは、ロケールを含むパラメーターを含むバナーまたはプロモーションのエントリを使用することです。

>[!ENDSHADEBOX]

+++ コンテンツスタックの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API キー、配信トークン、環境名、コンテンツタイプ UIDをスタックします。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* このパターンでは、フィールドマッピングにREST JSONを使用します。GraphQL配信は、異なる統合パスに従います。
* 実稼動用に適した配信トークンを使用します。プレビューと公開されたフローは互換性がありません。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 コンテンツスタックが必要とする`api_key`と`access_token`の両方のヘッダーを追加し、`environment` クエリパラメーターを含め、サンプル JSONを貼り付け、フィールドをマップ、テスト、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Content Delivery APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://cdn.contentstack.io/v3/content_types/{content_type_uid}/entries/{entry_uid}`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

統合フィールドのサンプル。 [Contentstack Content Delivery API](https://www.contentstack.com/docs/developers/apis/content-delivery-api/){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://cdn.contentstack.io/v3/content_types/{{content_type_uid}}/entries/{{entry_uid}}` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |
| ヘッダー | 追加のヘッダーは必要ありません。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `content_type_uid` | Content Type UID | `<your_content_type_uid>` |
| `entry_uid` | 入口UID | `<your_entry_uid>` |

**認証**

| キー名 | キー値 | 追加先 |
| --- | --- | --- |
| `api_key` | `<YOUR_STACK_API_KEY>` | ヘッダー |
| `access_token` | `<YOUR_DELIVERY_TOKEN>` | ヘッダー |

Contentstackでは、配信リクエストのヘッダーとして&#x200B;**両方**&#x200B;のキーが想定されています。

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `environment` | 環境名 | 変数 | `<your_environment_name>` | はい（オン） |

+++

### アケネオ {#akeneo}

>[!BEGINSHADEBOX]

Akeneo PIMは、製品、属性、メディア用にREST APIを公開しています。

一般的なユースケースには、メールモジュールの管理された製品データや、ジャーニーの特定のチャネルの属性などが含まれます。

>[!ENDSHADEBOX]

+++ Akeneoの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* PIM ベース URLとOAuth クライアント、製品UUIDまたはID戦略。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* PIM応答が大きい場合があります。 パーソナライゼーションに必要な属性のみをマッピングします。
* 書き込み操作は、一般的な読み取り専用パーソナライゼーションの例の範囲外です。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 **GET**&#x200B;をベアラートークンと共に使用し、クエリフラグに必要な属性オプションのみをリクエストし、サンプル JSONを貼り付け、最小限の属性セットをマッピングし、テストし、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Akeneo REST APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://{pim-host}/api/rest/v1/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

パターンの例：`https://{pim-host}/api/rest/v1/products-uuid/{uuid}` （例：`Accept: application/json`） [Akeneo API](https://api.akeneo.com/){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{your-akeneo-domain}}.com/api/rest/v1/products-uuid/{{uuidProduct}}` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `uuidProduct` | UUID | `<product_uuid>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| 認証 | 認証 | 定数 | `Bearer <YOUR_TOKEN>` | はい（オン） |
| Accept | Accept | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `with_attribute_options` | 属性オプションを含める | 変数 | false | いいえ（オフ） |
| `with_quality_scores` | 品質スコアを含める | 変数 | false | いいえ（オフ） |
| `with_completenesses` | 完全性を含める | 変数 | false | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | 認証 | `Bearer <YOUR_ACCESS_TOKEN>` | ヘッダー |

+++

### マグノリア {#magnolia}

>[!BEGINSHADEBOX]

Magnoliaでは、デプロイメントに応じて、ヘッドレスエンドポイントとREST配信エンドポイントを提供しています。

典型的なユースケースは、マーケティングモジュール用にコンテンツノードまたはコンテンツフラグメントを配信することです。

>[!ENDSHADEBOX]

+++ Magnoliaの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* インスタンス URLとトークンまたは基本的な認証。配信のワークスペースとパス。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* REST配信URLは、インストールされているMagnolia モジュールと設定によって異なります。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 モジュールが公開するパブリック配信URL パターンを使用し、Magnolia ガイダンス（匿名の配信と保護されたコンテンツのトークン）ごとに認証し、サンプル JSONの貼り付け、フィールドのマッピング、テスト、アクティベートを行います。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Magnolia REST （配信）を使用してエンドポイントを設定します。 URL パターンの例：

   `https://{author-or-public}/.rest/delivery/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

パターンの例：`https://{domain}/magnoliaAuthor/.rest/delivery/...`またはパブリック配信ツアースタイルのURL。 パスは、インストール済みのモジュールによって異なります。 [Magnolia ドキュメント &#x200B;](https://docs.magnolia-cms.com/){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `http://{{your-domain}}/magnoliaAuthor/.rest/delivery/<myEndpoint>/travel/@nodes` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| Content-Type | Content-Type | 定数 | application/json | はい（オン） |
| Accept | Accept | 定数 | application/json | はい（オン） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | 認証 | `<bearer_token>` | ヘッダー |

注意：配信APIは、ログインを必要としないコンテンツにrest-anonymous役割を使用することです。 保護されたデータへの安全なアクセスには、API トークンやOAuth 2.0などのより堅牢な方法が適しています。

+++


## ロイヤルティとリワード {#loyalty-and-rewards}

### Voucherify {#voucherify}

>[!BEGINSHADEBOX]

Voucherifyは、プロモーションとロイヤルティ REST API （キャンペーン、バウチャー、ロイヤルティプログラム）を提供します。

一般的なユースケースには、コンテンツのオファーに対して「ロイヤルティ」や「プロモーションの状態」を読み、適切な場合は「レベル」や「バランス」を表示することが含まれます。

>[!ENDSHADEBOX]

+++ Voucherifyの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* アプリケーション IDと秘密鍵（地域/クラスターごと）。呼び出すロイヤルティまたはキャンペーンエンドポイントを明確にします。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* 顧客向けエラーやメッセージコンテンツで、内部プロモーションやキャンペーンの識別子を公開しないようにする。
* アプリケーションレベルのレート制限が適用されます。 Voucherify ガイダンスごとに再試行とキャッシュを設定します。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 クラスターのベース URLの設定、必須ヘッダー（`X-APP-ID`、`X-APP-TOKEN`）の追加、フィルターまたはIDを使用したリスト エンドポイントの制約、サンプル JSONの貼り付け、フィールドのマッピング、テスト、アクティベート。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. ロイヤルティ / REST APIを使用してエンドポイントを設定します。 [Voucherify](https://docs.voucherify.io/){target="_blank"}ごとに、お住まいの地域の&#x200B;**クラスター**&#x200B;のホストとパスを設定します。 URL パターンの例：

   `https://{cluster}.voucherify.io/`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

統合フィールドのサンプル。 完全な参照：[Voucherify API](https://docs.voucherify.io/reference/introduction){target="_blank"}。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{cluster}}.voucherify.io/v1/loyalties/{{campaignId}}/members` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `cluster` | `cluster` | `<your_cluster>` |
| `campaignId` | `campaignId` | `<loyalty_campaign_Id>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |
| X-APP-ID | X-APP-ID | 定数 | `<YOUR-APP-ID>` | はい（オン） |
| X-Voucherify-Channel | X-Voucherify-Channel | 定数 | Voucherify Documentation | いいえ（オフ） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `limit` | `limit` | 変数 | 10 | いいえ（オフ） |
| `page` | `page` | 変数 | 1 | いいえ（オフ） |
| `customer` | `customer` | 変数 | `<customer_identifier>` | いいえ（オフ） |
| `created_at` | `created_at` | 変数 | `<iso8601_date>` | いいえ（オフ） |
| `updated_at` | `updated_at` | 変数 | `<iso8601_date>` | いいえ（オフ） |
| `order` | `order` | 変数 | `<sort_field>` | いいえ（オフ） |
| `code` | `code` | 変数 | `<loyalty_card_code>` | いいえ（オフ） |
| `ids` | `ids` | 変数 | `<array_of_ids>` | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | X-APP-TOKEN | `<YOUR-APP-TOKEN>` | ヘッダー |

+++

### Talon.One {#talon-one}

>[!BEGINSHADEBOX]

Talon.Oneは、セッション、エフェクト、プロファイル用のREST APIを備えたプロモーションおよびロイヤルティルールエンジンです。

一般的なユースケースには、パーソナライズされたコンテンツやロイヤルティの進捗状況、特典表示における、カートまたはプロファイルレベルでのプロモーションが含まれます。

>[!ENDSHADEBOX]

+++ Talon.Oneの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API キーとデプロイメント固有のベース URL。アプリケーションまたはキャンペーンのスコープの識別子。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* セッション量の多いフローでは、統合リクエストモデルへの慎重なマッピングが必要になる場合があります。
* Talon.Oneのレート制限とidempotency ガイダンスを確認してください。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 必要なプロファイルまたは達成パスで&#x200B;**GET**&#x200B;を使用し、`Authorization: ApiKey-v1 <key>`を文書化して設定し、サンプル JSONを貼り付け、フィールドをマップし、テストしてアクティブ化します。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Talon.One統合APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://{your-domain}.talon.one/v1/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{your-deployment}}.talon.one/v1/customer_profiles/{{integrationId}}/achievements/{{achievementId}}` |
| **HTTP メソッド** | `GET` |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `your-deployment` | `your-deployment` | `<your_deployment>` |
| `integrationId` | `integrationId` | `<integrationId>` |
| `achievementId` | `achievementId` | `<achievementId>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `progressStatus` | `progressStatus` | 変数 | 進行中/完了/期限切れ | いいえ（オフ） |
| `startDate` | `startDate` | 変数 | 2024-05-29T15:04:05+07:00 | いいえ（オフ） |
| `endDate` | `endDate` | 変数 | 2024-05-29T15:04:05+07:00 | いいえ（オフ） |
| `pageSize` | `pageSize` | 変数 | `<default_page_size>` | いいえ（オフ） |
| `skip` | `skip` | 変数 | `<items_to_skip>` | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | 認証 | ApiKey-v1 `<YOUR_API_KEY>` | ヘッダー |

+++

### アンタボ {#antavo}

>[!BEGINSHADEBOX]

Antavoは、メンバー、報酬、イベント用のREST APIを備えたエンタープライズロイヤルティプラットフォームです。

典型的なユースケースとしては、電子メールやプッシュ通知、オファーに対するポイント、階層、報酬などが挙げられます。

>[!ENDSHADEBOX]

+++ Antavoの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* URLとAPIの資格情報をスタックします。必要に応じて、プログラムまたはショップの識別子を指定します。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* お客様のPIIは、Antavo契約およびお客様のプライバシーポリシーに基づいて処理する必要があります。
* お使いの環境に合わせて、APIのバージョンと安定したエンドポイントをAntavoで確認します。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 ベンダーの認証（クエリのAPI キーなど）を使用して&#x200B;**GET**&#x200B;を設定し、ポリシーに対するPIIの公開を避け、サンプル JSONを貼り付け、フィールドをマッピングし、テストしてアクティブ化します。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Antavo Enterprise APIを使用してエンドポイントを設定します。

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

統合フィールドのサンプルには、**ステージング** ホストが使用されます。実稼動では、Antavo スタック ホスト名が使用されます。 [Antavo ドキュメント &#x200B;](https://antavo.com/docs/){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://api.staging.antavo.com/customers/{{customer_id}}/activities/offers` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `customer_id` | `customer_id` | `<customer_id>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |
| Accept | Accept | 定数 | application/json | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | `api_key` | `<YOUR_API_KEY>` | クエリパラメーター |

+++

### Salesforceロイヤルティ {#salesforce-loyalty}

>[!BEGINSHADEBOX]

Salesforce Loyalty Managementは、メンバー、プログラム、トランザクション用に、Salesforce プラットフォームでREST APIを公開します。

一般的なユースケースには、ジャーニーの階層、ポイント、メリットを明らかにし、メッセージとCRM データやロイヤルティデータを連携させることが含まれます。

>[!ENDSHADEBOX]

+++ Salesforce ロイヤルティの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* Salesforceインスタンス、接続アプリや統合ユーザー、組織に適したOAuth。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* Salesforce APIの制限とOAuth トークンの更新は、統合に設計する必要があります。
* API応答に表示されるフィールドを管理する、フィールドレベルのセキュリティおよび共有ルール。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 チームが承認したロイヤルティ統合エンドポイントを使用して、Salesforce OAuthを完成させ、サンプル JSONをペーストし、フィールドをマッピングし、複合APIの制限を尊重し、テストし、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Salesforce Loyalty Management RESTを使用してエンドポイントを設定します。 URL パターンの例：

   `https://{instance}.salesforce.com/services/data/vXX.X/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

組織のAPI バージョンについて文書化されたロイヤルティ管理&#x200B;**メンバープロファイル** GET操作を使用します。パスには、プログラムとメンバーのIDが含まれます。 [Salesforce developers](https://developer.salesforce.com/){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{your-instance}}.my.salesforce.com/services/data/{{version}}/connect/loyalty/management/members` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `your-instance` | `your-instance` | `<your_instance>` |
| `version` | `version` | `version` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |
| Accept | Accept | 定数 | application/json | いいえ（オフ） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `membershipNumber` | `membershipNumber` | 変数 | `<membership_number>` | いいえ（オフ） * |
| `membershipId` | `membershipId` | 変数 | `<membership_id>` | いいえ（オフ） * |
| `posMemId` | `posMemId` | 変数 | `<pos_mem_id>` | いいえ（オフ） * |

\* 3つのうち少なくとも1つは必要です。

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | 認証 | `<access_token>` | ヘッダー |

+++

### キャピラリー {#capillary}

>[!BEGINSHADEBOX]

キャピラリーは、小売スタックで一般的なロイヤルティおよびエンゲージメント APIを提供します。

一般的なユースケースには、パーソナライズされたジャーニー内のポイント、層、オファーなどがあります。

>[!ENDSHADEBOX]

+++ Capillaryの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API ホストと認証（多くの場合、署名済みリクエスト、Capillaryのドキュメントに従う）。
* エンドポイントのプログラム識別子。

次の制限事項と除外事項が適用されます。

* 認証スキームと地域ホストは、デプロイメントによって異なります。 お使いのスタックのキャピラリーで確認します。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 必要に応じて`CAP-API-ACCESS-TOKEN`などのヘッダーを設定し、サンプル JSONを貼り付け、フィールドをマッピングし、テストし、アクティブ化します。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Capillary APIを使用してエンドポイントを設定します。

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

例：`https://ushc.intouch.capillarytech.com/api/v3/rewards/{reward_id}` （ホストは地域によって異なります）。 ホストと認証スキームを[&#x200B; キャピラリー](https://capillarytech.com/){target="_blank"}で検証します。


| フィールド | 値 |
| --- | --- |
| **URL** | `https://ushc.intouch.capillarytech.com/api/v3/rewards/{{reward_id}}` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `reward_id` | 特典ID | `<your_reward_id>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| Content-Type | Content-Type | 定数 | application/json | はい（オン） |
| CAP-API-ACCESS-TOKEN | アクセストークン | 定数 | `<YOUR_ACCESS_TOKEN>` | はい（オン） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | CAP-API-ACCESS-TOKEN | `<YOUR_ACCESS_TOKEN>` | ヘッダー |

+++


## テンプレートとメッセージ {#templates-and-messaging}

### ステンスル {#stensul}

>[!BEGINSHADEBOX]

Stensulは、承認済みテンプレート用のメール作成プラットフォームです。Journey Optimizerは、APIを介してテンプレートメタデータと構造化リージョンを使用できます。

一般的なユースケースには、承認済みテンプレートのインポートや地域のプロファイル属性へのマッピング、管理されたブロックの再利用によるスケーラブルなキャンペーン構築などが含まれます。

>[!ENDSHADEBOX]

+++ Stensulの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API アクセス機能を備えたStensul アカウントと、定義されたトークンを備えた公開テンプレート。
* Journey Optimizerの管理者アクセス権にアクセスして、統合を作成できます。

次の制限事項と除外事項が適用されます。

* ここでは、Journey Optimizer内のStensul テンプレートのインプレースでのWYSIWYG編集については説明しません。
* テンプレートペイロード内の大規模または複雑なHTMLでは、セキュリティレビューとサニタイズが必要になる場合があります。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. 統合名を入力します。

1. Stensul テンプレート API URLを使用してエンドポイントを設定します。 URL パターンの例：

   `https://api.stensul.com/v1/templates/{template_id}`

1. 認証を設定します（Stensul API ドキュメントごとのAPI キーまたはOAuth）。

1. パス変数（テンプレート IDなど）を定義します。

1. フィールド検出用のサンプル JSON応答を貼り付けます。

1. 必須テンプレートフィールドをJourney Optimizer パーソナライゼーションフィールドにマッピングします。

1. 接続をテストしてアクティブ化します。

### マリゴールド {#marigold}

>[!BEGINSHADEBOX]

Marigoldは、ロイヤルティおよびエンゲージメント APIを公開します。ホストは、地域によって異なります（EUと米国のモジュールホスト名）。

典型的なユースケースは、マリーゴールドプログラムからのロイヤルティデータや嗜好データを利用したメッセージの強化です。

>[!ENDSHADEBOX]

+++ Marigoldの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* 契約のベース URLと資格情報。可能な場合は最小権限API ユーザー。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* エンドポイントはMarigold製品によって異なります。 お客様のデプロイメントにMarigold サポートを使用した検証。
* 個人情報は、DPAおよび保持ポリシーに準拠する必要があります。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 お住まいの地域のMarigold ホストを指定し、認証を設定します（以下のサンプルでは、キーと秘密鍵を使用して`X-Api-Key`を使用しています）。サンプル JSONを貼り付け、フィールドをマップし、テスト、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Marigold REST APIを使用してエンドポイントを設定します。

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

1. Marigoldは、顧客インスタンスがアクティブな地理的領域に基づいて2つのエンドポイントを使用します。

   * ヨーロッパ：`https://{{customername}}.module.slgnt.eu`
   * 米国：`https://{{customername}}.module.slgnt.us`

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

ベース ホストは地域によって異なります（例：`https://{{customername}}.module.slgnt.eu`または`https://{{customername}}.module.slgnt.us`）。 導入時にMarigoldでパスを確認する。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{customername}}.module.slgnt.{{locale}}/Portal/Api/organizations/{{organization}}/content/{{api_name}}` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `customername` | `customername` | `<your_name>` |
| `locale` | `locale` | `eu` / `us` |
| `organization` | `organization` | `<your_organization>` |
| `api_name` | `api_name` | `<api_name>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | X-Api-Key | `<apiKey>:<apiSecret>` | ヘッダー |

+++

### Adobe Targetの推奨事項 {#adobe-target-recommendations}

>[!BEGINSHADEBOX]

Adobe Targetには、使用権限に応じて、サーバーサイドまたは統合されたエクスペリエンス向けのレコメンデーションおよび配信APIが含まれています。

一般的なユースケースには、Journey Optimizerで作成したエクスペリエンスにレコメンデーションを挿入したり、プロファイルやExperience Platformのコンテキストとキーを整合させたりすることが含まれます。

>[!ENDSHADEBOX]

+++ Adobe Target Recommendationsの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* Recommendations; IMS組織とサポートされる認証を使用してターゲットを設定します。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* レコメンデーションおよび配信APIには、特定のパラメーター（mboxや製品識別子など）が必要です。 Adobe Targetのドキュメントに従ってください。
* 送信ボリュームとユースケースに合わせて、待ち時間とキャッシュを調整します。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 配信の呼び出しは、多くの場合、**POST**&#x200B;とJSON本文で行われます。 [&#x200B; ターゲット認証](https://experienceleague.adobe.com/en/docs/target-dev/developer/api/configure-authentication){target="_blank"}ごとにOAuthを設定し、サンプル応答を貼り付け、フィールドをマッピングし、想定されるボリュームでテストします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Target Recommendations / delivery APIを使用してエンドポイントを設定します。

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{client}}.tt.omtrdc.net/rest/v1/delivery` |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |
| **HTTP メソッド** | `POST` |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `client` | `client` | `<client_name>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| クライアント | クライアント | 変数 | `<customer_client_code>` | はい（オン） |
| sessionId | sessionId | 変数 | ` <session_identifier>` | はい（オン） |

**認証**

[Target認証設定](https://experienceleague.adobe.com/en/docs/target-dev/developer/api/configure-authentication)を参照し、JSONをペイロードに追加してください。

**要求ペイロード**

```Sample Request Payload JSON
{
  "id": {
    "tntId": "<YOUR_TENANT_ID>"
  },
  "context": {
    "channel": "web",
    "address": {
      "url": "https://example.com/store.html"
    },
    "screen": {
      "width": 1200,
      "height": 1400
    }
  },
  "experienceCloud": {
    "analytics": {
      "logging": "server_side",
      "supplementalDataId": "<supDataId>",
      "trackingServer": "sstats.adobe.com"
    }
  },
  "execute": {
    "pageLoad": {
      "parameters": {
        "pageType": "checkout",
        "preferredCurrency": "$"
      }
    },
    "mboxes": [
      {
        "index": 1,
        "name": "orderConfirmPage"
      }
    ]
  },
  "prefetch": {
    "views": [
      {
        "parameters": {
          "ad": "view"
        }
      }
    ],
    "mboxes": {
      "index": 1,
      "name": "SummerOffer"
    }
  }
}
```

+++


## データ、天候、運用 {#data-weather-and-operations}

### AccuWeather {#accuweather}

>[!BEGINSHADEBOX]

AccuWeatherは、予測および場所のREST APIを公開して、メッセージに天候に応じたスニペットを含めることができます。

一般的なユースケースには、電子メールやプッシュ通知での短い予測や、プロファイルやコンテキストに関連する予測値を使用したコンテンツのカスタマイズなどがあります。

>[!ENDSHADEBOX]

+++ AccuWeatherの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* APIのサブスクリプションとキー、位置情報キーまたは都市検索フロー。
* Journey Optimizerの管理者アクセス権にアクセスして、統合を作成できます。

次の制限事項と除外事項が適用されます。

* AccuWeather サブスクリプション層のJSON応答形状を確認します。統合は、JSON応答からフィールドをマッピングします。
* AccuWeatherのレート制限と推奨されるキャッシュを確認します。
* `locationKey`を解決するには、多くの場合、予測呼び出しの前に別の位置情報または都市検索リクエストが必要です。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 サブスクリプションで必要な場合を除き、**GET**&#x200B;を使用します。プロファイル/コンテキストから`apiKey` クエリパラメーター、マップ `locationKey`およびその他の変数を添付し、サンプル JSONを貼り付け、フィールドをマッピングしてからテストします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Daily Forecasts APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://dataservice.accuweather.com/forecasts/v1/daily/{days}day/{locationKey}`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++統合フィールドの例

統合フィールドのサンプル。 詳細と階層については、[AccuWeather API](https://developer.accuweather.com/apis){target="_blank"}を参照してください。 `locationKey`は、別の場所の検索呼び出し（例：`.../locations/v1/cities/search?q={{cityName}}`）で解決することがよくあります。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://dataservice.accuweather.com/forecasts/v1/daily/{{days}}day/{{locationKey}}` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `days` | `days` | `15` |
| `locationKey` | `locationKey` | `<desired_location_key>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `format` | `format` | 変数 | json | いいえ（オフ） |
| `language` | `language` | 変数 | en-US | いいえ（オフ） |
| `details` | `details` | 変数 | False | いいえ（オフ） |
| `metric` | `metric` | 変数 | False | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | `apiKey` | `<YOUR_API_KEY>` | クエリパラメーター |

+++

### ShipStation {#shipstation}

>[!BEGINSHADEBOX]

ShipStationでは、配送業者、ラベル、トラッキング用の配送APIと注文APIを提供しています。

一般的なユースケースには、注文状況、トラッキングリンク、トランザクションメッセージの配信ETAなどがあります。

>[!ENDSHADEBOX]

+++ ShipStationの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API キーと秘密鍵（ShipStation ドキュメントごとの基本認証）。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* メッセージコンテンツでShipStation API キーを公開しないでください。統合設定でのみ資格情報を保持します。
* ページ化されたリストエンドポイントは、統合には適していない可能性があります。可能な場合は、シングルリソース GETを優先します。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 必要なリソース（注文と出荷）をターゲットにし、[ShipStation API](https://www.shipstation.com/docs/api/){target="_blank"}ごとに認証し、サンプル JSONを貼り付け、フィールドをマップし、テストし、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. ShipStation REST APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://ssapi.shipstation.com/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

次の&#x200B;**Get Timer**&#x200B;の例は、ShipStation オートメーションのタイミング呼び出しを1つ示しています。 Journey Optimizerで再現する場合は、ShipStation統合ガイドの正確なパスと認証を使用してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://dashboard.sendtric.com/api/v1/timers/{{id}}` |
| **HTTP メソッド** | `POST` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | apiKey | `<your_api_key>` | ヘッダー |

**ペイロードのリクエスト**

```Sample Request Payload
{
    "external_batch_id": "se-28529731",
    "batch_notes": "This is my batch",
    "shipment_ids": [
      "se-28529731"
    ],
    "rate_ids": [
      "se-28529731"
    ]
}
```

+++

### RevenueCat {#revenuecat}

>[!BEGINSHADEBOX]

RevenueCatは、アプリのサブスクリプションステータスと使用権限APIを提供します。

典型的なユースケースは、ポリシーで許可されているライフサイクルキャンペーンにサブスクリプションの状態を反映することです。

>[!ENDSHADEBOX]

+++ RevenueCatの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* 秘密のAPI キーとアプリ識別子。プロファイルとRevenueCat顧客ID間の安定したマッピング。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* シークレット API キーを保護し、ローテーション ポリシーに従います。
* 購読データと使用権限データは機密性が高い： プライバシーと同意の要件を満たす。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 以下にモデル化したREST **GET**&#x200B;を呼び出し、秘密鍵ヘッダーで認証し、サンプル JSON、マップフィールド、テスト、アクティベートを貼り付けます。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. RevenueCat REST APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://api.revenuecat.com/v1/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

パターンの例：[RevenueCat ドキュメント &#x200B;](https://docs.revenuecat.com/){target="_blank"}のRevenueCatの&#x200B;**製品**&#x200B;または同等の製品/使用権限GETを、プロジェクトのベース URLとバージョンと共に使用します。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://api.revenuecat.com/projects/{{project_id}}/products/{{product_id}}` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `project_id` | `project_id` | `<project_id>` |
| `product_id` | `product_id` | `<product_id>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `country` | `country` | 変数 | `<iso_country_code>` | いいえ（オフ） |
| `locale` | `locale` | 変数 | `<locale_code>` | いいえ（オフ） |
| `parentId` | `parentId` | 変数 | `<parent_category_id>` | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | 認証 | `Bearer <token>` | ヘッダー |

+++

### Databricks {#databricks}

>[!BEGINSHADEBOX]

Databricksは、レイクハウス データに対してSQL APIとREST APIを提供します。以前のドラフトでは、結合されたステートメント実行ガイダンスと&#x200B;**jobs/get** サンプルを使用していました。

典型的なユースケースは、最小限の権限でパーソナライズするために、管理されたテーブルからの小さな非正規化属性を使用することです。

>[!ENDSHADEBOX]

+++ Databricksの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* Workspace ホスト、トークン、または組織ごとのOAuth ポリシー、最小限のスコープを持つサービスプリンシパル。
* Journey Optimizerでの管理者アクセス：

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 狭い読み取りパスを優先します。**POST** ステートメントの実行を使用する場合は、APIが必要とするJSON本文を含め、マッピング用に成功レスポンスのサンプルを貼り付け、待ち時間を慎重にテストし、アクティブ化します。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Databricks SQL ステートメント実行APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://{workspace-host}/api/2.0/sql/statements/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++統合フィールドの例

以下の&#x200B;**GET** ジョブの例は実例です。SQL ドリブン型のパーソナライゼーションの場合は、ワークスペースがサポートする[&#x200B; ステートメント実行API](https://docs.databricks.com/api/workspace/statementexecution){target="_blank"} パターンを優先します。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://<databricks-instance>/api/2.0/jobs/get` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |
| 認証 | OAuth |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| Accept | Accept | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `job_id` | `job_id` | 変数 | `12` | ○ |

+++

## レビュー、同意、ソーシャル {#reviews-consent-and-social}

### バインダー {#bynder}

>[!BEGINSHADEBOX]

BynderはREST APIを備えたDAMです。統合では、一般的に、読み取り専用のメタデータまたはアセット URLにOAuth 2.0を使用します。

一般的なユースケースには、アセットのメタデータや配信URLをメッセージに取り込み、Bynderでクリエイティブをジャーニーに沿って承認することです。

>[!ENDSHADEBOX]

+++ Bynderの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* ポータル ドメインとOAuth クライアント（または承認済みのトークン アプローチ）。
* 読み取り専用アクセスの範囲、Journey Optimizerでの管理者アクセス。

次の制限事項と除外事項が適用されます。

* ページネーションとOAuth トークンの更新は、BynderのAPI ルールに従う必要があります。
* 大きなページ分割された応答：パーソナライゼーションに必要なフィールドのみをマッピングします。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 選択したエンドポイントで&#x200B;**GET**&#x200B;を設定し（1つの一般的なパターンはユーザーリストです）、[Bynder](https://developer.bynder.com/){target="_blank"}ごとにOAuthを完了し、データの不要なページを引き出すのを避け、フィールドをマッピングし、テストしてからアクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Bynder API v4を使用してエンドポイントを設定します。 URL パターンの例：

   `https://{your-bynder-domain}/api/v4/users/`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

統合フィールドのサンプル。 OAuth 2.0 ペイロードの詳細については、[Bynder API ドキュメント &#x200B;](https://developer.bynder.com/){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{your-bynder-domain}}/api/v4/users/` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `your-bynder-domain` | `your-bynder-domain` | `<your-bynder-domain>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |
| 認証 | 認証 | 定数 | ベアラー`<token>` | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `includeInActive` | `includeInActive` | 変数 | False | いいえ（オフ） |
| `limit` | `limit` | 変数 | 100 | いいえ（オフ） |
| `page` | `page` | 変数 | 1 | いいえ（オフ） |

**認証**

| タイプ | ペイロード |
| --- | --- |
| OAuth 2.0 | OAuth 2.0 ペイロード （Bynderのドキュメントを参照） |

```
{
    "type": "oauth2",
    "endpoint": {
        "uri": ""
    },
    "method": "get",
    "response": {
        "type": "json"
    },
    "request": {
        "header": [
            {
                "key": "client_id",
                "value": ""
            },
            {
                "key": "client_secret",
                "value": ""
            }
        ],
        "queryParams": [
            {
                "key": "grant_type",
                "value": ""
            },
            {
                "key": "scope",
                "value": ""
            }
        ],
        "payload": {
            "type": "json",
            "content": {}
        }
    },
    "credentialPaths": [
        "header.client_id",
        "header.client_secret",
        "queryParam.scope"
    ],
    "tokenPath": "message.token",
    "policy": {
        "timeoutInMilliseconds": 30000,
        "cache": {
            "enabled": true,
            "ttlInSeconds": 300
        },
        "retry": {
            "enabled": false
        }
    },
    "locationConfig": {
        "key": "x-token",
        "location": "query"
    }
}
```

+++

### Trustpilot {#trustpilot}

>[!BEGINSHADEBOX]

Trustpilotは、ユースケースと契約が許可するビジネスとレビューの概要データ用のAPIを提供します。

一般的なユースケースとしては、Trustpilotの条件に準拠したマーケティングコンテンツのレビュー数や評価が表示されます。

>[!ENDSHADEBOX]

+++ Trustpilotの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API キーと承認済みのユースケース、クエリのビジネス識別子。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* Trustpilot データの使用は、Trustpilotのブランディングおよびデータ使用ポリシーに準拠する必要があります。
* レート制限は、概要と関連するエンドポイントのレビューに適用されます。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 必須のクエリ認証を使用して&#x200B;**GET**&#x200B;を設定し、プロファイルまたはコンテキストからIDをマッピングし、サンプル JSON、マップフィールド、テスト、アクティベートを貼り付けます。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Trustpilot APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://api.trustpilot.com/v1/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

統合パターンには、[Trustpilot開発者](https://developers.trustpilot.com/){target="_blank"}のカテゴリ リスト操作を使用します。パラメーターはリソースによって異なります。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://api.trustpilot.com/v1/categories` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `country` | `country` | 変数 | `<iso_country_code>` | いいえ（オフ） |
| `locale` | `locale` | 変数 | `<locale_code>` | いいえ（オフ） |
| `parentId` | `parentId` | 変数 | `<parent_category_id>` | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | apiKey | `<your_api_key>` | ヘッダー |

+++

### Bazaarvoice {#bazaarvoice}

>[!BEGINSHADEBOX]

Bazaarvoiceは評価、レビュー、UGC APIを提供しています。

典型的なユースケースは、ポリシーで許可されている場合に、レビューの概要や評価をメールで表示することです。

>[!ENDSHADEBOX]

+++ Bazaarvoiceの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* 契約のAPI パスキーとクライアント ID。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* 評価やレビューの表示はBazaarvoiceのコンテンツポリシーに従う必要があります。
* レート制限とキャッシングルールは、API キーごとに適用されます。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 **GET**&#x200B;を`passkey`と共にConversations APIのクエリパラメーターとして使用し、`Accept: application/json`を設定し、サンプル JSONを貼り付け、フィールドをマップし、テストし、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Bazarvoice Conversations APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://api.bazaarvoice.com/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

例エントリポイント：`https://api.bazaarvoice.com/data/products.json`、バージョンおよびフィルタークエリパラメーター。 [Bazaarvoice developer](https://developer.bazaarvoice.com/){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://api.bazaarvoice.com/data/products.json` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| Accept | Accept | 定数 | application/json | はい（オン） |

**認証**

| タイプ | キー値 | ロケーション |
| --- | --- | --- |
| パスキー | `<YOUR_ACCESS_TOKEN>` | クエリパラメーター |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `apiversion` | apiversionNumber | 定数 | 5.4 | はい（オン） |
| `filter` | `filter` | 変数 | Id:47950830 | いいえ（オフ） |
| `stats` | `stats` | 変数 | すべて | いいえ（オフ） |

+++

### OneTrust {#onetrust}

>[!BEGINSHADEBOX]

OneTrustは、プライバシーおよび同意API （製品固有のURLとスキーマ）を公開しています。

典型的なユースケースは、アーキテクチャと法律のレビューが許可する条件付きコンテンツの同意や嗜好シグナルを読むことです。

>[!ENDSHADEBOX]

+++ OneTrustの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* API資格情報と地域ベース URL。メッセージで使用されるフィールドの法的承認。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* 同意や嗜好データは厳しく規制されています。 法務部門とプライバシー部門の連携。
* API パスとペイロードは、OneTrust製品によって異なります。 サブスクリプションのドキュメントを使用します。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 公開されたスキーマまたは環境設定センターのパスを使用して、サブスクリプションドキュメントを作成し、必要に応じてOAuthを完了し、サンプル JSON、マップフィールド、テスト、アクティベートを貼り付けます。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. OneTrust APIを使用してエンドポイントを設定します。 テナント、製品、およびパスは、サブスクリプションの[OneTrust](https://developer.onetrust.com/){target="_blank"} ドキュメントに記載されています。 URL パターンの例：

   `https://{tenant}.my.onetrust.com/api/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

| フィールド | 値 |
| --- | --- |
| **URL** | `https://customer.my.onetrust.com/api/consentmanager/v2/preferencecenters/{{preferencecenterid}}/schema` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| **認証** | OAuth |

**パスパラメーター**

| パラメーター | 名前 | 値 |
| --- | --- | --- |
| `preferencecenterid` | `preferencecenterid` | `<pref-id>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| Accept | Accept | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `state` | `state` | 定数 | 公開日 | ○ |

+++

#### プリファレンスセンタースキーマ（公開）

パターン （フラグメント）の例：`https://{tenant}.my.onetrust.com/api/consentmanager/v2/preferencecenters/{preferencecenterid}/schema?state=PUBLISHED`。 [OneTrust Developer](https://developer.onetrust.com/){target="_blank"}で正確なパスを確認します。

### Meta {#meta}

>[!BEGINSHADEBOX]

Metaのグラフおよびマーケティング APIは、承認済みのビジネス統合のために、カタログとキャンペーンオブジェクトを公開します。

典型的なユースケースは、トークンとポリシーが許可するMetaの属性を使用してコンテンツを強化することです。

>[!ENDSHADEBOX]

+++ Metaの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* 正しい権限を持つシステムユーザーまたはアプリトークン。Business Managerの調整。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* 短期間有効なアクセストークンには、サーバーサイドの統合に適した更新または長期間有効な戦略が必要です。
* Meta Platformの条件に準拠します。メッセージペイロードにトークンやその他のシークレットを記録しないでください。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 グラフ呼び出しは、多くの場合、**GET**&#x200B;でバージョン管理されたパスを持ちます。トークンの有効期限を処理し、サンプル JSONを貼り付け、フィールドをマップし、テストしてアクティブ化します。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Meta Graph APIを使用してエンドポイントを設定します。 URL パターンの例：

   `https://graph.facebook.com/vXX.X/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

統合フィールドのサンプル。 バージョン管理とアクセストークンについては、[Graph API](https://developers.facebook.com/docs/graph-api){target="_blank"}を参照してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://graph.facebook.com/{{API_VERSION}}/{{PRODUCT_CATALOG_ID}}/products` |
| **HTTP メソッド** | `GET` |
| 応答ペイロード | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |
| ポリシー | 必要に応じてポリシーレベルの詳細を設定します。 |
| 認証 | OAuth |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `API_VERSION` | `API_VERSION` | `v19.0` |
| `PRODUCT_CATALOG_ID` | `PRODUCT_CATALOG_ID` | `12345` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| Accept | Accept | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `fields` | `fields` | 変数 | ID | × |
| `filter` | `filter` | 変数 | — | × |

+++

### Aprimo {#aprimo}

>[!BEGINSHADEBOX]

Aprimoは、レコード、アセット、メタデータのマーケティング業務とDAM APIを組み合わせています。

一般的なユースケースには、動的コンテンツの承認済みレコードやアセットフィールド、規制の厳しい業界における管理されたDAM ワークフローなどがあります。

>[!ENDSHADEBOX]

+++ Aprimoの前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* テナント URLと資格情報（設定ごとにOAuthまたはAPI キー）。
* Journey Optimizerでの管理者アクセス：

次の制限事項と除外事項が適用されます。

* Aprimoのフィールドレベルのセキュリティは、Journey Optimizerでマッピングする属性と一致している必要があります。
* 大規模なHALまたはJSON ペイロード：マッピングされたフィールドを最小必要セットに制限します。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 必要なレコードパスに&#x200B;**GET**&#x200B;を使用し、`API-VERSION`などの必須ヘッダーを送信し、サンプル JSON （返されたHALまたはJSON）を貼り付け、最小限のフィールドセットをマッピングし、テストし、アクティベートします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Aprimo DAM / Records APIを使用してエンドポイントを設定します。 **テナント**&#x200B;のAPI ベース URLとレコードパスを使用します（Aprimoごとに）。 URL パターンの例：

   `https://{tenant}.dam.aprimo.com/`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

| フィールド | 値 |
| --- | --- |
| **URL** | `https://productstrategy1.dam.aprimo.com/api/core/record/{{recordID}}` |
| **HTTP メソッド** | `GET` |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `recordId` | `recordId` | `<record_identifier>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |
| API-VERSION | API-VERSION | 定数 | 1 | はい（オン） |
| Accept | Accept | 定数 | application/hal+jsonまたはapplication/json | いいえ（オフ） |
| select-record | select-record | 変数 | `<selection_type>` | いいえ（オフ） |
| select-record-fields | select-record-fields | 変数 | `<field_list>` | いいえ（オフ） |
| select-field | select-field | 変数 | `<field_selection>` | いいえ（オフ） |

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | 認証 | ベアラー`<token>` | ヘッダー |

+++

### イプシロン（Epsilon3） {#epsilon}

>[!BEGINSHADEBOX]

Epsilonはエンタープライズ契約ごとにAPIを公開します。ベース URLと認証はアカウントチームから取得されます（以下のEvents APIの例は実例です）。

典型的なユースケースは、サポートされているJSON APIを通じてロイヤルティまたはオファー属性を公開することです。

>[!ENDSHADEBOX]

+++ Epsilon （Epsilon3）の前提条件と制限事項について詳しく説明します。

次の前提条件が適用されます。

* Epsilonの資格情報とエンドポイント、Journey Optimizerの管理者アクセス。

次の制限事項と除外事項が適用されます。

* エンドポイントとホストは顧客ごとに異なります。 Epsilon アカウントチームからのドキュメントなしでデプロイしないでください。

+++

Journey Optimizerでこの統合を設定するには、次の手順を使用します。 リクエストの詳細については、**統合フィールドのサンプル**&#x200B;を参照し、これらの値を環境のベンダードキュメントで確認してください。

1. [統合の操作](integrations.md)に従います。 公開URLを推測しないでください。 Epsilonの仕様を使用し、サンプル JSONを貼り付け、フィールドをマッピングし、テストし、アクティブにします。

1. Journey Optimizerで、**[!UICONTROL Configurations]** > **[!UICONTROL Manage]**&#x200B;に移動し、**[!UICONTROL Create Integration]**&#x200B;を選択します。

1. スペースなしで統合名を入力します。

1. Epsilon APIを使用してエンドポイントを設定します（統合仕様に従います）。 ベース URLとリソースパスは、Epsilon アカウントチームによって提供されます。 URL パターンの例：

   `https://{your-instance}.epsilon3.io/api/...`

1. 設定テーブルに表示されるHTTP メソッド（通常はGET）を選択します。特に指定がない限り、このメソッドを選択します。

1. テーブルおよびベンダードキュメントで指定されたとおりに認証（ヘッダー、クエリパラメーター、OAuth）を正確に設定します。

1. パス、クエリ、ヘッダーのパラメーターを定義し、必要に応じて変数をプロファイルデータやコンテキストデータにマッピングできます。

1. フィールドを検出してマッピングできるように、サンプル JSON応答を貼り付けます。

1. 応答ペイロードマッピングでパーソナライゼーションに必要なフィールドを選択します。

1. 予想されるボリュームに基づいて、タイムアウト、再試行、およびキャッシングポリシーを設定します。

1. 接続をテストし、統合をアクティブ化します。

次の表に、この統合リクエストの値の例を示します。

+++ 統合フィールドの例

パターンの例：`https://{your-instance}.epsilon3.io/api/v1/planning/events`、クエリ パラメーター`start`および`end`とヘッダーベースのAPI キー。 生産前にEpsilonで確認してください。

| フィールド | 値 |
| --- | --- |
| **URL** | `https://{{your-instance}}.epsilon3.io/api/v1/planning/events` |
| **HTTP メソッド** | `GET` |
| **ポリシー** | 必要に応じてポリシーレベルの詳細を設定します。 |
| **応答ペイロード** | API応答に基づいて、オーサリング中に使用する必要な応答フィールドを選択して設定します。 |

**パスパラメーター**

| パスパラメーター | 名前 | デフォルト値 |
| --- | --- | --- |
| `your-instance` | `your-instance` | `<your_instance>` |

**ヘッダー**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| コンテンツタイプ（デフォルト） | Content-Type | 定数 | application/json | はい（オン） |

**クエリパラメータ**

| パラメーター | 名前 | タイプ | 値 | 必須 |
| --- | --- | --- | --- | --- |
| `start` | `start` | 変数 | 2019-08-24T14:15:22Z | はい（オン） * |
| `end` | `end` | 変数 | 2019-08-24T14:15:22Z | はい（オン） * |
| `eventType` | `eventType` | 変数 | スケジュール済み/スケジュール外 | いいえ（オフ） |
| `exclude_recurrences` | `exclude_recurrences` | 変数 | true / false | いいえ（オフ） |

\* `eventType` = `unscheduled`および`exclude_recurrences` = `true`ではオプションです。

**認証**

| タイプ | API キー名 | API キー値 | ロケーション |
| --- | --- | --- | --- |
| API キー | `<your_username>` | `<EPSILON3_API_KEY>` | ヘッダー |

+++


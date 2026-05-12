---
solution: Journey Optimizer
product: journey optimizer
title: メールメッセージでディープリンクを使用する
description: IOSおよびAndroid アプリケーションでディープリンクをメールコンテンツに追加する方法と、ディープリンク処理を実装する方法について説明します。
feature: Email
topic: Content Management
role: User, Developer
level: Intermediate
keywords: ディープリンク、ディープリンク、ユニバーサルリンク、アプリリンク、電子メール
source-git-commit: f00bb7373065f199346326b3b3e85c542dcd56d8
workflow-type: tm+mt
source-wordcount: '1182'
ht-degree: 1%

---


# メールでのディープリンクの設定 {#email-deeplinks}

メールのディープリンクは、メールの受信者をモバイルアプリの特定の画面やコンテンツに誘導するのに役立ちます。 web ブラウザーやアプリストアを経由することなく、オーディエンスを意図したアプリ内エクスペリエンスに直接つなげることができます。これにより、ジャーニーを通じて、顧客のニーズに即し、ブランド基準を維持できます。

メールにディープリンクを追加するには、[ リンクトラッキングが有効になっていることを確認してください](message-tracking.md#enable-tracking)。 リンクする要素（テキスト、ボタン、画像）を電子メールDesignerで選択し、コンテキストツールバーの「**[!UICONTROL リンクを挿入]**」をクリックし、**[!UICONTROL Deeplink]**」を選択してディープリンク URLを入力します。 [ リンクの挿入の詳細](message-tracking.md#insert-links)

受信者がディープリンクをクリックすると、このページで詳細に説明されている設定手順&#x200B;**を完了すると、受信者は意図したアプリ内コンテンツに直接移動します。**

* Journey Optimizerでメールのディープリンクを設定する方法
* モバイルアプリにiOSとAndroidのディープリンク処理を実装する方法

>[!NOTE]
>
>[!DNL Adobe Journey Optimizer]では、トラッキングされたURL （`/ee/v1/mclick/*`）を使用して、iOSとAndroidの両方でディープリンクをサポートし、互換性とクリックのトラッキングを確保します。

## Journey Optimizerの設定 {#configuration}

モバイルアプリのメールでディープリンクを使用するには、以下の設定手順を完了してください。

>[!NOTE]
>
>このセクションは、**ユニバーサルリンク （iOS）**&#x200B;および&#x200B;**アプリリンク （Android）** （HTTPS ベースのディープリンク）を使用する場合に適用されます。

1. Journey Optimizerで、ディープリンクが有効になっているサブドメインをデリゲートします。 [詳細情報](../configuration/delegate-subdomain.md)

1. IOSのAASA ファイルとAndroidのassetLinks.json ファイルをサブドメインにホストします。 詳しくは、[Adobe カスタマーケア ](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}またはAdobe担当者にお問い合わせください。

   * **iOS （AASA）**&#x200B;の場合：
      * 委任されたサブドメイン
      * アプリバンドル ID
   * **Android （assetLinks.json）**&#x200B;の場合：
      * 委任されたサブドメイン
      * アプリバンドル ID
      * SHA-256証明書のフィンガープリント

>[!IMPORTANT]
>
>[ リンクトラッキングが有効になっている場合](message-tracking.md#enable-tracking)は、Adobe メールインフラストラクチャを通じてディープリンクが適用されます。 トラッキングされたディープリンクのクリックは、Adobeがホストおよび解決する`/ee/v1/mclick/*`の下のURLを使用します。
>
>トラッキングされていない&#x200B;**リンク**&#x200B;の場合、URLはAdobe システムで書き換えられません。 独自のドメインとホスティングでユニバーサルリンクまたはアプリリンクを設定し、それらのリンクが意図したとおりにアプリを開くように設定する必要があります。

## モバイルアプリの導入 {#mobile-implementation}

この節では、一般的な&#x200B;**HTTPS**&#x200B;の設定（ユニバーサルリンクとアプリリンク）で、単一のURLで次のことが可能になるように、[!DNL Adobe Journey Optimizer]を使用してモバイルのディープリンクを実装する方法について説明します。

* アプリがインストールされたときに、モバイルアプリ内の特定の画面を開く、または
* アプリがインストールされていない場合は、Web サイトをフォールバックとして開きます。

メッセージで[ リンクトラッキングが有効になっている](message-tracking.md#enable-tracking)場合、[!DNL Journey Optimizer]はこれらのクリックを引き続き追跡し、レポートに含め、メッセージで実行する場合は[ コンテンツ実験](../content-management/content-experiment.md)でそれらを使用できます。

このセクションでは、ディープリンクの一般的な実装パターンを提供します。 正確な設定は、アプリアーキテクチャとルーティングフレームワークによって異なります。

### iOS （ユニバーサルリンク） {#ios-implementation}

1. Xcodeで、**[!UICONTROL 署名と機能]** > **[!UICONTROL +機能]** > **[!UICONTROL 関連ドメイン]**&#x200B;からターゲットを選択します。
1. デリゲートされたサブドメインのエントリを追加します。例：

   ```text
   applinks:www.mybusiness.com
   applinks:data.email.mybusiness.com
   ```

1. アプリ内のユニバーサルリンクを処理し、応答ヘッダーから元のリンクを取得します。

   +++ 例：iOS 13以降のシーン

   ```swift
   class SceneDelegate: UIResponder, UIWindowSceneDelegate {
   
       func scene(_ scene: UIScene,
                 continue userActivity: NSUserActivity) {
           guard userActivity.activityType == NSUserActivityTypeBrowsingWeb,
                 let incomingURL = userActivity.webpageURL else {
               return
           }
   
           handleUniversalLink(url: incomingURL)
       }
   
       private func handleUniversalLink(url: URL) {
           // Only handle AJO tracked mobile clicks
           guard url.host == "data.email.mybusiness.com",
                 url.path.hasPrefix("/ee/v1/mclick") else {
               // Could also handle direct www.mybusiness.com links here
               return
           }
   
           resolveTrackedUrlAndRoute(url)
       }
   
       private func resolveTrackedUrlAndRoute(_ trackedUrl: URL) {
           var request = URLRequest(url: trackedUrl)
           request.httpMethod = "GET"
   
           URLSession.shared.dataTask(with: request) { _, response, error in
               guard error == nil,
                     let httpResponse = response as? HTTPURLResponse,
                     let locationValue = httpResponse.allHeaderFields["Location"] as? String,
                     let finalUrl = URL(string: locationValue) else {
                   return
               }
   
               DispatchQueue.main.async {
                   self.routeToDestination(finalUrl)
               }
           }.resume()
       }
   
       private func routeToDestination(_ url: URL) {
           // Example: map URL paths to screens
           // https://www.mybusiness.com/dashboard/offers/coupons
           // → OffersViewController for Coupons
       }
   }
   ```

   +++

>[!IMPORTANT]
>
>アプリは`mclick` URLで&#x200B;**GET**&#x200B;を実行し、**`Location`** ヘッダーを読み取り、**final** URLに基づいてルーティングする必要があります。
>
>Safariで`mclick` URLを単に開くのではなく、ディープリンクの目的を損なうものとします。

### Android （アプリリンク） {#android-implementation}

1. Android アプリにアプリリンクのインテントフィルターを追加します。

   ```xml
   <activity
       android:name=".DeepLinkActivity"
       android:exported="true">
   
       <intent-filter android:autoVerify="true">
           <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
   
           <data
               android:scheme="https"
               android:host="data.email.mybusiness.com"
               android:pathPrefix="/ee/v1/mclick" />
       </intent-filter>
   
   </activity>
   ```

1. ディープリンクハンドラーを実装します。

   +++ Kotlinで：

   ```kotlin
   class DeepLinkActivity : AppCompatActivity() {
   
       override fun onCreate(savedInstanceState: Bundle?) {
           super.onCreate(savedInstanceState)
   
           val trackedUri = intent?.data
           if (trackedUri == null ||
               trackedUri.host != "data.email.mybusiness.com" ||
               !trackedUri.path.orEmpty().startsWith("/ee/v1/mclick")) {
               finish()
               return
           }
   
           resolveTrackedUrlAndRoute(trackedUri)
       }
   
       private fun resolveTrackedUrlAndRoute(trackedUri: Uri) {
           lifecycleScope.launch(Dispatchers.IO) {
               try {
                   val finalUrl = followRedirect(trackedUri.toString())
                   withContext(Dispatchers.Main) {
                       routeToDestination(finalUrl)
                       finish()
                   }
               } catch (e: Exception) {
                   // Optionally log error, fallback to browser
                   finish()
               }
           }
       }
   
       private fun followRedirect(trackedUrl: String): Uri {
           val client = OkHttpClient.Builder()
               .followRedirects(false) // We want to read Location ourselves
               .build()
   
           val request = Request.Builder()
               .url(trackedUrl)
               .get()
               .build()
   
           client.newCall(request).execute().use { response ->
               val location = response.header("Location")
                   ?: throw IllegalStateException("Missing Location header")
               return Uri.parse(location)
           }
       }
   
       private fun routeToDestination(finalUri: Uri) {
           // Example: interpret https://www.mybusiness.com/dashboard/offers/coupons
           // and open the correct Activity / Fragment
       }
   }
   ```

   +++

>[!IMPORTANT]
>
>IOSと同様に、アプリは`mclick` URLを呼び出し、**`Location`** ヘッダーを使用して最終的な宛先を決定する必要があります。
>
>`followRedirects(false)`を使用して、リダイレクト処理を制御し、必要に応じて分析を正確にログに記録できます。
>
>ルーティングロジックはアプリに固有です。URLから画面への明確なマッピングを定義します。

## 推奨プラクティス {#deeplink-best-practices}

* **安定パスを使用**: アプリ UIの変更に対して回復力のあるルートを優先します（例：`/tab/3/view/2`ではなく`/account/orders`）。
* **追跡されたパスのアカウント**: リンク追跡が有効になっている場合、クリックしたリンクで追跡されたパスパターンが使用される場合があります（例：`/ee/v1/mclick/`）。 追跡されたリンクを解決した後、ルーターが最終的なURLを解析できることを確認してください。
* **パラメーターを予測可能な状態に保つ**：一貫したパラメーター体系を定義します（例：`?orderId=12345`）。
* **URL内の機密データを避ける**：秘密データまたは個人データをディープリンク URLに直接配置しないでください。
* **ディープリンクをテスト**：プルーフを送信し、アプリがインストールされているデバイスでディープリンクをクリックします。
* **実際のデバイスでの検証**：ユニバーサルリンクとトラッキングリンクの解決動作は、シミュレーターではなく物理デバイスでの検証の方が信頼性が高くなります。
* **アプリ側のルーティングを検証**: ディープリンクが予想される画面を開かない場合は、アプリ側のルーティングとURL形式（ホスト/パス/クエリおよびURL エンコーディング）を検証します。
* **アプリの初期化を念頭に置いてください**: アプリのリンクとユニバーサルリンクの動作は、アプリがインストールされ、少なくとも1回開かれた後に最も信頼性が高くなります。

## トラブルシューティングとFAQ {#troubleshooting-faq}

+++ ディープリンクをタップしてもアプリが開きません。

* リンク追跡が有効になっている場合の追跡クリックパスを含め、URLがアプリが処理する登録ホストとパスパターンに一致することを確認します（例：`/ee/v1/mclick/`以下のパス）。
* IOS ユニバーサルリンクとAndroid アプリリンクの場合、ドメインの関連付け（AASA / `assetlinks.json`）が正しく設定され、到達できることを確認します。
* 実際のデバイスでテストします（シミュレータ/エミュレータは、リンクの関連付けに対して異なる動作を行うことができます）。

+++

+++ アプリが開きますが、想定される画面に移動しません。

* アプリ側のルーターがURLのパス/クエリを正しく解析していることを確認します。
* URL エンコーディングを確認：予約済みの文字はURL エンコードする必要があります。
* パラメーター名と値がルーターの想定と一致することを検証します。

+++

+++ アプリがインストールされていない場合はどうなりますか？

* 同じHTTPS URLをweb サイトで提供できる場合、アプリがインストールされていないときにリンクがフォールバックとしてweb ページを開くことができます（webの宛先とルーティングを適切に設定します）。

+++

+++ パラメーターに特殊文字を安全に含めるにはどうすればよいですか？

URL エンコードクエリパラメーター値。 これにより、配信とレンダリングの問題を軽減し、アプリの解析エラーを防ぐことができます。

+++

+++ エンドツーエンドのテスト方法を検討します？

* ディープリンクを使用してプルーフを作成し、iOSおよびAndroid デバイス（インストール済みおよびインストールされていないシナリオ）でプルーフをクリックします。
* 検証：
   * 最後のメールリンク値（ホスト/パス/クエリ）
   * OS レベルの関連付け（ユニバーサルリンクまたはアプリリンクを使用している場合）
   * アプリ内ルーティングの結果

+++

+++ 1つのアプリがありますが、組織用に異なるサブドメインがあります。 サブドメインごとにAASAとassetLinks.jsonの作成をリクエストする必要がありますか？

はい。 デリゲートされたすべてのサブドメインを詳細に処理する場合は、機能をサポートする必要がある各サブドメインについて、AASAと`assetlinks.json`の設定をリクエストします。

+++

+++ 設定するURLにディープリンク形式（例：`appname://path`）を使用しますか？

カスタム URL スキーム （例：`appname://path`）を使用できますが、推奨されるアプローチは、ユニバーサルリンクまたはアプリリンク （`https://`）であり、このページの「設定」セクションと「実装」セクションのHTTPS ベースの設定と一致します。

+++

+++ URLのUTM パラメーターは、分析用モバイルアプリで使用できますか？

はい。 [!DNL Journey Optimizer]で設定したUTM パラメーターは、アプリが`mclick` URLでGETを実行したときに`Location` ヘッダーで返される最終的なURLに含まれるため、アプリ内分析に使用できます。

+++

+++ `/ee/v1/click/` URLのユーザーエクスペリエンスは何ですか？

リンクは、このページで説明されている`mclick` フローを介してアプリのディープリンクとして処理されるのではなく、デバイスのデフォルトのweb ブラウザー（標準のクリック追跡動作）で開きます。

+++

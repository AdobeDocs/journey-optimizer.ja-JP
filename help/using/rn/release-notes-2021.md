---
solution: Journey Optimizer
product: journey optimizer
title: 以前のリリースノート (2021)
description: 旅オプティマイザー2021リリースノート
exl-id: 0e43be98-f471-4860-be84-8f99ab93e983
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '2077'
ht-degree: 0%

---

# リリースノート2021 {#release-notes-2021}

このページには、2021でリリースされたすべての機能と機能強化 [!DNL Journey Optimizer] が記載されています。


## 11月2021リリース {#november-2021-release}

<table>
<thead>
<tr>
<th><strong>CNAME サブドメイン委任</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe の旅オプティマイザーが Cgi 名をサポートするようになりました。 CNAME、つまり正式名称のレコードは、IP アドレスではなく別のドメインアドレスを指定するレコードです。 CNAME サブドメイン委任を使用すると、サブドメインを作成して、Cgi 名を使用して Adobe 特有のレコードを指し示すことができます。 この構成を使用すると、電子メールの送信、レンダリングおよび追跡のために、環境設定のために DNS を管理するという責務があることになります。</p>
<p>この方法は、組織のポリシーによって完全なサブドメインの委任方法が制限されている場合にお勧めします。</p>
<p>詳しくは、詳細なマニュアル </a> に記載された <a href="../configuration/delegate-subdomain.md#cname-subdomain-delegation"> CNAME サブドメインの委任について詳しく説明します。</a></p>
</td>
</tr>
</tbody>
</table>


## 2021 10 月リリース {#oct-2021-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>意思決定管理-提示シミュレーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、旅のオプティマイザーの UI で、特定の場所について、特定のテストプロファイルに配信されるサービスをシミュレーションできるようになりました。 これにより、decisioning ロジックを、本稼動環境に取り込む前に、適格性制約やランク付けアルゴリズムを使用して簡単に検証することができます。 この機能を使用すると、技術スタッフ以外のユーザーが意思決定管理を迅速にテストし、潜在的な問題をトラブルシューティングすることができます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../offers/offer-activities/simulation.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>意思決定の管理-オファーのカスタマイズ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe エクスペリエンスプラットフォームのプロファイル属性およびセグメントを使用して、各ユーザーがコンテンツをパーソナライズできるようになりました。 </p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../offers/offer-library/creating-personalized-offers.md#custom-text"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>


[Adobe エクスペリエンス Platform 10 月リリースノート ](https://experienceleague.adobe.com/docs/experience-platform/release-notes/2021/october-2021.html) {target = &quot;_blank&quot;} を参照してください。

### 実現

**Journeys**

* **式エディター** -パワーユーザーで、関数を使用してマップを操作できるようになりました。 この機能は、購読リストで活用できます。 例として、セグメントから、購読リストから電子メールアドレスを取得できるようになりました。 [詳細については、このサンプルを参照してください。](../building-journeys/message-to-subscribers-uc.md)

* **ライブ journeys とテストモードの監視** イベントが改善されました。 [新しいフィールド ](../reports/sharing-field-list.md#serviceevents) が追加されました。プロファイルは、プロファイルのエクスポートジョブに関連付けられています。 より優れた操作性を実現するために、ステップのイベントフィールドが別のカテゴリーに分類されるようになりました。 これまでのすべてのステップのイベントフィールドは、 [ 「stepevents ](../reports/sharing-legacy-fields.md) 」カテゴリーでも使用できます。
* **アクセシビリティ** : アクセシビリティの強化が journeys に実装されています。
* **コレクション** -サブオブジェクトが含まれるオブジェクトの配列がサポートされるようになりました。 [詳細を読む](../building-journeys/collections.md)
* **リスト** : journeys、イベント、アクション、データソースのリストを表示する機能が強化されました。

**書**

* **グローバルビュー** のデータフォーマット-「実行 **」タブの** グローバルビュー **で** 数と比率を切り替えられるようになりました。


**管理**

* **メッセージプリセット** の編集-メッセージプリセットを編集して、そのアップデート状態を監視できるようになりました。 [詳細情報](../configuration/channel-surfaces.md#edit-channel-surface)
* **PTR レコード** の編集-ptr レコードを編集して、更新状況を監視できるようになりました。 [詳細情報](../configuration/ptr-records.md#edit-ptr-record)

**パーソナライゼーション**

* **日付をフォーマット** するための新しいヘルパー関数-日付ストリングの表示方法を指定することができます。 [詳細情報](../personalization/functions/dates.md#format-date)


**意思決定管理**

* **評価シーケンス** : 新しく改善された意思決定の作成フローによって、ディシジョンオブジェクト間の移動をよりシームレスにすることができます。また、デシジョンエンジンによって提供コレクションがどのように評価されるかを完全に制御できます。 これには、個別に評価されるコレクション、およびコレクションを評価する順序が含まれます。 [詳細情報](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

### さ

* ブラウザーの言語が英語以外の場合に、旅リスト、メッセージリスト、電子メールデザイナーが表示されなくなる問題を修正しました。
* 電子メールデザイナーのエクスプレッションを使用して、パーソナル化を追加する際に発生したシンタックスエラーが修正されました。文字がエスケープされていません。
* 管理 **メニュー内を移動すると、404エラーが発生する問題が修正されて** います。
* 業務イベントを使用して、旅をテストするときに、その他のライブ journeys をトリガーさせた問題を修正していました。


## 9月2021リリース {#september-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>レポート-対象ユーザーに対するより的確な洞察</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>レポートで新しいメトリックを使用できるようにする: 宛先を選択して電子メールの場合は除外 &amp; プルメッセージは、ライブとグローバルの両方のレポートに表示されます。 </br> 最新のメトリックスへのアクセスを許可するには、チャネルとレポートタイプごとに異なるレポートダッシュボードをリセットする必要があることに注意してください。 ダッシュボードのカスタマイズについて詳しくは、詳しくは <a href="../reports/live-report.md"> マニュアルを参照してください。</a></p>
<p>「メッセージ実行」リストの新しい列に、各メッセージが実行されたときのターゲットプロファイル数が表示されます。 </p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../reports/global-report.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>カスタムアクションを使用してデータのリストを動的に渡す</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>実行時に動的に値が設定されるカスタムアクションパラメーターで、コレクションまたはデータのリストを渡すことができるようになりました。 サポートされるコレクションには、単純なコレクションとオブジェクトコレクションの2種類があります。 以前に作成したカスタムアクションは継続して実行されます。 </p>
<p>コレクションについて詳しくは、詳細なマニュアル </a> を <a href="../building-journeys/collections.md"> 参照してください。 </a></p>
<p>この関数は、高度な式エディターで使用可能な関数のリストに追加されています。 これにより、コレクションのフィルター処理と比較が可能になります。</p>
<p>フィルター </a> 関数と <a href="../building-journeys/functions/functionintersect.md"> intersect </a> 関数について <a href="../building-journeys/functions/functionfilter.md"> 詳しくは、このドキュメントを参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

### 実現

**Journeys**

* システムによって生成されたスキーマと、step イベントの準備中に作成されたデータセットは読み取り専用モードになり、重要なスキーマが不用意に修正されていないことになります。 [詳細情報](../reports/sharing-overview.md)
* Canvas に表示されるラベルを使用して、 **待機** アクティビティーに正常にラベルを付けます。 また、ラベルはレポート作成やテストモードのログにも表示され、実行中の内容を明確に識別するために使用されます。 [詳細情報](../building-journeys/about-journey-activities.md#best-practices)
* 「検索」を使用して、 **イベント** と **アクション** カテゴリのエレメントをフィルタリングすることにより、イベントやアクションを迅速に検索できます。 オーケストレーションアクティビティはフィルターされなくなりました。 [詳細情報](../building-journeys/using-the-journey-designer.md)
* ルールに基づいてイベント ID の条件を定義すると、フィールドのストリング型については、「含む」演算子を使用できるようになります。 [詳細情報](../event/about-creating.md)

**電子メール設定**

* IP プールがメッセージプリセットに関連付けられた場合は、それを編集して、非同期にすることができます。 また、各 IP プールのアップデート状態を確認することもできます。 [詳細情報](../configuration/ip-pools.md#edit-ip-pool)


## 8月2021リリース {#august-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>最適なタイミングでメッセージを送信します。送信時の最適化</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>Adobe の旅オプティマイザーに従事した各お客様に、自動的にプッシュまたは電子メールを送信することができます。 Adobe の AI サービスによって実行される送信時の最適化は、電子メールを送信するのに最適な時期、つまり、ボックスの「オープン」と「レート」の「時間」をクリックして、契約を最大限にするのに適しています。</p>
<p>この機能は現在ベータ版に含まれており、ベータ版のお客様のみが利用できます。 ベータプログラムに参加するには、Adobe カスタマーケアにご連絡ください。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../building-journeys/journeys-message.md#send-time-optimization"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>ビジネスイベントでのスキーマリレーションシップの活用-ルックアップテーブルの管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ビジネスイベントを設定するときに、スキーマ間の関係を利用できるようになりました。 これには、ユニタリイベントを設定するときに、リンクテーブルのフィールドを使用する機能に加えて、中での条件、メッセージのパーソナライズ、およびカスタムアクションのパーソナル化についても使用できます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../event/experience-event-schema.md#leverage_schema_relationships"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>パーソナライズされた Url</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライズされた Url では、プロファイル属性に応じて、web サイトの特定のページ、またはパーソナライズされたマイクロサイトが宛先になります。 Adobe 旅のオプティマイザーを使用すると、メッセージコンテンツ内の Url にパーソナル化機能を追加することができます。 URL パーソナル化は、テキストとイメージに適用できます。また、プロファイルデータまたは文脈データを使用することもできます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../personalization/personalization-syntax.md#perso-urls"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>電子メールがユーザーに対して表示されることを確認してください。-Email Retry</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>必要になったときにリトライが実行されないように、プリセットごとにリトライ期間を定義できるようになりました。 例えば、1日あたりのリンクが有効になっているときに、パスワードの再設定トランザクションメッセージについては、再試行の間隔を24時間に設定することができます。 「再送」設定は、電子メールチャンネルにのみ適用されます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../configuration/retries.md#retry-duration"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>送信抑制リストから除外するアドレスの定義</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>抑制リストへの電子メールアドレスとドメインの追加は、CSV ファイルのアップロードを使用してバルクモードにして、ユーザーインターフェイスから実行できるようになりました。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../configuration/manage-suppression-list.md#add-addresses-and-domains"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>


### 実現

**Journeys**

* **動的なヘッダー** : HTTP ヘッダパラメーターに動的データを渡すことができるようになりました。 これらのパラメーターは、タイムスタンプや追跡 ID などの、旅のアクション HTTP 呼び出しを受け取る統合システムによって使用されます。 [詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* **動的 URL パス** : カスタムアクション用の動的 url パスを設定できるようになりました。 [詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* 読み取りセグメントの全体的なスロットル率は、1秒間に 17000 ~ 2万メッセージに変更されました。 [詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**ユーザーインターフェイス**

* **検索** -すべてのページで、統合されたエクスペリエンスクラウド検索フィールドから直接、ビジネスオブジェクトの検索と記事のヘルプを利用できるようになりました。 [詳細情報](../start/user-interface.md#unified-search)
* **** Recents-Adobe 旅オプティマイザーホームページの recents の表示が、追加のビジネスオブジェクトに拡張されました。このアップデートを使用すると、最近アクセスされたメッセージに対するショートカットとして、Journeys、Segment、スキーマ、データセット、データソース、イベント、アクション、ソース、移動先が含まれます。 [詳細情報](../action/about-custom-action-configuration.md#passing-collection)

**コンテンツデザイン**

* **バックグラウンド** イメージがライブプレビューでサポートされるようになりました。 [詳細情報](../email/preview.md)
* **ワンクリックのオプトアウトリンク** -電子メールコンテンツに新しいタイプのリンクを挿入できます。この場合、ユーザーは、 **** 1 回のクリックで受信を行うことができ、ジャンプページにリダイレクトされることなく、オプトインが確認されます。[詳細情報](../privacy/opt-out.md#one-click-opt-out-link)

**パーソナライゼーション**

* **式エディター** を使用して、パーソナル化を定義するときにフォールバック値を簡単に追加できるようになりました。プロファイルに対して「パーソナライズ」フィールドが空の場合は、フォールバック値が表示されます。 [詳細情報](../personalization/functions/helpers.md)

**電子メール設定**

* **許可リスト** -許可リストは、API 呼び出しを通じて非プロダクションサンドボックスで有効または無効にすることができるようになりました。 [詳細情報](../configuration/allow-list.md#enable-allow-list)
* **ナビゲーション** : 「管理 > チャンネル > 電子メール設定 > 「一般」メニューの下 **にアクセス可能な** 抑制リストが、「新規 **抑制リスト** 」サブメニューに移動されました。これにより、関連するすべての機能が収集され、アクセスが容易になります。 [詳細情報](../configuration/manage-suppression-list.md#access-suppression-list)

**意思決定管理**

* オファーの作成時に表示を追加および設定することによって、ユーザーエクスペリエンスが改善されました。 特に、アセットライブラリが表示されるようになりました。これは、イメージタイプのコンテンツを定義するときに限られます。 [詳細情報](../offers/offer-library/creating-personalized-offers.md#representations)

### さ

* 「メッセージ」タブのナビゲーションで、アクセシビリティに関する問題を修正していました。
* 電子メールデザイナーのラベルでローカライズの問題を修正しています。
* 1つの旅で複数のノードを選択し、「削除」をクリックすると問題が修正されています。
* この問題を修正して、旅で使用されるアクションに新しいヘッダーを追加することができなくなります。
* ユーザーインターフェイスでより明示的な警告を使用して、メッセージの事前設定の作成が失敗した理由を確認できるようになりました。


## 2021年7月リリース {#july-2021-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>メッセージにメタデータを使用: ルックアップテーブルの管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>このように、旅オプティマイザーに読み込まれた参照データによって、操作性を強化することができます。 例としては、エクスペリエンスイベントの予約 ID にメタデータを表示したり、canvas で使用するためにエクスペリエンスイベントで sku から製品情報を検索することができます。 </p>
<p>スキーマ間の関係を活用して、1つのデータセットを別のデータセットのルックアップテーブルとして使用できるようになりました。 その後、ユニタリイベントを設定するときに、リンクテーブルのすべてのフィールドを使用できます。この場合、次のように、処理中、メッセージの個人用設定、およびカスタムアクションのパーソナル化において使用されます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../event/experience-event-schema.md#leverage_schema_relationships"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>許可リスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>サンドボックスレベルで特定の送信セーフリストを定義して、テスト目的の安全な環境を作成できるようになりました。 非プロダクションインスタンスでは、間違いが発生する可能性があるので、許可リストを使用すると、不要なメッセージがユーザーに送信される恐れがなくなります。 この機能は、抑制 Api を利用することによって有効になります。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../configuration/allow-list.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

### 実現

**Journeys**

* 同じサンドボックスで同時に実行されるすべての読み取りセグメントの全体的なスロットル率は、1秒間に17000メッセージに制限されています。 [詳細を読む](../building-journeys/read-segment.md#configuring-segment-trigger-activity)
* **キャッシュ期間** フィールドは、データソース設定ペインから削除されました。[詳細を読む](../datasource/about-data-sources.md)
* 外部データソースでは、毎秒15呼び出しの上限規則が自動的に定義されています。 [詳細を読む](../configuration/external-systems.md#capping)
* ライブ journeys については、「ドキュメントのパブリッシュ日付」とその旅をパブリッシュしたユーザー名が表示されるようになりました。 [詳細を読む](../building-journeys/journey-gs.md#change-properties)
* 「旅のリスト」画面に、旅の種類フィルターが追加されました。 [詳細を読む](../start/user-interface.md#filter-lists)
* **[!UICONTROL Throttling rate]**&#x200B;このパラメーターは、Segment 読み取り操作で追加されました。[詳細を読む](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**プレビューとテスト**

* Id と名前空間が画面に **[!UICONTROL Preview]** 表示されるようになりました。 [詳細を読む](../email/preview.md#preview-your-messages)
* 校正用のテスト電子メールの数は10個に制限されるようになりました。
* 校正において、件名の接頭辞 **とし** て使用できる文字が制限されるようになりました。[詳細を読む](../email/preview.md#send-proofs)

**パーソナル化式エディター**

* ヘルパードロップダウンリストには名前が変更され、並べ替えられました。

### さ

* バッチ電子メールを配信するために、重複メッセージが配信される問題を修正しました。
* リトライ期間が経過しても電子メールの送信が実行されない場合に、イベントが生成されるようになりました。
* PTR レコード画面に IP 情報が見つからないという問題が修正されました。
* Expression editor 内の提供鉄道のローカライズが実装されました。
* 情報ポップアップ内の間隔が間違っていることが修正されています。
* HTML ファイルをアップロードするときに、内部スタイルシート `background-image` のプロパティがサポートされていなかった場合に、電子メールデザイナーで問題を修正しました。

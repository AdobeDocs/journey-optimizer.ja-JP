---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 6c4b79ad4291d6206fbbbe831ea10b76b431389f
workflow-type: tm+mt
source-wordcount: '2614'
ht-degree: 93%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。



## 2022 年 2 月リリース {#feb-2022-release}

### 新機能

<!--table>
<thead>
<tr>
<th><strong>Subscription Landing Pages</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create and design landing pages in Journey Optimizer, and direct your users to online forms where they can opt-in or opt-out from receiving your communications, or subscribe to a specific service such as a newsletter.</p>
<p>For more information, refer to the <a href="../landing-pages/create-lp.md">detailed documentation</a> and related <a href="../landing-pages/lp-use-cases.md">sample use case</a>.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Expression Personalization Library</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer now provides a library where you can access predefined personalization expressions. These expressions are configured by Admin users.</p>
<!--p>For more information, refer to the <a href="../landing-pages/create-lp.md">detailed documentation</a> and related <a href="../landing-pages/lp-use-case.md">sample use case</a>.</p>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>API Developer Site and Suppression API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer provide RESTful APIs that allow you to programmatically perform key operations in your applications.
Developer SDK for Journey Optimizer is now available with the Suppression API (beta).</p>
<p>With this API, you can control your outgoing messages using suppression and allow lists.
The suppression list helps you with honoring the ISPs’ feedback to preserve sending IP reputation. The allow list helps you ensure that you send only to those email addresses which are in the allowed list, and typically to ensure that you don't send mails to customers from your development sandbox.</p>
<p>See <a href="https://developer.adobe.com/journey-optimizer-apis/">Adobe Journey Optimizer APIs</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>UTM トラッキングパラメーターを使用してメッセージをトラッキングする情報を渡す</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerのメッセージコンテンツで、リンクに UTM パラメーターを追加できるようになりました。顧客は、そのリンクに関する追加データを提供し、顧客がリンクをクリックした場所と理由を特定するのに役立ちます。</p>
<p>詳しくは、 <a href="../configuration/message-presets.md">詳細なドキュメント</a>を参照してください。</p-->
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* パフォーマンスを最適化するために、1 週間トリガーされていないテストモードのすべてのジャーニーが、ドラフトステータスに戻るようになりました。 [詳細情報](../building-journeys/testing-the-journey.md#important_notes)
* Journey OptimizerとAdobe Campaign Classicの統合は、パフォーマンスを向上させるために最適化されています。 上限のデフォルト設定は、4,000 呼び出し/ 5 分に変更されました。	[詳細情報](../action/acc-action.md#important-notes)

**レポート**

* 配信は、ステータスに応じてフィルタリングできるようになりました。
   * 「メッセージの実行」リストで、配信のリストから配達確認を除外できるようになりました。
   * ライブレポートまたはグローバルレポートから、テストイベントの除外を選択できます。

* 送信時間の最適化データに関するレポートにアクセスできるようになりました。即時にメッセージを送信した人の数、1 時間の最適化、2 時間の最適化などでメッセージを送信した人の数

<!--* Offer Decisioning reports are now available in Journey Optimizer. You can access the following metrics: Offers sent - Offers' impression rate - Offers' click rate - Breakdown report on Offers' sent.-->

**意思決定管理**

* ランキングと AI ランキングが 1 つのタブにグループ化されました。

## 2022年1月リリース {#january-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>ジャーニー - プロファイルキャップ条件による IP ランプアップの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーで<strong>条件</strong>アクティビティを設定する際、プロファイルのキャップを定義できるようになりました。この新しい条件タイプを使用すると、ジャーニーパスの最大プロファイル数を設定できます。この制限に到達すると、エントリするプロファイルは代替パスを使用します。これにより、配信の量を増やすことができます（IP ランプアップ）。 例えば、1 日目に 1000 通のメッセージ、2 日目に 2000 通というように、ドメインでの実行を分割して配信を増やす場合があります。</p>
<p>詳しくは、<a href="../building-journeys/condition-activity.md#profile_cap">詳細なドキュメント</a>および関連する<a href="../building-journeys/ramp-up-deliveries-uc.md">サンプルユースケース</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニー - セグメントの読み取りの向上</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>増分読み取り</strong>オプションが、繰り返しの<strong>セグメントを読み取り</strong>アクティビティに追加されました 。このオプションを使用すると、ジャーニーの最後の実行以降にセグメントにエントリした個人のみをターゲットにすることができます。最初の実行では、常にすべてのセグメントメンバーがターゲットになります。</p>
<p>詳しくは、 <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* Journey Optimizer ステップイベントを、[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) の他のデータセットにリンクできるようになりました。ビルトイン Journey Step Event スキーマの **profileID** フィールドが、ID フィールドとして定義されるようになりました。[詳細情報](../reports/sharing-overview.md#integration-cja)

**Offer Decisioning**

* 公開済みメッセージ内で直接または間接的に参照されるオファー、フォールバックオファー、オファーコレクション、オファー決定を更新すると、その更新は、対応するメッセージに自動的に反映されるようになり、再公開する必要がなくなりました。[詳細情報](../offers/offers-e2e.md#insert-decision-in-email)

* 特定のテストプロファイルに配信するオファーをシミュレートする際に、デフォルトのシミュレーション設定を変更し、トラブルシューティング目的で使用できる、シミュレーションに対応したコードを表示できるようになりました。[詳細情報](../offers/offer-activities/simulation.md#define-simulation-settings)

**管理**

* 管理者は、CNAME を設定したサブドメインを使用して PTR レコードを編集できるようになりました。[詳細情報](../configuration/ptr-records.md#edit-ptr-subdomains-cname)

**パーソナライゼーション**

* **お気に入りに追加** - パーソナライゼーションを使用する際の効率を向上させるために、お気に入りを保存するという概念を導入しました。お気に入りメニューに異なる属性を追加すると、最も頻繁に使用する項目にすばやくアクセスできます。 [詳細情報](../personalization/personalize.md#fav)

## 2021年11月リリース {#november-2021-release}

<table>
<thead>
<tr>
<th><strong>CNAME サブドメインのデリゲーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer で CNAME がサポートされるようになりました。CNAME（正規名レコード）とは、IP アドレスではなく別のドメインアドレスを指すレコードです。CNAME サブドメインデリゲーションを使用すると、サブドメインを作成し、CNAME を使用してアドビ固有のレコードを指定できます。この設定を使用すると、 メールの送信、レンダリング、トラッキングの環境を設定するために、DNS の管理に対する責任を、お客様とアドビで共有します。</p>
<p>組織のポリシーで完全なサブドメインデリゲーションの方法が制限されている場合は、この方法をお勧めします。</p>
<p>CNAME サブドメインのデリゲーションについて詳しくは、 <a href="../configuration/delegate-subdomain.md#cname-subdomain-delegation">詳細ドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


## 2021年10月リリース {#oct-2021-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>意思決定管理 - オファーのシミュレーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer UI で、特定のプレースメントの場合にテストプロファイルに配信されるオファーをシミュレートできるようになりました。これにより、実稼動環境に配置する前に、実施要件の制約やランキングアルゴリズムなどの決定ロジックを容易に検証できます。この機能を使用すると、技術に詳しいユーザーもそうでないユーザーも Offer Decisioning を迅速にテストし、潜在的な問題をトラブルシューティングできます。</p>
<p>詳しくは、<a href="../offers/offer-activities/simulation.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>意思決定管理 - オファーのパーソナライズ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer UI の至る所で登場する式エディターコンポーネントと同じものを使用して、Adobe Experience Platform のプロファイル属性とセグメントでオファーのコンテンツをパーソナライズできるようになりました。 </p>
<p>詳しくは、<a href="../offers/offer-library/creating-personalized-offers.md#custom-text">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


その他の変更点については、[Adobe Experience Platform 10月リリースのリリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/2021/october-2021.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

### 機能強化

**ジャーニー**

* **式エディター** - パワーユーザーは、関数を使用してマップを操作できるようになりました。この機能は、サブスクリプションリストで利用できます。例えば、セグメントでは、サブスクリプションリストからメールアドレスを取得できるようになりました。詳しくは、[このサンプル](../building-journeys/message-to-subscribers-uc.md)を参照してください。

* **監視** - ライブジャーニーのステップイベントとテストモードが強化されました。プロファイルエクスポートジョブに関連する[新規フィールド](../reports/sharing-field-list.md#serviceevents)が追加されました。ユーザーエクスペリエンスを向上させるために、ステップイベントフィールドが様々なカテゴリに分類されるようになりました。以前のステップイベントフィールドはすべて、引き続き[stepEvents](../reports/sharing-legacy-fields.md) カテゴリで使用できます。
* **アクセシビリティ** - ジャーニーにアクセシビリティ機能の強化が実装されました。
* **コレクション** - サブオブジェクトを含んだオブジェクトの配列がサポートされるようになりました。[詳細情報](../building-journeys/collections.md)
* **リスト** - ジャーニー、イベント、アクション、データソースのリスト画面が改善されました。

**レポート**

* **グローバル表示のデータフォーマット** -「**実行**」タブの&#x200B;**グローバル表示**&#x200B;で数値表示とパーセント表示を切り替えられるようになりました。[詳細情報](../messages/message-monitoring.md)


**管理**

* **メッセージプリセットの編集** - メッセージプリセットを編集し、その更新ステータスを監視できるようになりました。[詳細情報](../configuration/message-presets.md#edit-message-preset)
* **PTR レコードの編集** - PTR レコードを編集し、その更新ステータスを監視できるようになりました。[詳細情報](../configuration/ptr-records.md#edit-ptr-record)

**パーソナライゼーション**

* **日付書式設定用の新しいヘルパー関数** - 日付文字列の表現方法を指定できるようになりました。 [詳細情報](../personalization/functions/dates.md#format-date)


**意思決定管理**

* **評価順序** - 改善された新しい決定作成フローにより、決定オブジェクト間をよりシームレスに移動できるだけでなく、決定エンジンによるオファーコレクションの評価方法を完全に制御できるようにもなりました。これには、一括で評価されるコレクションと個別に評価されるコレクションの区別や、コレクションの評価順序などが含まれます。[詳細情報](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

### 修正点

* ブラウザー言語が英語以外の場合に、ジャーニーリスト、メッセージリストおよび E メールデザイナーが表示されない問題を修正しました。
* E メールデザイナーで式を使用してパーソナライゼーションを追加する際に発生する構文エラーを修正しました。文字が誤ってエスケープされていました。
* **管理**&#x200B;メニュー内を移動すると 404 エラーになる問題を修正しました。
* ビジネスイベントを使用してジャーニーをテストする際に他のライブジャーニーがトリガーされる問題を修正しました。


## 2021年9月リリース {#september-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>レポート - ターゲットオーディエンスに対するインサイトの向上</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>レポートで新しい指標を使用できます。メールおよびプッシュメッセージの「ターゲット」と「除外」がライブレポートとグローバルレポートの両方に表示されます。 </br> 最新の指標にアクセスするには、チャネルとレポートのタイプごとに異なるレポートダッシュボードをリセットする必要があります。 ダッシュボードのカスタマイズについて詳しくは、<a href="../reports/live-report.md">詳細ドキュメント</a>を参照してください。</p>
<p>メッセージ実行リストの新しい列に、メッセージ実行ごとのターゲットプロファイル数が表示されます。 </p>
<p>詳しくは、<a href="../messages/message-monitoring.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>カスタムアクションを使用したデータリストの動的な受け渡し</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>実行時に動的に入力されるカスタムアクションパラメーターに、コレクションつまりデータのリストを渡すことができるようになりました。 単純なコレクションとオブジェクトコレクションの 2 種類のコレクションがサポートされています。 以前に作成したカスタムアクションは引き続き機能します。 </p>
<p>コレクションについて詳しくは、<a href="../building-journeys/collections.md">詳細なドキュメント</a>を参照してください。 </p>
<p>filter 関数と intersect 関数が、高度な式エディターで使用できる関数のリストに追加されました。これにより、コレクションのフィルタリングと比較でさらに多くのことを行えるようになります。</p>
<p><a href="../building-journeys/functions/functionfilter.md">filter</a> 関数と <a href="../building-journeys/functions/functionintersect.md">intersect</a> 関数のドキュメントを参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* ステップイベントのプロビジョニング時に作成されたシステム生成スキーマおよびデータセットは、読み取り専用モードになり、重要なスキーマへの不用意な変更に対する保護が強化されました。 [詳細情報](../reports/sharing-overview.md)
* 「**待機**」アクティビティのラベルとして、キャンバスに表示されるラベルがはっきりと表示されます。このラベルは、レポートおよびテストモードのログでも使用され、実行内容がはっきりとわかるようになっています。 [詳細情報](../building-journeys/about-journey-activities.md#best-practices)
* 検索を使用して&#x200B;**イベント**&#x200B;および&#x200B;**アクション**&#x200B;カテゴリの要素をフィルタリングすることで、イベントとアクションをすばやく見つけることができます。オーケストレーションアクティビティがフィルタリングされなくなりました。 [詳細情報](../building-journeys/using-the-journey-designer.md)
* ルールベースイベントまたはビジネスイベントでイベント ID 条件を定義する際に、「次を含む」演算子を文字列タイプのフィールドで使用できるようになりました。 [詳細情報](../event/about-creating.md)

**メール設定**

* IP プールがメッセージプリセットに関連付けられている場合に IP プールを編集できるようになり、更新は非同期になります。 また、各 IP プールの更新ステータスを確認することもできます。 [詳細情報](../configuration/ip-pools.md#edit-ip-pool)


## 2021 年 8 月リリース {#august-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>最適なタイミングでのメッセージの送信 - 送信時間の最適化</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer とのエンゲージメントの対象となる顧客ごとに、最適なタイミングでプッシュ通知またはメールを自動的に送信します。アドビの AI サービスを活用した送信時間最適化により、メールまたはプッシュメッセージの送信に最適な時間を標準で予測して、過去の開封率やクリック率に基づいてエンゲージメントを最大化できます。</p>
<p>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。</p>
<p>詳しくは、<a href="../building-journeys/journeys-message.md#send-time-optimization">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>ビジネスイベントでのスキーマ関係の活用 - ルックアップテーブルの管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ビジネスイベントの設定時に、スキーマ間の関係を活用できるようになりました。これに加えて、単一イベントの設定、ジャーニーでの条件の使用、メッセージのパーソナライゼーションおよびカスタムアクションのパーソナライゼーションの際に、リンクされたテーブルのフィールドも活用できます。</p>
<p>詳しくは、<a href="../event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>パーソナライズされた URL</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライズされた URL は、プロファイル属性に応じて、受信者を web サイトの特定のページに誘導するか、パーソナライズされたマイクロサイトに誘導します。 Adobe Journey Optimizer で、メッセージコンテンツの URL にパーソナライゼーションを追加できるようになりました。 URL のパーソナライゼーションはテキストや画像に適用でき、その際にプロファイルデータやコンテキストデータを使用できます。</p>
<p>詳しくは、<a href="../personalization/personalization-syntax.md#perso-urls">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ユーザーへのメールの確実な配信 - メールの再試行</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>プリセットごとに再試行期間を定義して、不要になったときに再試行がそれ以上実行されないようにすることが可能になりました。例えば、1 日のみ有効なリンクを含んだパスワードリセット用トランザクションメッセージの場合は、再試行期間を 24 時間に設定できます。なお、再試行設定はメールチャネルにのみ適用されます。</p>
<p>詳しくは、<a href="../configuration/retries.md#retry-duration">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>送信から除外するアドレスの定義 - 抑制リスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ユーザーインターフェイスでメールアドレスとドメインを抑制リストに追加する際に、1 つずつ追加するか、CSV ファイルのアップロードを使用して一括モードで追加するかを選択できるようになりました。</p>
<p>詳しくは、 <a href="../configuration/manage-suppression-list.md#add-addresses-and-domains">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


### 機能強化

**ジャーニー**

* **動的ヘッダー** - HTTP ヘッダーパラメーターで動的データを渡せるようになりました。これらのパラメーターは、ジャーニーアクションの HTTP 呼び出し（タイムスタンプやトラッキング ID など）を受け取る統合システムで使用できます。 [詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* **動的 URL パス** - カスタムアクションの動的 URL パスを設定できるようになりました。[詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* 読み取りセグメントの全体的なスロットル率が、1 秒あたり17,000 メッセージから 20,000 メッセージに変更されました。[詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**ユーザーインターフェイス**

* **検索** - すべてのページで、Experience Cloud 統合検索フィールドからビジネスオブジェクトやヘルプ記事を直接検索できるようになりました。[詳細情報](../start/user-interface.md#unified-search)
* **最近の情報** - Adobe Journey Optimizer ホームページの最近の情報要素の表示が拡張され、追加のビジネスオブジェクトが含まれるようになりました。この更新で、最近アクセスしたものへのショートカットに、メッセージ、ジャーニー、セグメント、スキーマ、データセット、データソース、イベント、アクション、ソースおよび宛先が含まれるようになりました。[詳細情報](../action/about-custom-action-configuration.md#passing-collection)

**コンテンツデザイン**

* **背景** - 背景画像がライブプレビューでサポートされるようになりました。[詳細情報](../messages/preview.md)
* **ワンクリックオプトアウトリンク** - メールコンテンツに新しいタイプのリンクを挿入できます。この&#x200B;**オプトアウト**&#x200B;リンクを使用すると、ユーザーがワンクリックでコミュニケーションの受信登録を解除でき、オプトアウトを確認するためにランディングページにリダイレクトされることはありません。[詳細情報](../messages/consent.md#one-click-opt-out-link)

**パーソナライゼーション**

* **式エディター** - パーソナライゼーションを定義する際に、フォールバック値を容易に追加できるようになりました。プロファイルのパーソナライゼーションフィールドが空の場合、フォールバック値が表示されます。[詳細情報](../personalization/functions/helpers.md)

**メール設定**

* **許可リスト** - API 呼び出しを通じて、実稼動以外のサンドボックスで許可リストを有効および無効にできるようになりました。[詳細情報](../messages/allow-list.md#enable-allow-list)
* **ナビゲーション** - 抑制リストは&#x200B;**管理／チャネル／メール設定／一般**&#x200B;メニューでアクセス可能でしたが、新しい&#x200B;**抑制リスト**&#x200B;サブメニューに移動しました。このサブメニューには、関連するすべての機能が集約されているので、アクセスしやすくなっています。[詳細情報](../configuration/manage-suppression-list.md#access-suppression-list)

**意思決定管理**

* オファーの作成時に表示域を追加および設定する方法が更新され、ユーザーエクスペリエンスが向上しました。 特に、アセットライブラリは、表示域に対して画像タイプのコンテンツを定義する場合にのみ表示されるようになりました。[詳細情報](../offers/offer-library/creating-personalized-offers.md#representations)

### 修正点

* メッセージタブのナビゲーションにおけるアクセシビリティの問題を修正しました。
* 電子メールデザイナーのラベルに関するローカライゼーションの問題を修正しました。
* 1 つのジャーニーで複数のノードを選択してプロパティパネルの「削除」をクリックする際の問題を修正しました。
* ジャーニーで使用するアクションに新しいヘッダーを追加できなかった問題を修正しました。
* ユーザーインターフェイスの警告がより明確になったので、メッセージプリセットの作成が失敗した理由を特定できるようになりました。


## 2021 年 7 月リリース {#july-2021-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>メッセージでのメタデータの使用 - ルックアップテーブルの管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer に読み込んだ参照データを使用して、エクスペリエンスを強化できます。例えば、エクスペリエンスイベントで予約 ID のメタデータを検索したり、キャンバスで使用するためにエクスペリエンスイベントで SKU から製品情報を検索したりすることができます。 </p>
<p>あるデータセットを別のデータセットのルックアップテーブルとして使用するために、スキーマ間の関係を活用できるようになりました。その場合、リンクされたテーブルのすべてのフィールドは、単一イベントの設定時、ジャーニーでの条件の使用時、メッセージのパーソナライゼーション、カスタムアクションのパーソナライゼーションに活用できます。</p>
<p>詳しくは、<a href="../event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
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
<p>特定の送信セーフリストをサンドボックスレベルで定義して、テスト目的の安全な環境を構築できるようになりました。 ミスが発生する可能性のある非実稼働インスタンスでは、許可リストにより、不要なメッセージが顧客に送信されるリスクがなくなります。この機能は、抑制 API を利用することで有効になります。</p>
<p>詳しくは、 <a href="../messages/allow-list.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* 同じサンドボックスで同時に実行されるすべての「セグメントを読み取り」アクティビティの全体的なスロットルレートは、1 秒あたり 17,000 メッセージに制限されています。[詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)
* 「**キャッシュ時間**」フィールドがデータソース設定ペインから削除されました。[詳細情報](../datasource/about-data-sources.md)
* 外部データソースの場合、1 秒あたり 15 回までの呼び出し回数制限（キャッピング）ルールが自動的に定義されるようになりました。 [詳細を読む](../configuration/external-systems.md#capping)
* ライブジャーニーの場合、ジャーニーを公開した日付とユーザーの名前がジャーニープロパティ画面に表示されるようになりました。 [詳細を読む](../building-journeys/journey-gs.md#change-properties)
* ジャーニーリスト画面にジャーニータイプフィルターが追加されました。 [詳細を読む](../start/user-interface.md#filter-lists)
* **[!UICONTROL スロットルレート]**&#x200B;パラメーターが「セグメントを読み取り」アクティビティに追加されました。 [詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**メッセージのプレビューとテスト**

* ID と名前空間が&#x200B;**[!UICONTROL プレビュー]**&#x200B;画面に表示されるようになりました。[詳細情報](../messages/preview.md#preview-your-messages)
* 配達確認のテストメールの数が 10 個に制限されるようになりました。
* 配達確認の&#x200B;**件名行のプレフィックス**&#x200B;に使用できる文字が制限されるようになりました。 [詳細情報](../messages/preview.md#send-proofs)

**パーソナライゼーション式エディター**

* ヘルパードロップダウンリストの名前と順序が変更されました。

### 修正点

* 一括メール配信で重複メッセージが配信される問題を修正しました。
* 再試行期間が終了した後、メール送信が実行されない場合、それに応じてイベントが生成されるようになりました。
* PTR レコード画面に IP 情報が表示されない問題を修正しました。
* 式エディター内のオファーパネルのローカライゼーションが実装されました。
* 情報ポップアップの間隔の誤りを修正しました。
* `background-image` プロパティを持つ内部スタイルシートがサポートされていない HTML ファイルをアップロードする際の電子メールデザイナーの問題を修正しました。

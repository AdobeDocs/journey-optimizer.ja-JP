---
title: リリースノート
description: Journey Optimizer リリースノート
source-git-commit: ff48c78cfa5c48f32073e9df1f126504e291ab5a
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 37%

---


# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。最新の[ドキュメント更新](documentation-updates.md)を参照することもできます。


## 2021 年 8 月リリース {#august-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>最適なタイミングでのメッセージ送信 — 送信時の最適化</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerと関わるすべての顧客に対し、最適なタイミングでプッシュまたは電子メールを自動的に送信します。 AdobeのAIサービスを活用した送信時間の最適化は、Eメールまたはプッシュメッセージの送信に最適な時間を予測し、開封履歴とクリック率に基づいてエンゲージメントを最大化します。</p>
<p>この機能は現在ベータ版で、ベータ版のお客様のみがご利用いただけます。 ベータ版プログラムに参加するには、Adobeカスタマーケアにお問い合わせください。</p>
<p>詳しくは、<a href="building-journeys/journeys-message.md#send-time-optimization">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>ビジネスイベントでのスキーマの関係の活用 — ルックアップテーブル管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ビジネスイベントを設定する際に、スキーマ間の関係を活用できるようになりました。 これは、単一イベントを設定する場合、ジャーニーで条件を使用する場合、メッセージのパーソナライゼーション、カスタムアクションのパーソナライゼーションで、リンクされたテーブルのフィールドを活用する機能に加えて、</p>
<p>詳しくは、<a href="event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>
<!--
<table>
<thead>
<tr>
<th><strong>Personalized URLs</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Personalized URLs take recipients to specific pages of a website, or to a personalized microsite, depending on the profile attributes. In Adobe Journey Optimizer, you can now add personalization to URLs in your message content. URL personalization can be applied to text and images, and use profile data or contextual data.</p>
<p>For more information, refer to the <a href="documentation-updates.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>電子メールがユーザーに届くことを確認します — 電子メールの再試行</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>プリセットごとに再試行期間を定義して、不要になったときに再試行が実行されなくなるようになりました。 例えば、1日のみ有効なリンクを含むパスワードリセットトランザクションメッセージの再試行期間を24時間に設定できます。 なお、再試行設定はEメールチャネルにのみ適用されます。</p>
<p>詳しくは、 <a href="configuration/retries.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>
<!--
<table>
<thead>
<tr>
<th><strong>Customer Alerts</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now subscribe to event-based alerts regarding Adobe Journey Optimizer activities. The user interface allows you to view a history of received alerts based on metrics revealed by Adobe Experience Platform Observability Insights. The UI also allows you to view, enable, and disable available alert rules.</p>
<p>This feature is currently in beta version and only available to beta customers. To join the beta program, contact Adobe Customer Care.
</p>
<p>For more information, refer to the <a href="https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html">Adobe Experience Platform documentation</a>.</p>
</td>
</tr>
</tbody>
</table>
-->

### 機能強化

**ジャーニー**

* **動的ヘッダー**  - HTTPヘッダーパラメーターで動的データを渡せるようになりました。これらのパラメーターは、ジャーニーアクションのHTTP呼び出し（タイムスタンプや追跡IDなど）を受け取る統合システムで使用できます。 [詳細情報](action/about-custom-action-configuration.md#url-configuration)
* **動的URLパス**  — カスタムアクションの動的URLパスを設定できるようになりました。[詳細情報](action/about-custom-action-configuration.md#url-configuration)
* 読み取りセグメントの全体的なスロットル率は、1秒あたり17,000件から20,000件に変更されました。 [詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**ユーザーインターフェイス**

* **検索** ：各ページで、「統合Experience Cloud」検索フィールドから直接ビジネスオブジェクトやヘルプ記事を検索できるようになりました。[詳細情報](user-interface.md#unified-search)
* **最近の情報**  - Adobe Journey Optimizerホームページの最近の情報要素の表示が、追加のビジネスオブジェクトに拡張されました。この更新により、最近アクセスしたショートカットには、メッセージ、ジャーニー、セグメント、スキーマ、データセット、データソース、イベント、アクション、ソース、宛先が含まれます。 [詳細情報](action/about-custom-action-configuration.md#passing-collection)

**コンテンツデザイン**

* **背景**  — 背景画像がライブプレビューでサポートされるようになりました。[詳細情報](preview.md)
* **ワンクリックオプトアウトリンク**  - Eメールコンテンツに新しいタイプのリンクを挿入できます。オプ **トアウトリ** ンクを使用すると、ユーザーは、オプトアウトを確認するランディングページにリダイレクトされずに、1回のクリックで通信の受信を登録解除できます。[詳細情報](message-tracking.md#one-click-opt-out-link)

**パーソナライズ機能**

* **式エディター**  — パーソナライゼーションを定義する際に、フォールバック値を簡単に追加できるようになりました。プロファイルのパーソナライゼーションフィールドが空の場合、フォールバック値が表示されます。[詳細情報](documentation-updates.md)

**メールの設定**

* **許可リスト**  -許可リストは、API呼び出しを通じて、実稼動以外のサンドボックスで有効化および無効化できるようになりました。[詳細情報](allow-list.md#enable-allow-list)

<!--* **Suppression list** - Adding email addresses and domains into the suppression list is now available from the user interface, either one by one, either in bulk mode through a CSV file upload. [Learn more](configuration/manage-suppression-list.md#add-addresses-and-domains)-->
<!--* **Navigation** - The suppression list, which was accessible under the **Channels > Email configuration > General** menu, has been moved to the **Channels > Email configuration > Suppression list** menu for easier access. [Learn more](configuration/manage-suppression-list.md#access-suppression-list)-->


### 修正点

* メッセージタブのナビゲーションにおけるアクセシビリティの問題を修正しました。
* Eメールデザイナーのラベルに関するローカライゼーションの問題を修正しました。
* 1つのジャーニーで複数のノードを選択してプロパティパネルの「削除」をクリックする際の問題を修正しました。
* ジャーニーで使用するアクションに新しいヘッダーを追加できない問題を修正しました。
* ユーザーインターフェイスのより明示的な警告を使用して、メッセージプリセットの作成が失敗した理由を特定できるようになりました。


## 2021 年 7 月リリース {#july-2021-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>メッセージでのメタデータの使用 — ルックアップテーブル管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerに読み込んだ参照データを使用して、エクスペリエンスを強化します。 例としては、エクスペリエンスイベントの予約IDのメタデータの検索や、エクスペリエンスイベントのskuから製品情報を検索してキャンバスで使用する場合などがあります。 </p>
<p>スキーマ間の関係を活用して、1つのデータセットを別のデータセットのルックアップテーブルとして使用できるようになりました。 その後、単一イベントを設定する場合、ジャーニーで条件を使用する場合、メッセージのパーソナライゼーションで、カスタムアクションのパーソナライゼーションで、リンクされたテーブルのすべてのフィールドを活用できます。</p>
<p>詳しくは、<a href="event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
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
<p>詳しくは、 <a href="allow-list.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* 同じサンドボックスで同時に実行されるすべての「セグメントを読み取り」アクティビティの全体的なスロットルレートは、1 秒あたり 17,000 メッセージに制限されています。[詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)
* 「**キャッシュ時間**」フィールドがデータソース設定ペインから削除されました。[詳細情報](datasource/about-data-sources.md)
* 外部データソースの場合、1 秒あたり 15 回までの呼び出し回数制限（キャッピング）ルールが自動的に定義されるようになりました。 [詳細を読む](configuration/external-systems.md#capping)
* ライブジャーニーの場合、ジャーニーを公開した日付とユーザーの名前がジャーニープロパティ画面に表示されるようになりました。 [詳細を読む](building-journeys/journey-gs.md#change-properties)
* ジャーニーリスト画面にジャーニータイプフィルターが追加されました。 [詳細を読む](user-interface.md#section_lgm_hpz_pgb)
* **[!UICONTROL スロットルレート]**&#x200B;パラメーターが「セグメントを読み取り」アクティビティに追加されました。 [詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**メッセージのプレビューとテスト**

* ID と名前空間が&#x200B;**[!UICONTROL プレビュー]**&#x200B;画面に表示されるようになりました。[詳細情報](preview.md#preview-your-messages)
* 配達確認のテストメールの数が 10 個に制限されるようになりました。
* 配達確認の&#x200B;**件名行のプレフィックス**&#x200B;に使用できる文字が制限されるようになりました。 [詳細情報](preview.md#send-proofs)

**パーソナライゼーション式エディター**

* ヘルパードロップダウンリストの名前と順序が変更されました。

### 修正点

* 一括メール配信で重複メッセージが配信される問題を修正しました。
* 再試行期間が終了した後、メール送信が実行されない場合、それに応じてイベントが生成されるようになりました。
* PTR レコード画面に IP 情報が表示されない問題を修正しました。
* 式エディター内のオファーパネルのローカライゼーションが実装されました。
* 情報ポップアップの間隔の誤りを修正しました。
* `background-image`プロパティを含む内部スタイルシートがサポートされていないHTMLファイルをアップロードする際のEメールデザイナーの問題を修正しました。

